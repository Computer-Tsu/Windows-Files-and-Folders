# Windows Stored Credentials and Crypto Secrets


Introduced in (referenced-objects-that-are-not-files-or-folders.md)

# DPAPI & Repair Safety

The profile isn't just files and a registry hive — it's the anchor for a chain of encrypted
secrets. Deleting or rebuilding a profile, or resetting a password the wrong way, silently
destroys anything protected by **user-scope DPAPI**. This page is the "warn the client before you
nuke it" checklist.

---

## 1. DPAPI in one paragraph

The Data Protection API (`CryptProtectData` / `CryptUnprotectData`, and the CNG `NCryptProtectSecret`)
encrypts blobs with a **master key**. Each user has one or more master keys stored under their
profile; the master key itself is protected by a key derived from the **user's password** plus the
user's **SID**. Break the link to either the password or the SID and the master key - and every
secret under it - becomes unrecoverable. There is a parallel **machine/system DPAPI** scope
(`S-1-5-18`) that is *not* tied to any interactive user, which is why some secrets survive a
profile rebuild and others don't (§4).

---

## 2. Where the material lives

User scope (dies with the profile / hive):

| Store | Path |
|-------|------|
| DPAPI master keys | `%APPDATA%\Microsoft\Protect\<SID>\<GUID>` |
| — preferred key pointer | `%APPDATA%\Microsoft\Protect\<SID>\Preferred` |
| — credential history | `%APPDATA%\Microsoft\Protect\<SID>\CREDHIST` |
| — domain backup key ref | `%APPDATA%\Microsoft\Protect\<SID>\BK-<DOMAIN>` |
| Credential Manager (creds) | `%APPDATA%\Microsoft\Credentials\` and `%LOCALAPPDATA%\Microsoft\Credentials\` |
| Credential/Web Vault | `%LOCALAPPDATA%\Microsoft\Vault\` and `%APPDATA%\Microsoft\Vault\` |
| EFS / RSA private keys | `%APPDATA%\Microsoft\Crypto\RSA\<SID>\` |
| CNG private keys | `%APPDATA%\Microsoft\Crypto\Keys\` |

Machine / system scope (survives a user-profile rebuild; dies on OS reinstall):

| Store | Path | Protector |
|-------|------|-----------|
| System DPAPI master keys | `%WINDIR%\System32\Microsoft\Protect\S-1-5-18\` (and `\User\`) | Machine (LSA secret `DPAPI_SYSTEM`) |
| Saved Wi-Fi / WLAN keys | `%ProgramData%\Microsoft\Wlansvc\Profiles\Interfaces\{GUID}\{profile}.xml` | System DPAPI |
| System Vault | `%ProgramData%\Microsoft\Vault\` | System DPAPI |
| Machine certificate keys | `%ProgramData%\Microsoft\Crypto\{RSA,Keys}\` | Machine |
| Windows Hello (NGC) | `%WINDIR%\ServiceProfiles\LocalService\AppData\...\Ngc` | TPM / machine |

> Note the split: **saved Wi-Fi passwords are machine-scoped**, so they survive deleting a user
> profile - but an OS reinstall loses them. Credential Manager entries and EFS keys are the
> opposite: user-scoped, gone the moment the hive is rebuilt.

---

## 3. Password change vs. reset — the decisive distinction

| Scenario | DPAPI outcome |
|----------|---------------|
| User **changes** own password (supplies old one) | Master keys re-encrypted with the new password. **All secrets survive.** |
| User resets via **Windows Hello / MS-account** while signed in | Generally re-keyed; survives (MS-account path uses the online identity). |
| Admin **resets** a **local/workgroup** account password | Master keys **not** re-encrypted → **all user-DPAPI secrets lost.** `CREDHIST` can recover them *only* if the original password is later supplied. |
| Admin **resets** a **domain** account password | **Recoverable** - the DC holds a domain backup master key (MS-BKRP). Domain admin can decrypt. |

Operational upshot: on a standalone/workgroup box (most SMB clients), an admin password *reset*
is destructive to saved credentials and EFS. Have the user *change* their own password whenever
the old one is known, and never "reset from another admin account" as a first move if secrets
matter.

---

## 4. What actually dies on a profile rebuild

Rebuilding a profile (delete `ProfileList\<SID>` + folder, re-login) discards the user hive and
therefore the user-DPAPI chain. Casualties:

- **Credential Manager** - Windows credentials (incl. saved RDP `TERMSRV/*`, mapped-drive creds)
  and Web credentials.
- **EFS-encrypted files** - without the private key, `cipher`-encrypted files are unrecoverable
  unless a **Data Recovery Agent (DRA)** cert exists. This is the one that turns a routine repair
  into permanent data loss.
- **Browser saved passwords** - Chrome/Edge wrap their local AES key with DPAPI. Since **Chrome
  127 / Edge equivalent (mid-2024) "App-Bound Encryption"**, that key is additionally bound to a
  system service and machine, so even copying files between profiles no longer migrates them -
  export or account-sync beforehand.
- **Sticky Notes** - `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftStickyNotes_*\LocalState\plum.sqlite`
  (not DPAPI, but profile-local; copy it out).
- **App tokens** - anything an app stashed via `CryptProtectData` (VPN clients, mail clients,
  line-of-business apps).

Survives the rebuild (machine scope): saved Wi-Fi, machine certs, Windows Hello.

---

## 5. Pre-rebuild audit (run before you touch anything)

```powershell
<#
Author: Mark McDow | My Computer Guru, LLC
Purpose: Inventory profile-bound secrets before deleting/rebuilding a user profile.
Run in the AFFECTED user's context where possible (creds/EFS are user-scoped).
#>

'--- Credential Manager (Windows) ---'
cmdkey /list

'--- Vault stores ---'
vaultcmd /list
foreach ($v in (vaultcmd /list) -match ':') {}   # enumerate then:
vaultcmd /listcreds:"Windows Credentials" /all
vaultcmd /listcreds:"Web Credentials" /all

'--- EFS-encrypted files owned by this user ---'
cipher /u /n 2>$null      # lists files whose EFS key belongs to the current user

'--- Personal certificates with private keys (EFS/S-MIME/etc.) ---'
Get-ChildItem Cert:\CurrentUser\My |
  Select-Object Subject, Thumbprint, NotAfter, HasPrivateKey,
                @{n='EnhancedKeyUsage';e={($_.EnhancedKeyUsageList.FriendlyName) -join ','}}

'--- DPAPI master keys present ---'
$sid = [System.Security.Principal.WindowsIdentity]::GetCurrent().User.Value
Get-ChildItem "$env:APPDATA\Microsoft\Protect\$sid" -Force -ErrorAction SilentlyContinue |
  Select-Object Name, LastWriteTime
```

**Then, before rebuild:**
1. **Export EFS certs + keys** - `certmgr.msc` → Personal → export **with private key** to a PFX,
   or `certutil -user -exportPFX My <thumbprint> C:\safe\efs.pfx`. Store the PFX + password
   offline. (Alternative: pre-configure a DRA via GPO so recovery is centralized.)
2. **Export / sync browser passwords** - browser Settings → export CSV, or ensure profile sync is
   current. Delete the CSV after re-import.
3. **Record Credential Manager entries** - `cmdkey /list` output; recreate manually after (there
   is no supported bulk export of the encrypted blobs).

**Alternatives / tooling:** the same inventory in **batch** (`cmdkey /list`, `vaultcmd`,
`cipher /u /n`, `certutil -store -user My`); for fleet visibility, wrap steps 1–3 as a **Kaseya
VSA** pre-flight procedure that writes a "profile-secret risk" flag to a custom field before any
automated profile remediation runs. Nirsoft **CredentialsFileView** / **VaultPasswordView** (run
in-user-context) can decode the stores for documentation, but treat third-party credential
decoders as sensitive-use tools and keep them off shared shares.

---

## 6. References

- Microsoft `[MS-DPAPI]` / `[MS-BKRP]` protocol docs (master-key derivation, domain backup key).
- Microsoft Learn: "Protecting Data with the Data Protection API", EFS recovery-agent docs.
- Passcape / Elcomsoft DPAPI write-ups (offline master-key decryption mechanics - for
  understanding, not endorsement).
- Benjamin Delpy (`mimikatz` `dpapi::` modules) documentation - the definitive practical
  reference for how the chain fits together; relevant to both recovery and IR.

