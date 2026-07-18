# User Profiles

- folder path locations
- .default profile
  - use
  - corruption / repair
- All Users/Public
- sid mapping
- copying profiles
- moving / migrating
  - copy profile UI
  - tools
    - Microsoft Migrate User tool
- repairing or recovery
- Types
  - Local
  - AD
  - MSA
  - AAD (365 Work / School)
    - allow login for this app only vs all apps / this machine
- Appendix
  - security ACL

Create a local user, bypass the MSA wizard

windows 10 1807 feature update damaged default profile. existing users could log in to workstation but new user could not.

post feature update profile updating

Default / All Users when provisioning a Windows image, you can preinstall Windows Terminal or other MSIX apps) with the PowerShell cmdlet `Add-AppXProvisionedPackage`. This provisions the package so that any user logging into the machine will have the installation registered for them.

User State Migration Tool (USMT) is part of the Windows Assessment and Deployment Kit (ADK)


-----

# Windows User Profiles — Technical Reference

Scope: local + roaming user profiles on Windows 10/11 and Server 2016–2025. Covers on-disk
anatomy, registry mappings, SID structure, default ACLs, load/unload mechanics, and repair
workflows. Paths assume `%SystemDrive%` = `C:` and `ProfilesDirectory` = `C:\Users`.

---

## 1. Profile types

| Type | Backing store | Notes |
|------|---------------|-------|
| **Local** | `C:\Users\<name>` | Default. Machine-bound. |
| **Roaming (RUP)** | UNC share + local cache | `%username%.V6` suffix on Win10/11 (profile version 6). Cached under `C:\Users\<name>`. |
| **Mandatory** | `NTUSER.MAN` (read-only) | Renamed `NTUSER.DAT`; changes discarded at logoff. |
| **Super-mandatory** | Share path ends in `.man` | User cannot log on if profile is unavailable. |
| **Temporary** | `C:\Users\TEMP` | Fallback when the real profile fails to load. Data lost at logoff. |
| **Special/service** | see §2 | System, LocalService, NetworkService. |

Profile version suffixes track the ABI: `.V2` (Vista/7), `.V3/.V4` (8/8.1), `.V5` (early 10),
`.V6` (10 1607+ / 11). A mismatch forces a new profile — the root cause of most "brand-new
desktop after upgrade" complaints.

---

## 2. On-disk anatomy

### 2.1 Profile root

```
C:\Users\
├── <username>\          user profile
├── Default\             template copied for every new profile (hidden)
├── Public\              shared "All Users" data
├── Default User         → junction to Default (XP-compat, hidden)
└── desktop.ini / AppData…
```

Special/service profiles live outside `C:\Users`:

| Principal | SID | Profile path |
|-----------|-----|--------------|
| Local System | `S-1-5-18` | `C:\Windows\System32\config\systemprofile` |
| Local Service | `S-1-5-19` | `C:\Windows\ServiceProfiles\LocalService` |
| Network Service | `S-1-5-20` | `C:\Windows\ServiceProfiles\NetworkService` |

### 2.2 Essential files inside a profile

| File | Maps to | Purpose |
|------|---------|---------|
| `NTUSER.DAT` | `HKU\<SID>` → `HKCU` | Per-user registry hive. |
| `NTUSER.DAT.LOG1`, `.LOG2` | — | Registry transaction logs (dirty-page recovery). |
| `ntuser.dat{...}.TM.blf`, `.regtrans-ms` | — | CLFS/KTM transaction logs for registry writes. |
| `ntuser.ini` | — | Excludes folders from roaming; roaming metadata. |
| `AppData\Local\Microsoft\Windows\UsrClass.dat` | `HKU\<SID>_Classes` → `HKCU\Software\Classes` | Per-user file associations, COM registrations, shell state. |
| `UsrClass.dat.LOG1/.LOG2` | — | Transaction logs for the Classes hive. |

`NTUSER.DAT` and `UsrClass.dat` are the two that matter for corruption; everything else is
regenerable.

### 2.3 Known folders (Win10/11 defaults)

`Desktop, Documents, Downloads, Music, Pictures, Videos, Favorites, Links, Contacts,
Searches, Saved Games, 3D Objects` (deprecated), plus:

```
AppData\
├── Roaming\    → %APPDATA%      (roams with RUP)
├── Local\      → %LOCALAPPDATA% (machine-local, incl. UsrClass.dat, Temp)
└── LocalLow\                    (low-integrity, e.g. IE/Edge protected mode)
```

### 2.4 Legacy junction reparse points (XP → Vista+ compat)

Hidden, system, and protected by a **deny-list ACL** (`Everyone: Deny List Folder / Read Data`)
so apps traverse but users don't enumerate them. Attempting `dir` on them throws Access Denied
by design — not corruption.

```
Application Data   → AppData\Roaming
Local Settings     → AppData\Local
My Documents       → Documents
Cookies            → AppData\Local\Microsoft\Windows\INetCookies
NetHood            → AppData\Roaming\Microsoft\Windows\Network Shortcuts
PrintHood          → AppData\Roaming\Microsoft\Windows\Printer Shortcuts
Recent             → AppData\Roaming\Microsoft\Windows\Recent
SendTo             → AppData\Roaming\Microsoft\Windows\SendTo
Start Menu         → AppData\Roaming\Microsoft\Windows\Start Menu
Templates          → AppData\Roaming\Microsoft\Windows\Templates
```

Inspect with `dir /a:l C:\Users\<name>` or `fsutil reparsepoint query "<path>"`.

---

## 3. SID structure

```
S - 1 - 5 - 21 - X1-X2-X3 - RID
│   │   │    │       │        └── Relative Identifier (account within the authority)
│   │   │    │       └── 96-bit machine/domain identifier (three 32-bit subauthorities)
│   │   │    └── SECURITY_NT_NON_UNIQUE (local/domain accounts)
│   │   └── SECURITY_NT_AUTHORITY (identifier authority 5)
│   └── revision (always 1)
└── literal "S"
```

Well-known RIDs (appended to the machine/domain identifier):

| RID | Account |
|-----|---------|
| `500` | Built-in Administrator |
| `501` | Guest |
| `503` | DefaultAccount |
| `504` | WDAGUtilityAccount |
| `512` | Domain Admins (domain) |
| `513` | Domain Users (domain) |
| `1000+` | First and subsequent locally-created accounts |

Binary form (as stored in `ProfileList\...\Sid` `REG_BINARY`): `01` revision, `05` subauth
count, `000000000005` authority, then little-endian DWORDs for `21`, X1, X2, X3, RID.

Resolve names ↔ SIDs:

```powershell
# SID → name
([System.Security.Principal.SecurityIdentifier]'S-1-5-21-...-1001').Translate([System.Security.Principal.NTAccount])
# name → SID
(New-Object System.Security.Principal.NTAccount('DOMAIN\user')).Translate([System.Security.Principal.SecurityIdentifier])
```

CLI equivalents: `wmic useraccount where name='user' get sid` (deprecated),
`whoami /user`, or `PsGetSid`.

---

## 4. Registry mappings

### 4.1 Global profile configuration

`HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`

| Value | Type | Default | Meaning |
|-------|------|---------|---------|
| `ProfilesDirectory` | `REG_EXPAND_SZ` | `%SystemDrive%\Users` | Root for all profiles. |
| `Default` | `REG_EXPAND_SZ` | `%SystemDrive%\Users\Default` | Template profile. |
| `Public` | `REG_EXPAND_SZ` | `%SystemDrive%\Users\Public` | Shared profile. |
| `ProgramData` | `REG_EXPAND_SZ` | `%SystemDrive%\ProgramData` | All-users app data. |
| `AllUsersProfile` | `REG_SZ` | `ProgramData` | Legacy alias. |

Relocating `C:\Users` to another volume = change `ProfilesDirectory` **before** any profile is
created (sysprep/audit mode). Post-hoc edits break existing hardcoded paths.

### 4.2 Per-profile subkeys

`HKLM\...\ProfileList\<SID>`

| Value | Type | Meaning |
|-------|------|---------|
| `ProfileImagePath` | `REG_EXPAND_SZ` | Path to the profile folder (i.e. to its `NTUSER.DAT`). |
| `Sid` | `REG_BINARY` | Binary SID (redundant with key name). |
| `Flags` | `REG_DWORD` | Profile flags. |
| `State` | `REG_DWORD` | Bitmask (see §4.3). |
| `RefCount` | `REG_DWORD` | Live load references. `0` = fully unloaded. |
| `Guid` | `REG_SZ` | Links to `…\ProfileGuid\{GUID}`. |
| `ProfileLoadTimeLow/High`, `LocalProfileLoadTimeLow/High`, `LocalProfileUnloadTimeLow/High` | `REG_DWORD` | FILETIME halves for forensics. |
| `RunLogonScriptSync` | `REG_DWORD` | Sync logon-script execution. |

Companion keys:
- `HKLM\...\ProfileGuid\{GUID}` → back-reference to the SID (used by roaming/GP).
- `HKLM\...\ProfileNotification` → subsystems notified on load/unload.
- `HKLM\...\Winlogon` → `Userinit`, `Shell` (profile bootstrap; malware-persistence hotspot).

### 4.3 `State` bitmask (documented flags)

| Bit | Meaning |
|-----|---------|
| `0x0001` | Mandatory profile |
| `0x0002` | Update locally cached profile |
| `0x0004` | New local profile |
| `0x0008` | New central (roaming) profile |
| `0x0010` | Update central profile |
| `0x0020` | Delete cached profile |
| `0x0040` | Upgrade profile |
| `0x0080` | Guest user profile |
| `0x0100` | Administrator profile |
| `0x0200` | Default net profile available |
| `0x0400` | Slow link detected |
| `0x0800` | Temporary profile loaded |

For repair, `State` and `RefCount` are simply zeroed (§7.1) — you are not reasoning about
individual bits, just clearing the "stuck/temp" condition.

### 4.4 HKCU vs HKU

`HKCU` is not a real hive — it is a symbolic link resolving to `HKU\<SID>` for the interactive
console user. Per-user Classes live at `HKU\<SID>_Classes` (backed by `UsrClass.dat`) and
surface under `HKCU\Software\Classes`. Shell folder redirection lives at:

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders   (with env vars)
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders        (resolved paths)
```

To edit another user's hive offline:

```cmd
reg load HKU\Offline "C:\Users\<name>\NTUSER.DAT"
:: ...edit HKU\Offline...
reg unload HKU\Offline
```

Unload cleanly — a leaked handle is the classic cause of Event ID **1530** ("registry file is
still in use") and profile-unload failures.

---

## 5. Default ACLs

### 5.1 `C:\Users\<name>` (profile root)

Non-inherited, non-propagating to peers; a freshly-created profile gets:

```
NT AUTHORITY\SYSTEM:(OI)(CI)(F)
BUILTIN\Administrators:(OI)(CI)(F)
<DOMAIN>\<user>:(OI)(CI)(F)
```

Owner: the user (or Administrators for admin-created). Verify with
`icacls "C:\Users\<name>"`.

### 5.2 `C:\Users` (container)

```
SYSTEM:(OI)(CI)(F)
Administrators:(OI)(CI)(F)
Users:(RX) and (OI)(CI)(IO)(GR,GE)      # traverse + read
Everyone:(RX) and (OI)(CI)(IO)(GR,GE)   # traverse only
```

### 5.3 `NTUSER.DAT` / hive

`SYSTEM:(F)`, `Administrators:(F)`, `<user>:(F)`. The loaded hive's registry ACL
(`HKU\<SID>`) mirrors this: SYSTEM, RESTRICTED, and the owning user get access; other standard
users do not.

### 5.4 Repairing broken ACLs

```cmd
:: Re-grant the canonical set and reset inheritance downward
icacls "C:\Users\<name>" /setowner "<user>" /T /C
icacls "C:\Users\<name>" /grant "SYSTEM:(OI)(CI)F" "Administrators:(OI)(CI)F" "<user>:(OI)(CI)F" /T /C
icacls "C:\Users\<name>" /inheritance:e /T /C
```

Nuclear reset (re-inherit everything from parent, wiping explicit ACEs):
`icacls "C:\Users\<name>" /reset /T /C`. Use with care — it also clears the deny ACEs on the
legacy junctions in §2.4.

---

## 6. Load / unload mechanics

1. **Winlogon/LSA** authenticates; a token with the user's SID is created.
2. **User Profile Service** (`ProfSvc`, `profsvc.dll`) reads `ProfileList\<SID>`.
3. `NTUSER.DAT` is loaded into `HKU\<SID>`; `UsrClass.dat` into `HKU\<SID>_Classes`.
4. `HKCU` link is bound; `RefCount` increments, `State` updated.
5. Shell (`explorer.exe`) launches per `Winlogon\Shell`; `Userinit` runs logon scripts / GPO.
6. At logoff: hives flushed and unloaded, `RefCount` → 0, unload time stamped.

Diagnostics:
- **Event log:** `Applications and Services Logs → Microsoft → Windows → User Profile Service →
  Operational`, plus Application-log source **User Profile Service** (IDs 1500–1542). Notables:
  `1511`/`1515` temp profile loaded, `1509` copy error, `1500`/`1508` load failure, `1521`
  can't unload, **1530** registry-in-use handle leak.
- **Live:** `Get-CimInstance Win32_UserProfile | Select SID,LocalPath,Loaded,Status,Special`.
- **Deep:** Process Monitor filtered on `profsvc`/`NTUSER.DAT` to catch the exact `ACCESS DENIED`
  or `SHARING VIOLATION` behind a failed load.

---

## 7. Repair workflows

### 7.1 "The User Profile Service failed the logon" (temp/`.bak`)

Cause: `ProfileList\<SID>` points at a missing/renamed folder, or a `.bak` shadow key exists
because Windows fell back to a temp profile.

Under `HKLM\...\ProfileList`:
- **Two keys** (`<SID>` and `<SID>.bak`): rename the live one to `<SID>.bk`, drop `.bak` off the
  backup so it becomes `<SID>`, then rename `.bk` → `.bak`. Net effect: the good backup becomes
  the active key without a name collision.
- **One key** (`<SID>.bak`): just remove the `.bak` suffix.

Then on the now-active `<SID>` key:
- `RefCount` = `0`
- `State` = `0`
- Confirm `ProfileImagePath` points to the real, existing folder.

Reboot, log on. (Script: KB947215 All-In-One Framework sample.)

### 7.2 Orphaned SID (deleted profile folder, stale registry entry)

Manually deleting `C:\Users\<name>` leaves the `ProfileList\<SID>` key, so Windows keeps trying
to load a dead path. Remove it via:

- **GUI:** `sysdm.cpl` → Advanced → User Profiles → *Settings* → select → *Delete* (removes folder
  **and** registry key + ProfileGuid — the correct way, versus hand-deleting either half).
- **WMI/PowerShell:**
  ```powershell
  Get-CimInstance Win32_UserProfile |
    Where-Object { $_.LocalPath -like '*<name>' -and -not $_.Special } |
    Remove-CimInstance
  ```
- **Tooling:** `DelProf2` (Helge Klein) for bulk/stale-by-age cleanup across endpoints —
  scriptable and Kaseya-friendly.

### 7.3 Rebuild a corrupt profile (preserve data)

1. Log on as a different local admin (or built-in Administrator in Safe Mode).
2. `sysdm.cpl` → *Delete* the broken profile (or rename `C:\Users\<name>` → `<name>.old` and
   delete the `ProfileList\<SID>` key).
3. Log the user back in → fresh profile from `C:\Users\Default`.
4. Copy data selectively from `<name>.old`: `Desktop, Documents, Downloads, Pictures,
   Favorites`, and app data folders you trust. **Do not** copy `NTUSER.DAT`/`UsrClass.dat` —
   that reintroduces the corruption.

### 7.4 Offline hive check

```cmd
reg load HKU\Chk "C:\Users\<name>\NTUSER.DAT"   :: success alone proves the hive mounts
reg unload HKU\Chk
```

If it won't load, the hive is corrupt: restore from `NTUSER.DAT.LOG*` is automatic on next
mount attempt; if that fails, the profile is a rebuild (§7.3). System-wide integrity issues:
`sfc /scannow` then `DISM /Online /Cleanup-Image /RestoreHealth`.

### 7.5 Reset a mangled Default profile

If new profiles inherit breakage, the `C:\Users\Default` template is polluted. Rebuild it from a
clean reference via `sysprep /generalize` with a `CopyProfile=true` unattend, or restore
`Default` from a known-good image. Ad-hoc file copies into `Default` are unsupported and often
carry ACL problems forward.

---

## 8. Query / audit script

```powershell
<#
Author: Mark McDow | My Computer Guru, LLC
Purpose: Enumerate ProfileList against Win32_UserProfile; flag orphans and temp/.bak state.
#>
$base = 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList'
Get-ChildItem $base | ForEach-Object {
    $p    = Get-ItemProperty $_.PSPath
    $sid  = Split-Path $_.PSPath -Leaf
    $path = [Environment]::ExpandEnvironmentVariables($p.ProfileImagePath)
    [pscustomobject]@{
        SID          = $sid
        Path         = $path
        Exists       = Test-Path $path
        RefCount     = $p.RefCount
        State        = ('0x{0:X4}' -f $p.State)
        BakShadow    = $sid.EndsWith('.bak')
        Account      = try { ([Security.Principal.SecurityIdentifier]($sid -replace '\.bak$')).
                              Translate([Security.Principal.NTAccount]).Value } catch { '<unresolved>' }
    }
} | Format-Table -Auto
```

Orphan = `Exists = False`. Stuck = `RefCount ≠ 0` while logged off, or `BakShadow = True`.

**Alternatives:** the same enumeration in **`reg query`** + `for /f` batch, in **CIM/WMIC**
(`Win32_UserProfile`), or via **`wmic path win32_userprofile`** if you need a one-liner on legacy
boxes. For fleet-wide collection, wrap the above as a Kaseya VSA procedure writing `SID/Path/State`
to a custom field.

---

## 9. Authoritative sources

**Primary / reference-grade**
- *Windows Internals, 7th ed.* (Yosifovich, Russinovich, Solomon, Ionescu) — Ch. 7 (Security:
  SIDs, tokens, ACLs) and registry/HKU internals. The canonical treatment.
- Honeycutt, *Microsoft Windows Registry Guide, 2nd ed.* — Ch. 12 "Mapping Tweaks / User
  Profiles" (ProfileList ↔ HKU ↔ HKCU relationship).
- Microsoft Learn: "Deploy Roaming User Profiles", "User State Migration Tool (USMT)",
  "SID-related KB / well-known SIDs" reference, and the `ProfileList` / User Profile Service
  documentation. (Search current URLs on learn.microsoft.com; the Server-2003-era HKCU/HKU
  articles still describe the unchanged mechanics.)

**SID / well-known accounts**
- Microsoft "Well-known SID structures" (`[MS-DTYP]` §2.4.2.4) and the "Security identifiers"
  Learn article.

**Repair / troubleshooting**
- KB947215 "The User Profile Service failed the logon" + the All-In-One Script Framework VBScript
  sample (archived on Microsoft Learn) — the `.bak`/`State`/`RefCount` procedure.
- Helge Klein, `DelProf2` documentation (bulk profile cleanup, stale-by-age).

**Forensics-oriented (excellent for exact value semantics)**
- Psmths, *windows-forensic-artifacts* → `account/profile-list-key.md` (per-value breakdown with
  live `Get-ItemProperty` output).
- forensafe / SANS DFIR posts on ProfileList timestamps and orphan detection.

> Vendor how-to pages (MakeUseOf, TheITBros, WinTips, GeeksforGeeks) reliably reproduce the §7.1
> `.bak` procedure with screenshots but treat them as procedure confirmation, not authority.

