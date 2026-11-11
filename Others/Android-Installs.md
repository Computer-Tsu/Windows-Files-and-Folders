# Android Tools: ADB and Fastboot
 
Reference for installing, using, and removing the Android Debug Bridge (ADB) and fastboot on a technician's computer, with worked examples for app inspection, backups, file transfer, boot modes, rooting, and phone migration.
 
## Contents
 
- [Quick Facts](#quick-facts)
- [Install](#install)
- [Phone Setup](#phone-setup)
- [Command Structure](#command-structure)
- [Command Reference](#command-reference)
- [Worked Example Examining an App](#worked-example-examining-an-app)
- [Backups](#backups)
- [Moving Files](#moving-files)
- [File System Map](#file-system-map)
- [Property and Settings Files](#property-and-settings-files)
- [Boot Modes](#boot-modes)
- [Rooting Walkthroughs](#rooting-walkthroughs)
- [Migration Guide](#migration-guide)
- [Troubleshooting](#troubleshooting)
- [References](#references)
## Quick Facts
 
| Item | Detail |
| :--- | :--- |
| Package name | Android SDK Platform-Tools |
| Publisher | Google |
| Main programs | `adb` (talks to a running phone), `fastboot` (talks to the bootloader) |
| Installer | None. Portable zip, unpack and run |
| Default folder | Wherever it is unzipped, commonly `C:\platform-tools` |
| Per-user data | `%USERPROFILE%\.android` (Windows), `~/.android` (macOS, Linux) |
| Background process | `adb.exe` server, TCP port 5037 on localhost |
| Runtime needed | None. Java is not required |
| Registry footprint | None of its own. Only a PATH entry if you add one |
 
## Install
 
### Download Sources
 
| Source | Command or location | Notes |
| :--- | :--- | :--- |
| Google direct, latest | `https://dl.google.com/android/repository/platform-tools-latest-windows.zip` | Also `-latest-darwin.zip` and `-latest-linux.zip`. File name carries no version |
| Google direct, pinned | `https://dl.google.com/android/repository/platform-tools_r<version>-windows.zip` | Same pattern with `darwin` or `linux`. Use for repeatable installs |
| Google release page | [SDK Platform Tools release notes](https://developer.android.com/tools/releases/platform-tools) | Shows which version "latest" currently is |
| Android Studio | Tools > SDK Manager > SDK Tools > Android SDK Platform-Tools | Installs under the SDK folder, not `C:\platform-tools` |
| `sdkmanager` | `sdkmanager "platform-tools"` | Needs Google's command-line tools and Java first |
| WinGet | `winget install Google.PlatformTools` | Community manifest, pulls Google's zip |
| Scoop | `scoop install adb` | Community package |
| Chocolatey | `choco install adb` | Community package |
| Homebrew (macOS) | `brew install --cask android-platform-tools` | Community cask |
| Debian, Ubuntu | `sudo apt install adb fastboot` | Distro build, often older than Google's |
| Fedora | `sudo dnf install android-tools` | Distro build |
| Arch | `sudo pacman -S android-tools` | Distro build |
| AOSP source | `platform/packages/modules/adb` on `android.googlesource.com` | Source only. No binaries |
| GitHub | None official | Mirrors and wrapper scripts only |
| Browser, no install | WebADB-style pages using WebUSB in Chrome or Edge | Covers shell, files, and app install. Nothing left on the computer |
 
Download, unpack, and verify on Windows (PowerShell):
 
```powershell
$url = 'https://dl.google.com/android/repository/platform-tools-latest-windows.zip'
$zip = "$env:TEMP\platform-tools.zip"
Invoke-WebRequest -Uri $url -OutFile $zip
Expand-Archive -Path $zip -DestinationPath 'C:\' -Force
& 'C:\platform-tools\adb.exe' version
```
 
Same thing on macOS or Linux:
 
```bash
curl -LO https://dl.google.com/android/repository/platform-tools-latest-linux.zip
unzip platform-tools-latest-linux.zip -d ~/
~/platform-tools/adb version
```
 
The zip always unpacks into a `platform-tools` subfolder. Google's SDK repository manifest (an XML file on `dl.google.com/android/repository/`, for example `repository2-3.xml`) lists the size and checksum of each package for verification.
 
### Where It Goes
 
| OS | Typical location | PATH change |
| :--- | :--- | :--- |
| Windows, manual | `C:\platform-tools` | Optional, added by hand |
| Windows, WinGet | `%LOCALAPPDATA%\Microsoft\WinGet\Packages\Google.PlatformTools_*` | Added by WinGet |
| Windows, Android Studio | `%LOCALAPPDATA%\Android\Sdk\platform-tools` | Not added |
| macOS, manual | `~/platform-tools` or `~/Library/Android/sdk/platform-tools` | Shell profile (`~/.zshrc`) |
| Linux, manual | `~/platform-tools` | Shell profile (`~/.bashrc`) |
| Linux, distro package | `/usr/bin/adb`, `/usr/bin/fastboot` | Already on PATH |
 
Add the folder to the user PATH on Windows without touching the machine PATH:
 
```powershell
$p = [Environment]::GetEnvironmentVariable('Path', 'User')
[Environment]::SetEnvironmentVariable('Path', "$p;C:\platform-tools", 'User')
```
 
PATH registry locations:
 
| Scope | Key | Value |
| :--- | :--- | :--- |
| Current user | `HKEY_CURRENT_USER\Environment` | `Path` (REG_EXPAND_SZ) |
| All users | `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Environment` | `Path` (REG_EXPAND_SZ) |
 
A PATH entry is not required. Run `C:\platform-tools\adb.exe` by full path, or open the terminal in that folder.
 
### Minimal File Set
 
| File | Needed for | Keep |
| :--- | :--- | :--- |
| `adb.exe` | Everything ADB | Yes |
| `AdbWinApi.dll` | USB access on Windows | Yes |
| `AdbWinUsbApi.dll` | USB access on Windows | Yes |
| `libwinpthread-1.dll` | Threading library used by recent builds | Yes, if present in the zip |
| `fastboot.exe` | Bootloader work, flashing, rooting | Only if needed |
| `source.properties` | Text file holding `Pkg.Revision` (the version) | Handy |
| `sqlite3.exe`, `mke2fs.exe`, `make_f2fs.exe`, `etc1tool.exe`, `hprof-conv.exe` | Developer utilities | No |
 
On macOS and Linux, `adb` is a single binary. The exact Windows file list changes between releases, so copy the minimal set to a new folder and confirm with `adb version` before trusting it on a thumb drive.
 
### Dependencies
 
| Dependency | When needed | Source | How to update |
| :--- | :--- | :--- | :--- |
| USB driver (Windows) | Phone not detected, or shows with a warning in Device Manager | Windows Update, phone maker, or Google USB Driver for Pixel | Device Manager > Update driver, Windows Update optional updates, or the maker's installer |
| udev rules (Linux) | `adb devices` shows `no permissions` | Distro package such as `android-sdk-platform-tools-common`, or a rules file in `/etc/udev/rules.d/` | Package manager |
| Data-capable USB cable | Always | | Replace it. Charge-only cables are a top cause of "no device" |
| USB debugging on the phone | Always | Developer options | See [Phone Setup](#phone-setup) |
| Java, Android Studio | Never for ADB itself | | Their own updaters |
 
List and inspect installed phone drivers on Windows from an elevated prompt:
 
```cmd
pnputil /enum-drivers
```
 
### Check Versions
 
| Check | Command |
| :--- | :--- |
| ADB version and install path | `adb version` |
| Fastboot version | `fastboot --version` |
| Version without running anything | Open `source.properties`, read `Pkg.Revision` |
| Which copy is on PATH (Windows) | `where adb` |
| Which copy is on PATH (macOS, Linux) | `which adb` |
| WinGet package version | `winget list Google.PlatformTools` |
| Phone-side ADB daemon and Android version | `adb shell getprop ro.build.version.release` |
| Driver version (Windows) | Device Manager > device > Properties > Driver |
 
More than one `adb` on the PATH causes `adb server version doesn't match this client` errors. `where adb` shows every copy.
 
### Update
 
| Install type | Update steps |
| :--- | :--- |
| Manual zip | `adb kill-server`, download the new zip, unpack over the old folder, `adb version` |
| WinGet | `winget upgrade Google.PlatformTools` |
| Scoop | `scoop update adb` |
| Chocolatey | `choco upgrade adb` |
| Homebrew | `brew upgrade --cask android-platform-tools` |
| Distro package | `sudo apt update && sudo apt upgrade` or the distro equivalent |
| Android Studio | SDK Manager shows an update when one exists |
 
ADB does not update itself and does not notify.
 
### Uninstall
 
1. Stop the server: `adb kill-server`
2. Delete the folder, for example `C:\platform-tools`. For packaged installs use `winget uninstall Google.PlatformTools`, `scoop uninstall adb`, `choco uninstall adb`, `brew uninstall --cask android-platform-tools`, or `sudo apt remove adb fastboot`.
3. Remove the PATH entry (Settings > System > About > Advanced system settings > Environment Variables, or the registry keys listed above).
4. Delete `%USERPROFILE%\.android` (or `~/.android`). It holds `adbkey` and `adbkey.pub`, the key pair that phones have been told to trust.
5. Optional: remove a phone-maker USB driver with Settings > Apps, or `pnputil /delete-driver oemNN.inf /uninstall` from an elevated prompt.
6. Optional: remove `ANDROID_HOME` and `ANDROID_SDK_ROOT` environment variables if Android Studio set them.
7. Verify in a new terminal: `adb version` should fail with command not found.
Phone side: Developer options > Revoke USB debugging authorizations, then turn USB debugging off. Deleting the keys on the computer does not remove that computer from the phone's trusted list.
 
## Phone Setup
 
1. Settings > About phone > tap **Build number** seven times. Developer options appears.
2. Developer options > turn on **USB debugging**.
3. Connect by USB. Unlock the phone and accept the **Allow USB debugging** prompt showing the computer's key fingerprint.
4. Run `adb devices`. Status should read `device`.
| `adb devices` status | Meaning |
| :--- | :--- |
| `device` | Connected and authorized |
| `unauthorized` | Prompt on the phone not yet accepted |
| `offline` | Connection stalled. Replug, or `adb kill-server` |
| `recovery`, `sideload` | Phone is in recovery mode |
| (empty list) | Cable, driver, or USB debugging is off |
 
Wireless (Android 11 and later): Developer options > Wireless debugging > Pair device with pairing code. Then `adb pair IP:PORT`, enter the code, and `adb connect IP:PORT` using the port shown on the main Wireless debugging screen.
 
## Command Structure
 
ADB commands are layered, not a fixed verb and noun pair. Read them left to right:
 
- `adb` : the program on the computer
  - Optional target selector
    - `-s SERIAL` : pick one device when several are connected
    - `-d` : the only USB device
    - `-e` : the only emulator
  - Then one of two branches
    - **ADB commands**, handled by ADB itself
      - Connection: `devices`, `connect`, `pair`, `tcpip`, `kill-server`
      - Apps: `install`, `uninstall`
      - Files: `push`, `pull`
      - Diagnostics: `logcat`, `bugreport`
      - Power: `reboot`
    - **`shell`**, which passes the rest of the line to the phone's own command line
      - Android tools: `pm` (packages), `am` (activities), `dumpsys` (system services), `getprop` (properties), `settings`, `input`, `cmd`
        - Each has its own subcommands: `pm list packages`, `am force-stop`
        - Options start with a dash: `-r`, `-k`, `--user 0`
        - Package names and paths are plain arguments
      - Standard Linux tools: `ls`, `cp`, `mv`, `rm`, `cat`, `df`, `touch`, `grep`
Pattern: `adb [target] <adb-command> [options] [arguments]` or `adb [target] shell <tool> <subcommand> [options] [arguments]`
 
`fastboot` is a separate program with its own pattern: `fastboot [options] <command> [partition] [file]`. It only works while the phone is in bootloader or fastbootd mode, where `adb` does not respond.
 
Pipes and Windows: in `adb shell dumpsys battery | findstr level` the pipe runs on the computer. To run the pipe on the phone and use `grep`, quote the whole phone-side command:
 
```cmd
adb shell "dumpsys package com.android.chrome | grep -i version"
```
 
## Command Reference
 
### Connection and Server
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb version` | Read the label on the tool |
| `adb devices` | Roll call. Who is plugged in and are they talking to me |
| `adb devices -l` | Roll call with model and transport details |
| `adb start-server` | Turn the switchboard on |
| `adb kill-server` | Turn the switchboard off. First fix for odd behavior |
| `adb reconnect` | Hang up and redial |
| `adb pair IP:PORT` | Exchange a one-time code so the phone trusts this computer over Wi-Fi |
| `adb connect IP:PORT` | Dial the phone over the network |
| `adb disconnect` | Hang up all network connections |
| `adb tcpip 5555` | Tell a USB-connected phone to also listen on the network |
| `adb usb` | Tell the phone to go back to USB only |
| `adb -s SERIAL <command>` | Address the envelope to one specific phone |
| `adb wait-for-device` | Hold the line until a phone answers. Useful in scripts |
| `adb get-state` | Ask which mode the phone is in |
| `adb get-serialno` | Read the phone's serial number |
| `adb forward tcp:8080 tcp:8080` | Run a pipe from a computer port to a phone port |
| `adb reverse tcp:8080 tcp:8080` | Run a pipe from a phone port to a computer port |
| `adb root`, `adb unroot` | Restart the phone-side daemon as root. Works only on engineering builds, not retail phones |
 
### Apps
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb install app.apk` | Hand the phone an app and have it installed |
| `adb install -r app.apk` | Replace the app, keep its data |
| `adb install -d app.apk` | Allow an older version over a newer one |
| `adb install-multiple base.apk split1.apk` | Install an app that ships as several pieces |
| `adb uninstall com.example.app` | Remove the app and its data |
| `adb uninstall -k com.example.app` | Remove the app, leave its data behind |
| `adb shell pm list packages` | Inventory of every package |
| `adb shell pm list packages -3` | Only apps the user added |
| `adb shell pm list packages -s` | Only apps that came with the phone |
| `adb shell pm list packages -d` | Only disabled (frozen) apps |
| `adb shell pm list packages -i` | Inventory with who installed each one |
| `adb shell pm path com.example.app` | Where the app's installer file is stored |
| `adb shell pm clear com.example.app` | Reset the app to day one |
| `adb shell pm disable-user --user 0 com.example.app` | Freeze the app. Still installed, cannot run |
| `adb shell pm enable com.example.app` | Thaw a frozen app |
| `adb shell pm uninstall --user 0 com.example.app` | Remove a preinstalled app for this user only |
| `adb shell cmd package install-existing com.example.app` | Bring back an app removed with the line above |
| `adb shell pm grant com.example.app android.permission.CAMERA` | Hand the app a permission |
| `adb shell pm revoke com.example.app android.permission.CAMERA` | Take a permission back |
| `adb shell am start -n com.example.app/.MainActivity` | Open a specific screen of an app |
| `adb shell am force-stop com.example.app` | Pull the plug on a running app |
| `adb shell monkey -p com.example.app 1` | Launch an app by package name alone |
 
### Files
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb push local.txt /sdcard/Download/` | Copy from the computer to the phone |
| `adb pull /sdcard/Download/file.txt .` | Copy from the phone to the current folder |
| `adb push Music /sdcard/` | Copy a whole folder to the phone |
| `adb pull /sdcard/DCIM ./photos` | Copy a whole folder from the phone |
| `adb push --sync Music /sdcard/` | Copy only files that are newer on the computer |
| `adb shell ls -la /sdcard/` | List a phone folder, hidden files included |
| `adb shell cp /sdcard/a.mp3 /sdcard/Ringtones/` | Copy between two places on the phone |
| `adb shell mv /sdcard/a.txt /sdcard/Documents/` | Move or rename on the phone |
| `adb shell rm /sdcard/Download/old.zip` | Delete on the phone. No recycle bin |
| `adb shell mkdir -p /sdcard/Themes` | Make a folder on the phone |
| `adb shell df -h /data` | Free space on the phone's main storage |
| `adb shell du -sh /sdcard/DCIM` | Size of one folder |
 
`adb sync` (without `push`) is a developer command that copies a compiled Android build onto the phone's system partitions. It is not a general file sync tool.
 
### Shell Tools
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb shell` | Sit down at the phone's own command prompt. `exit` to leave |
| `adb shell getprop` | Read the phone's full spec sheet |
| `adb shell getprop ro.product.model` | Model name |
| `adb shell getprop ro.product.manufacturer` | Maker |
| `adb shell getprop ro.build.version.release` | Android version |
| `adb shell getprop ro.build.version.security_patch` | Security patch date |
| `adb shell getprop ro.build.fingerprint` | Exact build identity. Needed to match firmware when rooting |
| `adb shell dumpsys battery` | Battery level, health, temperature |
| `adb shell dumpsys meminfo` | Memory use by app |
| `adb shell dumpsys package com.example.app` | Everything the system knows about one app |
| `adb shell dumpsys activity activities` | What is on screen and what is behind it |
| `adb shell dumpsys usagestats` | Usage history by app |
| `adb shell settings list global` | Dump one of the three settings tables (`system`, `secure`, `global`) |
| `adb shell settings get global airplane_mode_on` | Read one setting |
| `adb shell settings put system screen_off_timeout 600000` | Change one setting (milliseconds here) |
| `adb shell input keyevent 26` | Press a button. 26 power, 3 home, 4 back, 24 and 25 volume |
| `adb shell input tap 500 800` | Tap the screen at x, y |
| `adb shell input text hello` | Type text |
| `adb shell screencap -p /sdcard/screen.png` | Take a screenshot, saved on the phone |
| `adb shell screenrecord /sdcard/demo.mp4` | Record the screen. Stops at 3 minutes or Ctrl+C |
| `adb shell wm size` | Screen resolution |
| `adb shell wm density` | Screen density (DPI) |
| `adb shell ip addr show wlan0` | Wi-Fi IP address |
 
### Logs and Diagnostics
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb logcat` | Watch the phone's running diary. Ctrl+C to stop |
| `adb logcat -d > log.txt` | Save the diary so far to a file |
| `adb logcat -c` | Tear out the old pages |
| `adb logcat "*:E"` | Show only errors |
| `adb logcat --pid=1234` | Show one process only |
| `adb bugreport bugreport.zip` | Full diagnostic bundle. Large, takes minutes |
| `adb shell cat /proc/version` | Kernel version |
| `adb shell uptime` | Time since last boot |
 
### Reboot
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb reboot` | Normal restart |
| `adb reboot recovery` | Restart into the maintenance menu |
| `adb reboot bootloader` | Restart into the service door (fastboot) |
| `adb reboot fastboot` | Restart into fastbootd on newer phones |
| `adb reboot sideload` | Restart into recovery, ready to receive an update |
| `adb sideload update.zip` | Feed a signed update package to recovery |
| `adb shell reboot -p` | Power off |
 
### Fastboot
 
| Command | Plain-language meaning |
| :--- | :--- |
| `fastboot devices` | Roll call in bootloader mode |
| `fastboot getvar all` | Read the bootloader's spec sheet |
| `fastboot getvar current-slot` | Which of the two system copies (a or b) is active |
| `fastboot getvar unlocked` | Is the bootloader unlocked |
| `fastboot flashing unlock` | Unlock the bootloader. Erases the phone |
| `fastboot flashing lock` | Lock it again. Erases again. Only with fully stock firmware |
| `fastboot oem unlock` | Older or maker-specific unlock command |
| `fastboot boot image.img` | Start from this image once, without installing it |
| `fastboot flash boot image.img` | Write an image onto the boot partition |
| `fastboot flash init_boot image.img` | Same, for phones that keep the ramdisk in `init_boot` |
| `fastboot flash recovery image.img` | Replace the recovery |
| `fastboot --set-active=a` | Switch the active slot |
| `fastboot erase userdata` | Wipe user data |
| `fastboot reboot` | Leave fastboot, start Android |
| `fastboot reboot bootloader` | Restart back into the bootloader |
| `fastboot reboot recovery` | Go to recovery |
| `fastboot reboot fastboot` | Go to fastbootd |
 
## Worked Example Examining an App
 
Target: Google Chrome, package name `com.android.chrome`. The package name is the handle for every command below. Find any app's package name with `adb shell pm list packages` and a filter:
 
```cmd
adb shell "pm list packages | grep -i chrome"
```
 
| Question | Command | Where to look in the output |
| :--- | :--- | :--- |
| Is it installed | `adb shell pm list packages com.android.chrome` | A line is returned |
| What version | `adb shell dumpsys package com.android.chrome` | `versionName`, `versionCode` |
| Where is it stored | `adb shell pm path com.android.chrome` | `/data/app/...` user-installed or updated, `/system/...` or `/product/...` preinstalled |
| Where did it come from | `adb shell pm list packages -i com.android.chrome` | `installer=com.android.vending` is the Play Store. `null` usually means preinstalled or sideloaded |
| When was it installed | `adb shell dumpsys package com.android.chrome` | `firstInstallTime` |
| When was it last updated | Same | `lastUpdateTime` |
| When was it last used | `adb shell dumpsys usagestats` | `lastTimeUsed` on the package's line. Format varies by Android version |
| What can it do | `adb shell dumpsys package com.android.chrome` | `requested permissions`, `install permissions`, `runtime permissions` with `granted=true` or `false` |
| Is it a system app | Same | `flags=[ SYSTEM ... ]` |
| Is it frozen | Same | `enabled=` under the user section. 0 or 1 enabled, 2 or 3 disabled |
| How much space | `adb shell dumpsys diskstats` | App, data, and cache sizes by package |
| Who made it | Pull the APK, then inspect the signing certificate (below) | Certificate subject and SHA-256 fingerprint |
| What is on screen now | `adb shell dumpsys activity activities` | `topResumedActivity` or `mResumedActivity` |
 
Narrow the long `dumpsys package` output on the phone side:
 
```cmd
adb shell "dumpsys package com.android.chrome | grep -E 'versionName|firstInstallTime|lastUpdateTime|installerPackageName|enabled='"
```
 
Who made it: the package name is a claim, the signing certificate is proof. Copy the installer file off the phone and read its certificate:
 
```cmd
adb shell pm path com.android.chrome
adb pull /data/app/~~XXXX/com.android.chrome-YYYY/base.apk chrome.apk
apksigner verify --print-certs chrome.apk
```
 
`apksigner` ships in the Android SDK Build-Tools, not Platform-Tools. `keytool -printcert -jarfile chrome.apk` from a JDK reads older-style signatures. Apps delivered as split APKs return several paths from `pm path`; `base.apk` holds the manifest and certificate.
 
| Goal | Command | Reversible |
| :--- | :--- | :--- |
| Stop it now | `adb shell am force-stop com.android.chrome` | Starts again when opened |
| Reset it | `adb shell pm clear com.android.chrome` | No. Data is gone |
| Freeze it | `adb shell pm disable-user --user 0 com.android.chrome` | `adb shell pm enable com.android.chrome` |
| Remove a user-installed app | `adb uninstall com.android.chrome` | Reinstall |
| Remove a preinstalled app for the user | `adb shell pm uninstall --user 0 com.android.chrome` | `adb shell cmd package install-existing com.android.chrome`, or a factory reset |
| Remove but keep data | `adb shell pm uninstall -k --user 0 com.android.chrome` | Same as above |
 
Preinstalled apps live on a read-only partition and cannot be deleted without root. The `--user 0` form hides the app from the main user and frees its data, but the installer file stays. Removing the wrong system package can cause boot loops, so freeze first, test, then remove.
 
## Backups
 
### Backup Methods
 
| Method | Covers | Limits |
| :--- | :--- | :--- |
| `adb pull /sdcard ./phone-sdcard` | Everything in shared storage: photos, downloads, music, documents | No app private data, no SMS, no settings |
| `adb backup -apk -shared -all -f phone.ab` | App installers, shared storage, and app data for apps that allow it | Deprecated. On Android 12 and later, most current apps are excluded from the data portion. Do not rely on it alone |
| `adb backup -f chrome.ab com.android.chrome` | One app | Same limit |
| `adb restore phone.ab` | Restores an `.ab` file | Same limit |
| Pull installer files | `adb shell pm path <package>` then `adb pull` | Installers only, no data |
| Google backup | Settings > System > Backup | App data only where the developer supports it |
| Maker tools | Samsung Smart Switch (PC, SD card, or phone to phone) | Maker-specific |
| App-level export | SMS Backup and Restore, WhatsApp chat backup, authenticator export | One app each |
| Recovery image backup | TWRP or similar | Needs an unlocked bootloader |
| App data with root | Copy `/data/data/<package>` | Needs root |
 
`adb backup` options:
 
| Option | Meaning | Default |
| :--- | :--- | :--- |
| `-f file.ab` | Output file name | `backup.ab` in the current folder |
| `-apk` / `-noapk` | Include the installer files | Not included |
| `-shared` / `-noshared` | Include shared storage (`/sdcard`) | Not included |
| `-all` | Every app that permits backup | Off |
| `-system` / `-nosystem` | Include system apps when `-all` is used | Included |
| `-obb` / `-noobb` | Include large game expansion files | Not included |
 
### Passwords
 
The phone shows a confirmation screen when `adb backup` starts. The encryption password field on that screen is **optional**. Leave it blank for an unencrypted backup.
 
- Unencrypted backups can be opened and inspected with ordinary tools (see below).
- An encrypted backup with a forgotten password cannot be restored or opened. There is no recovery path.
- For personal use, an unencrypted backup stored somewhere already protected (an encrypted drive, a locked cabinet) avoids the lost-password failure.
- If a password is used, record it in a password manager before trusting the backup.
- Some phones with a device-encryption password set may insist on one.
### File Extensions Can Mislead
 
Many Android files are ordinary archives under a different extension. Rename a copy, or open it directly in 7-Zip, to look inside.
 
| Extension | Really is | How to open |
| :--- | :--- | :--- |
| `.apk` | Zip archive | Rename to `.zip`, or open in 7-Zip |
| `.jar` | Zip archive | Same |
| `.aab` | Zip archive (app bundle for the Play Store) | Same |
| `.apks`, `.xapk`, `.apkm` | Zip holding several `.apk` files | Same |
| OTA `update.zip` | Zip, usually holding `payload.bin` | Zip tool, then a payload extractor for the partition images |
| `.ab` | 24-byte text header, then a zlib-compressed **tar** archive (when not encrypted) | Not a zip. Strip the header and inflate, or use Android Backup Extractor (`abe.jar`) to convert to `.tar` |
| `.tar.md5` (Samsung firmware) | Tar archive with a checksum appended | Rename to `.tar` |
| `.img` | Raw or sparse partition image | 7-Zip opens some. `simg2img` converts sparse images |
| `.novabackup` and similar launcher backups | Usually a zip | Rename to `.zip` |
| `.vcf` | Plain text contact cards | Any text editor |
 
Convert an unencrypted `.ab` to a tar on macOS or Linux:
 
```bash
( printf "\x1f\x8b\x08\x00\x00\x00\x00\x00"; tail -c +25 phone.ab ) | tar -xzf -
```
 
Always work on a copy. Repacking an edited APK breaks its signature, and the phone will refuse it.
 
### Inside an APK
 
A small example, opened as a zip:
 
```text
ExampleApp.apk
├── AndroidManifest.xml
├── classes.dex
├── resources.arsc
├── res/
│   ├── drawable/icon.png
│   └── layout/main.xml
├── lib/
│   └── arm64-v8a/libnative.so
├── assets/
│   └── help.html
└── META-INF/
    ├── MANIFEST.MF
    ├── CERT.SF
    └── CERT.RSA
```
 
| Item | What it is |
| :--- | :--- |
| `AndroidManifest.xml` | The app's identity card: package name, version, permissions requested, screens and services declared. Stored as binary XML, so it needs a tool such as `aapt2 dump` or apktool to read |
| `classes.dex` | The compiled program code. Larger apps have `classes2.dex`, `classes3.dex`, and so on |
| `resources.arsc` | Lookup table matching resource names to files and text, including translations |
| `res/` | Images, screen layouts, and other resources referenced by the table |
| `lib/` | Native code libraries, one subfolder per processor type |
| `assets/` | Raw files the app reads as-is: web pages, fonts, databases, game data |
| `META-INF/` | Signature files. `MANIFEST.MF` lists a hash of every file, `CERT.SF` signs that list, `CERT.RSA` holds the developer's certificate. Newer signature schemes also store a signing block outside this folder |
 
### Inside an adb Backup
 
After converting `.ab` to `.tar` and unpacking:
 
```text
phone-backup/
├── apps/
│   └── com.example.notes/
│       ├── _manifest
│       ├── a/
│       │   └── base.apk
│       ├── db/
│       │   └── notes.db
│       ├── sp/
│       │   └── settings.xml
│       └── f/
│           └── attachment1.jpg
└── shared/
    └── 0/
        ├── DCIM/
        └── Download/
```
 
| Item | What it is |
| :--- | :--- |
| `apps/<package>/` | One folder per backed-up app |
| `_manifest` | Small text file: package name, version, signature, used to validate a restore |
| `a/` | The installer file, present when `-apk` was used |
| `db/` | The app's SQLite databases. Open with DB Browser for SQLite |
| `sp/` | Shared preferences: the app's settings as XML text |
| `f/` | The app's private files |
| `r/`, `ef/` | Other app data roots and app files on external storage |
| `shared/0/` | Shared storage for the main user, present when `-shared` was used |
 
## Moving Files
 
### Transfer Methods
 
| Method | Example | Best for |
| :--- | :--- | :--- |
| ADB push | `adb push report.pdf /sdcard/Documents/` | Single files or folders to the phone |
| ADB pull | `adb pull /sdcard/DCIM ./phone-photos` | Single files or folders from the phone |
| ADB push, newer only | `adb push --sync Music /sdcard/` | Repeat runs without recopying everything |
| Shell copy on the phone | `adb shell cp /sdcard/Download/tone.mp3 /sdcard/Ringtones/` | Rearranging files already on the phone |
| Stream without a temp file | `adb exec-out screencap -p > screen.png` | Screenshots straight to the computer. Use `cmd.exe`; Windows PowerShell 5 corrupts binary redirects |
| MTP (File Explorer) | Phone set to File transfer | Clients, no ADB needed. Slow with many small files |
| Quick Share, cloud, SD card | | Non-technical handoffs |
| scrcpy | Screen mirror with drag and drop | Visual work. Uses ADB underneath |
 
Names with spaces need quotes: `adb push "My File.pdf" "/sdcard/Documents/My File.pdf"`
 
### Where Media Goes
 
`/sdcard` is a shortcut to `/storage/emulated/0`, the main user's shared storage.
 
| Content | Phone folder | Shows up in |
| :--- | :--- | :--- |
| Camera photos and video | `/sdcard/DCIM/Camera` | Gallery, Google Photos |
| Other pictures, screenshots | `/sdcard/Pictures` | Gallery |
| Video files | `/sdcard/Movies` | Gallery, video players |
| Music | `/sdcard/Music` | Music players |
| Ringtones | `/sdcard/Ringtones` | Settings > Sound > Phone ringtone |
| Notification sounds | `/sdcard/Notifications` | Notification sound picker |
| Alarm sounds | `/sdcard/Alarms` | Clock app alarm sound picker |
| Podcasts, audiobooks | `/sdcard/Podcasts`, `/sdcard/Audiobooks` | Matching apps |
| Documents, e-books | `/sdcard/Documents` or `/sdcard/Download` | Files app, e-reader apps (import from there) |
| Downloads | `/sdcard/Download` | Files app |
 
Examples:
 
```cmd
adb push vacation.jpg /sdcard/Pictures/
adb push album /sdcard/Music/
adb push mytone.mp3 /sdcard/Ringtones/
adb push wakeup.ogg /sdcard/Alarms/
adb push manual.pdf /sdcard/Documents/
adb push novel.epub /sdcard/Download/
adb pull /sdcard/DCIM ./phone-photos
```
 
Files pushed by ADB may not appear in apps until the media index catches up. Ask for a scan of one file, or restart the phone:
 
```cmd
adb shell am broadcast -a android.intent.action.MEDIA_SCANNER_SCAN_FILE -d file:///sdcard/Music/song.mp3
```
 
### Hiding Folders with nomedia
 
An empty file named `.nomedia` tells Android's media scanner to skip that folder and everything under it. Use it for folders of themes, icon packs, app artwork, or scans that should not appear in the gallery or music player.
 
| Task | Command |
| :--- | :--- |
| Hide a folder | `adb shell touch /sdcard/Themes/.nomedia` |
| Check for one | `adb shell ls -la /sdcard/Themes` |
| Find them all | `adb shell find /sdcard -name .nomedia` |
| Unhide | `adb shell rm /sdcard/Themes/.nomedia` |
 
Changes take effect after the next media scan or a restart.
 
Do **not** put `.nomedia` in `/sdcard/Ringtones`, `/sdcard/Alarms`, or `/sdcard/Notifications`. The sound pickers read the same media index, so hiding the folder removes the sounds from the pickers. Files in those folders are already tagged as ringtones, alarms, or notifications, and most music players skip them for that reason.
 
## File System Map
 
```text
/
├── sdcard -> /storage/emulated/0     shared storage (read, write)
│   ├── DCIM, Pictures, Movies, Music
│   ├── Download, Documents
│   ├── Ringtones, Alarms, Notifications
│   └── Android/
│       ├── data/<package>/           app files on shared storage
│       ├── media/<package>/          app media
│       └── obb/<package>/            game expansion files
├── storage/XXXX-XXXX                 removable SD card, if fitted
├── data/
│   ├── local/tmp                     scratch space for ADB (read, write)
│   ├── app/                          installed app packages
│   ├── data/<package>/               app private data (root only)
│   ├── media/0                       real location of shared storage
│   └── misc/                         system state, Wi-Fi, ADB keys (root only)
├── system/                           Android itself (read-only)
├── vendor/, product/                 maker and chipset files (read-only)
├── proc/, sys/                       live kernel information
└── cache/, metadata/                 system use
```
 
| Path | Without root | Notes |
| :--- | :--- | :--- |
| `/sdcard` and media folders | Read and write | Where nearly all ADB file work happens |
| `/sdcard/Android/data/<package>` | Usually readable through ADB | File manager apps on the phone are blocked on Android 11 and later. Behavior varies by version and maker |
| `/storage/XXXX-XXXX` | Read, usually write | The ID is the card's volume serial |
| `/data/local/tmp` | Read and write | Good staging area. Files here can be made executable |
| `/data/app/.../base.apk` | Readable when the exact path is known | Get the path from `pm path`. The folder itself cannot be listed |
| `/data/data/<package>` | Permission denied | App databases, settings, logins. Launcher layouts live here too |
| `/data/misc`, `/data/system` | Permission denied | Saved Wi-Fi networks, accounts, lock settings |
| `/system`, `/vendor`, `/product` | Read-only | Stays read-only on modern phones even with root, without extra steps |
| `/proc`, `/sys` | Partly readable | `cat /proc/meminfo`, `cat /proc/cpuinfo` |
 
`adb shell run-as <package>` enters an app's private folder without root, but only for apps built as debuggable, which retail apps are not.
 
## Property and Settings Files
 
Android keeps much of its identity and configuration in plain text files. The best known is `build.prop`, but it is one of several property files, and many other settings live in XML, `.conf`, `.rc`, and `.ini` files.
 
### Property Files
 
Property files are plain text, one `name=value` per line, with `#` for comments. At startup Android reads all of them in a fixed order and merges the result into one in-memory table, which is what `getprop` shows.
 
| File | Holds | Readable without root |
| :--- | :--- | :--- |
| `/system/build.prop` | Android version, build ID, build date, core system defaults | Often no on recent versions |
| `/system_ext/etc/build.prop` | Properties for system extensions | Varies |
| `/product/etc/build.prop` (older: `/product/build.prop`) | Model name, brand, product-specific settings | Varies |
| `/vendor/build.prop` | Chipset and hardware settings from the maker | Varies |
| `/vendor/default.prop` | Vendor defaults | Varies |
| `/odm/etc/build.prop` | Settings from the device manufacturer layer | Varies |
| `/vendor_dlkm/etc/build.prop`, `/odm_dlkm/etc/build.prop` | Kernel module partitions, newer phones | Varies |
| `/system/etc/prop.default` (older: `/default.prop`, `/prop.default`) | Early-boot defaults such as `ro.secure` and `ro.debuggable` | Varies |
| `/data/local.prop` | Local overrides. Only honored on debuggable (engineering) builds | No |
| `/data/property/persistent_properties` | Saved `persist.*` values. A binary file on Android 9 and later; a folder of one small text file per property before that | No |
| `/proc/cmdline`, `/proc/bootconfig` | Values handed over by the bootloader, which become `ro.boot.*` properties | No on recent versions |
| `/data/adb/modules/<id>/system.prop` | Property overrides supplied by a Magisk module (rooted phones) | No |
| `/data/adb/modules/<id>/module.prop` | A Magisk module's own name, version, and author | No |
 
Because the files are split across partitions and often unreadable, use `getprop` to see the merged result instead of opening the files.
 
Property name prefixes:
 
| Prefix | Meaning |
| :--- | :--- |
| `ro.` | Read-only. Set once at boot, cannot be changed until the next boot |
| `ro.boot.` | Passed in by the bootloader |
| `ro.build.`, `ro.product.` | Build and model identity |
| `persist.` | Survives restarts. Stored under `/data/property` |
| `sys.` | Live system state |
| `init.svc.` | State of each system service: `running`, `stopped` |
| `gsm.`, `ril.` | Mobile radio and SIM information |
| `debug.`, `log.tag.` | Debugging switches. Settable from the ADB shell |
| `vendor.` | Maker and chipset additions |
 
### Reading and Setting Properties
 
| Command | Plain-language meaning |
| :--- | :--- |
| `adb shell getprop` | Print the whole merged table |
| `adb shell getprop ro.product.model` | Read one value |
| `adb shell getprop -T` | Show each property's data type |
| `adb shell getprop -Z` | Show each property's security label |
| `adb shell setprop debug.example 1` | Set a value. Without root, only a few prefixes such as `debug.` and `log.tag.` are allowed |
| `adb shell cat /vendor/build.prop` | Read a file directly, where permitted |
| `resetprop ro.example value` | Magisk's tool for changing even read-only properties (root) |
 
Filter on the phone side, and save a full copy for the client record:
 
```cmd
adb shell "getprop | grep -i -E 'boot|slot|locked'"
adb shell getprop > phone-properties.txt
```
 
Editing `build.prop` directly is rarely possible on current phones, even with root: the system partitions are read-only and verified at boot. Rooted phones change properties without touching the file, through a Magisk module's `system.prop` or `resetprop`. A bad property edit can cause a boot loop, and changing identity properties can break updates and app integrity checks.
 
### Useful Properties
 
| Property | Tells you |
| :--- | :--- |
| `ro.product.manufacturer`, `ro.product.brand` | Maker and brand |
| `ro.product.model` | Marketing model number |
| `ro.product.device` | Codename. Used to find matching firmware and custom recoveries |
| `ro.build.version.release` | Android version |
| `ro.build.version.sdk` | API level |
| `ro.build.version.security_patch` | Security patch date |
| `ro.build.id`, `ro.build.display.id` | Build number as shown in Settings |
| `ro.build.fingerprint` | Full build identity string |
| `ro.build.date` | When the firmware was built |
| `ro.build.type` | `user` (retail), `userdebug`, or `eng` |
| `ro.build.tags` | `release-keys` for official firmware, `test-keys` for custom |
| `ro.debuggable` | 1 on engineering builds |
| `ro.product.first_api_level` | Android version the phone shipped with |
| `ro.product.cpu.abilist` | Processor types supported: `arm64-v8a`, `armeabi-v7a` |
| `ro.hardware`, `ro.board.platform` | Chipset family |
| `ro.serialno` | Serial number |
| `ro.boot.slot_suffix` | Active slot, `_a` or `_b` |
| `ro.build.ab_update` | `true` on A/B slot phones |
| `ro.boot.verifiedbootstate` | `green` locked and verified, `yellow` custom key, `orange` unlocked, `red` failed |
| `ro.boot.flash.locked` | 1 locked bootloader, 0 unlocked |
| `ro.crypto.state` | `encrypted` or `unencrypted` |
| `ro.csc.sales_code` | Samsung region and carrier code |
| `persist.sys.timezone` | Time zone |
| `persist.sys.locale` | Language and region |
| `gsm.sim.operator.alpha` | Carrier name on the SIM |
| `gsm.operator.alpha` | Network currently registered on |
| `sys.boot_completed` | 1 once startup has finished. Useful in scripts |
 
### Other Text Settings Files
 
| File | Format | Holds | Without root |
| :--- | :--- | :--- | :--- |
| `/data/data/<package>/shared_prefs/*.xml` | XML | Each app's own settings | No |
| `/data/system/users/0/settings_system.xml`, `settings_secure.xml`, `settings_global.xml` | XML | The three system settings tables | No. Read with `adb shell settings list` instead |
| `/data/system/packages.xml` | XML | Every installed package, its permissions and signatures | No. Read with `dumpsys package` |
| `/data/system/packages.list` | Text | One line per package with its user ID and data folder | No |
| `/data/system/users/0/package-restrictions.xml` | XML | Which apps are disabled or hidden for the user | No |
| `/data/system/device_policies.xml` | XML | Device administrator and MDM policy | No |
| `/data/misc/apexdata/com.android.wifi/WifiConfigStore.xml` | XML | Saved Wi-Fi networks and passwords, Android 11 and later | No |
| `/data/misc/wifi/WifiConfigStore.xml` | XML | Same, Android 8 to 10 | No |
| `/data/misc/wifi/wpa_supplicant.conf` | Conf | Same, Android 7 and earlier | No |
| `/data/misc/bluedroid/bt_config.conf` | INI style | Paired Bluetooth devices and link keys | No |
| `/data/misc/adb/adb_keys` | Text | Public keys of computers trusted for USB debugging | No |
| `/system/etc/hosts` | Text | Hosts file, same idea as on Windows | Read |
| `/system/etc/permissions/*.xml`, `/system/etc/sysconfig/*.xml` | XML | Hardware features declared, and permission allowlists for preinstalled apps | Read |
| `/product/etc/apns-conf.xml` (or `/system/etc/`) | XML | Carrier APN list | Read |
| `/system/etc/fonts.xml` | XML | Font families and fallbacks | Read |
| `/vendor/etc/gps.conf` (or `/system/etc/`) | Conf | GPS assistance and time servers | Varies |
| `/vendor/etc/audio_policy_configuration.xml`, `mixer_paths*.xml` | XML | Audio routing and volume paths | Varies |
| `/vendor/etc/media_codecs*.xml` | XML | Supported audio and video codecs | Varies |
| `/vendor/etc/wifi/*.ini`, `*.conf` | INI, Conf | Wi-Fi chipset tuning | Varies |
| `/vendor/etc/fstab.*` | Text table | Which partitions mount where at boot | Varies |
| `/system/etc/init/*.rc`, `/vendor/etc/init/*.rc` | Init script | What starts at boot, and which properties trigger actions | Read, varies |
| `/system/usr/keylayout/*.kl`, `/system/usr/keychars/*.kcm`, `/system/usr/idc/*.idc` | Text | Button, keyboard, and input device mappings | Read |
| `/system/etc/selinux/*_contexts`, `*.cil` | Text | Security policy labels | Read, varies |
| `/vendor/etc/vintf/manifest.xml` | XML | Hardware interfaces the vendor provides | Varies |
| `/system/etc/security/cacerts/` (Android 14 and later: `/apex/com.android.conscrypt/cacerts/`) | PEM text | Trusted root certificates | Read |
| `META-INF/com/android/metadata` inside an OTA zip | `name=value` | Which build the update is from and for | On the computer |
 
On Android 12 and later, many of the XML files under `/data/system` are stored as **binary XML** (they begin with the letters `ABX`) and look like gibberish in a text editor. The phone includes converters: `abx2xml input output` and `xml2abx input output`, run from the shell. Reading the originals still needs root.
 
Not everything is text. Contacts, messages, call log, and many app stores are SQLite databases (`.db`), opened with DB Browser for SQLite after extraction.
 
### Formats by Extension
 
| Extension | Format | Example |
| :--- | :--- | :--- |
| `.prop` | `name=value` lines | `build.prop`, `default.prop`, `module.prop` |
| `.properties` | `name=value` lines | `source.properties` in the Platform-Tools folder on the computer |
| `.xml` | XML, or binary XML on newer versions | Settings tables, shared preferences, APN list |
| `.conf` | Free-form or `name=value` | `gps.conf`, `wpa_supplicant.conf`, `bt_config.conf` |
| `.ini` | Sections and `name=value` | Wi-Fi chipset files |
| `.rc` | Android init language | `init.rc` and service definitions |
| `.json` | JSON | Power and thermal profiles under `/vendor/etc` |
| `.kl`, `.kcm`, `.idc` | Text maps | Key layouts |
| `.cil`, `*_contexts` | Text | SELinux policy |
| `fstab.*` | Text table | Mount table |
| `.db` | SQLite database, not text | `contacts2.db`, `mmssms.db` |
 
## Boot Modes
 
| Mode | What it is | Enter by command | Enter by buttons (typical) | Computer tool | Can do |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Normal | Android | `adb reboot` | Power | `adb` | Everything in this page above |
| Safe mode | Android with only factory apps loaded | | Hold Power, long-press **Power off**, confirm. Or hold Volume Down during the boot logo | `adb` | Prove whether an added app causes a fault |
| Recovery | Small separate maintenance system | `adb reboot recovery` | Power + Volume Up from off. On many phones, pick it from the bootloader menu | `adb` (limited) | Factory reset, wipe cache, apply updates |
| Sideload | Recovery waiting for an update file | `adb reboot sideload` | Recovery > Apply update from ADB | `adb sideload` | Install a signed OTA package |
| Bootloader (fastboot) | Pre-boot service mode | `adb reboot bootloader` | Power + Volume Down from off | `fastboot` | Unlock, flash partitions, boot a test image |
| Fastbootd | Fastboot running inside recovery | `adb reboot fastboot` or `fastboot reboot fastboot` | Bootloader or recovery menu | `fastboot` | Flash `system`, `vendor`, `product` on phones with dynamic partitions |
| Download (Odin) mode | Samsung's flashing mode | `adb reboot download` | From off, hold Volume Up + Volume Down and plug in USB. Older models: Volume Down + Home + Power | Odin (Windows), Heimdall | Flash Samsung firmware. Shows lock and Knox status |
| EDL (Qualcomm 9008) | Chip-level emergency loader | `adb reboot edl` where allowed | Test points or a special cable | QFIL, maker tools | Revive a phone that will not boot. Usually needs maker-signed files |
| BROM, Preloader (MediaTek) | Chip-level loader | | Hold a volume key while plugging in, from off | SP Flash Tool | Same idea for MediaTek chips |
 
Button combinations differ by maker and model; check the maker's documentation. The most common error on this subject is using the wrong computer tool for the mode: `adb` does not see a phone in bootloader mode, `fastboot` does not see a running phone, and neither sees a Samsung in Download mode.
 
Custom recoveries (TWRP, OrangeFox) replace the stock recovery and add full-image backups, file management, and installing unsigned zips. They need an unlocked bootloader.
 
## Rooting Walkthroughs
 
These explain what published rooting instructions are doing, so errors can be understood. They are not a procedure for a specific model. Use the maker's and the tool's current documentation for the exact phone and build.
 
Before any of it:
 
- Unlocking the bootloader erases the phone. Back up first.
- It may void the warranty. On Samsung it permanently trips Knox, disabling Samsung Pay and Secure Folder for good.
- Banking, payment, and some game apps may refuse to run on an unlocked or rooted phone.
- Carrier-sold phones often cannot be unlocked at all (the **OEM unlocking** switch is missing or grayed out).
- Automatic system updates stop working normally on a rooted phone.
### Common Sequence
 
Most current guides follow the same three stages: unlock the bootloader, patch a copy of the phone's boot image with Magisk, then write the patched image back.
 
| Step | Command or action | What it does | If it fails |
| :--- | :--- | :--- | :--- |
| 1 | Developer options > **OEM unlocking** on | Gives the bootloader permission to be unlocked | Grayed out: carrier lock, or the phone needs to be online for a period first |
| 2 | `adb reboot bootloader` | Restarts into the service door, before Android loads | Nothing happens: USB debugging is off or not authorized |
| 3 | `fastboot devices` | Confirms the computer can reach the bootloader | Empty list: fastboot driver missing on Windows, or a bad cable. Not a command problem |
| 4 | `fastboot flashing unlock` | Asks the bootloader to stop enforcing signed-only software. Confirm on the phone with the volume and power keys. Phone is wiped | `not allowed`: step 1 was skipped |
| 5 | Obtain the stock firmware for the **exact** build | The boot image must match what is installed. Check with `adb shell getprop ro.build.fingerprint` | A mismatched image causes a boot loop |
| 6 | Extract `boot.img` or `init_boot.img` and `adb push` it to `/sdcard/Download/` | Puts the stock image where the Magisk app can read it | |
| 7 | Magisk app > Install > Select and Patch a File | Magisk copies the image and adds its own startup code to the copy. Output is `magisk_patched-XXXXX.img` in Download | Patch the image on the same phone it will be flashed to |
| 8 | `adb pull /sdcard/Download/magisk_patched-XXXXX.img` | Brings the patched image back to the computer | |
| 9 | `fastboot boot magisk_patched-XXXXX.img` | Optional test: starts from the patched image once without installing it. Nothing permanent changes | Not supported by every bootloader |
| 10 | `fastboot flash boot magisk_patched-XXXXX.img` | Writes the patched image over the boot partition. Use `init_boot` in place of `boot` on phones that have that partition | `partition not found`: wrong partition name for this phone |
| 11 | `fastboot reboot` | Starts Android with the patched image | Boot loop: flash the stock image back with the same command |
 
Keep the untouched stock image. Flashing it back with the step 10 command removes root.
 
### Brand Differences
 
| Brand | Unlock | Flash tool | Notes |
| :--- | :--- | :--- | :--- |
| Google Pixel | `fastboot flashing unlock` | `fastboot` | Factory images on Google's site. Recent models with Android 13 and later patch `init_boot`. PixelFlasher automates the steps |
| Samsung | OEM unlocking, then a long Volume Up press in Download mode | Odin, not fastboot | Magisk patches the firmware's `AP` tar file, flashed back through Odin's AP slot. US Snapdragon models generally cannot be unlocked |
| Xiaomi, Redmi, POCO | Mi Unlock tool with a Mi account and an enforced waiting period | `fastboot` | Policy varies by region and has tightened over time |
| Motorola | `fastboot oem get_unlock_data`, request a code on Motorola's site, then `fastboot oem unlock CODE` | `fastboot` | Not all models are eligible |
| OnePlus | `fastboot flashing unlock` (older: `fastboot oem unlock`) | `fastboot` | Firmware often ships as `payload.bin`, which needs an extractor to get `boot.img` |
| Sony | Unlock code from Sony's developer site, `fastboot oem unlock 0xCODE` | `fastboot` | Unlocking can degrade camera processing on some models |
| A/B slot phones (many brands) | | `fastboot` | Two copies of each partition. `fastboot flash boot_a file.img` and `boot_b`, or `fastboot flash --slot=all boot file.img` |
| MediaTek phones | Varies | `fastboot` or SP Flash Tool | Some lock the boot partition after startup |
 
Other pieces that appear in guides:
 
| Command or term | Meaning |
| :--- | :--- |
| `fastboot flash vbmeta --disable-verity --disable-verification vbmeta.img` | Rewrites the table that verified boot uses to check other partitions, with checking turned off. Only for phones that need it. May wipe data |
| `fastboot flash recovery twrp.img` | Replaces the stock recovery with a custom one. Older method |
| `fastboot boot twrp.img` | Runs a custom recovery once without installing it |
| `adb sideload Magisk.zip` | Installs Magisk from inside a custom recovery. Legacy method |
| Magisk > Direct Install | Used after a temporary boot (step 9) to make root permanent from inside Android |
| KernelSU, APatch | Newer root methods that work at the kernel level, with their own manager apps |
| Play Integrity (formerly SafetyNet) | Google's check that apps use to detect unlocked or modified phones |
| `fastboot flashing lock` | Re-locks the bootloader. Doing this with any modified partition can leave the phone unbootable. Restore full stock firmware first |
 
### Error Messages
 
| Message | Likely cause | Direction |
| :--- | :--- | :--- |
| `waiting for any device` | Fastboot cannot see the phone | Driver or cable. Check Device Manager for an unknown device |
| `FAILED (remote: 'flashing unlock is not allowed')` | OEM unlocking is off | Step 1 |
| `FAILED (remote: 'partition does not exist')` or `not found` | Wrong partition name | `boot` versus `init_boot`, or a slot suffix is needed |
| `FAILED (remote: 'Flashing is not allowed in Lock State')` | Bootloader is still locked | Unlock first |
| `Your device is corrupt` on startup | Verified boot rejected a partition | Wrong or mismatched image. Some phones need the `vbmeta` step |
| Orange or yellow warning screen at every boot | Normal for an unlocked bootloader | Informational |
| Boot loop after flashing | Patched image does not match the installed build | Flash the stock boot image back |
| `error: device unauthorized` | ADB key not accepted on the phone | Unlock the screen and accept the prompt |
| `adb: sideload connection failed` | Phone is not in sideload mode, or an old `adb` | Recovery > Apply update from ADB. Update Platform-Tools |
| Odin `FAIL! (Auth)` | Firmware does not match the model or region, or the bootloader is locked | Match the firmware to the exact model code |
 
## Migration Guide
 
Things a technician can do when a client moves to, from, or between Android phones.
 
### Before Starting
 
- Confirm the client knows their Google account password, and their Samsung account password if they have one.
- Keep the old phone intact and powered until the new one has been checked. Do not factory reset it the same day.
- Compare Android versions. A Google backup from a newer version generally will not restore onto an older one.
- Confirm with the carrier how the SIM or eSIM moves. eSIM transfer is carrier-specific.
- Update both phones and charge them.
- Record what is installed, as a checklist that survives a failed restore:
```cmd
adb shell pm list packages -3 > installed-apps.txt
adb shell getprop ro.product.model
adb shell getprop ro.build.version.release
```
 
### What to Move
 
| Item | How it moves | Watch for |
| :--- | :--- | :--- |
| Contacts | Google account sync, or Contacts app > Export to `.vcf` and import | Contacts saved as "Phone" or "SIM" do not sync. Check the storage account of each group |
| Calendar | Account sync | Local-only calendars |
| Photos and video | Google Photos backup, or `adb pull /sdcard/DCIM` | Also `Pictures`, `Movies`, `Download`, and app folders such as WhatsApp media. Verify counts before wiping |
| Text messages, call log | Google backup (partial), SMS Backup and Restore, or the maker's tool | MMS pictures and group threads are the usual losses |
| WhatsApp | In-app chat backup to Google Drive, restored at first sign-in | Must be done inside WhatsApp. Same phone number required |
| Signal | In-app transfer or its own encrypted backup file with a passphrase | No cloud copy by default |
| Authenticator apps (2FA) | Each app's own export, transfer, or cloud sync | The highest-risk item. Move these before wiping the old phone, or the client is locked out of accounts |
| Passwords | Google Password Manager sync or the client's password manager | Sign in and confirm on the new phone |
| Apps | Reinstalled by Google restore or the setup cable transfer | Paid apps follow the Google account. Sideloaded apps do not come across |
| App data | Only where the developer supports backup | Games and note apps vary. Check each important app for its own sync or export |
| Banking and payment apps | Reinstall and re-enroll | Device re-registration, often with a code sent by text |
| Google Wallet cards | Re-add each card | Bank verification each time |
| Music, documents, e-books | `adb pull` and `adb push`, MTP, or cloud | See [Moving Files](#moving-files) |
| Ringtones, alarms, notification sounds | Copy the `Ringtones`, `Alarms`, and `Notifications` folders | Reassign them in Settings afterward |
| Wi-Fi networks | Google backup or the maker's tool | |
| Bluetooth pairings | Re-pair each device | Cars, earbuds, hearing aids |
| Smartwatch | Usually requires a watch reset and re-pair | Back up the watch in its companion app first |
| Voicemail | Carrier feature | Saved voicemails may not move. Export important ones as audio |
| Alarms, wallpaper, settings | Google backup or the maker's tool | Partial |
| Home screen layout | See below | |
| Accessibility settings | Manual | Font size, display size, hearing options. Note them before the move |
| Emergency information | Manual | Medical info and emergency contacts on the lock screen |
| SD card | Move the card | Cards formatted as internal (adoptable) storage are encrypted to the old phone and unreadable elsewhere |
 
### Transfer Tools
 
| Tool | Direction | Notes |
| :--- | :--- | :--- |
| Android setup cable or Wi-Fi copy | Android to Android, iPhone to Android | Offered during first-time setup. Most complete when both phones are present |
| Google backup | Android to Android | Settings > System > Backup. Restored at setup sign-in |
| Samsung Smart Switch | To Samsung | Phone to phone, or via PC and SD card. Most complete Samsung to Samsung |
| Maker tools | To that maker | OnePlus Clone Phone, Xiaomi Mi Mover, and similar |
| SMS Backup and Restore | Any Android to any Android | Messages and call log as XML |
| ADB push and pull | Any | Files only. Fast and scriptable |
| Move to iOS (Apple) | Android to iPhone | Run during iPhone setup |
 
### Home Screen Layout
 
The layout belongs to the launcher app, so the answer depends on which launcher is in use and whether the new phone runs the same one.
 
| Situation | Method | Result |
| :--- | :--- | :--- |
| Samsung to Samsung | Smart Switch with **Home screen** selected | Icons, folders, and wallpaper carry over. Widgets often need re-adding |
| Samsung, same phone or later restore | Good Lock > Home Up > Backup and Restore | Saves layout files on a schedule |
| Pixel to Pixel | Google backup or cable copy at setup | Layout usually restored. No manual backup option in Pixel Launcher |
| Other brand to same brand | Maker's clone tool | Varies |
| Different brands | Third-party launcher with its own backup (Nova Launcher, Lawnchair, Action Launcher, and others) | Portable backup file. The launcher must be installed and set up on the old phone first; it cannot import a Samsung layout |
| Anything else | Screenshots of every page, the dock, and each open folder | Manual rebuild |
 
- Screenshot every page regardless. It is the only method that always works.
- Set the same grid size (for example 5x5) on the new phone before restoring, or icons shift.
- Apps not yet installed leave gaps or gray icons until they finish downloading.
- The stock launcher's layout database is under `/data/data/<launcher package>/`, which ADB cannot read without root.
- Capture screenshots over ADB:
```cmd
adb shell screencap -p /sdcard/home1.png
adb pull /sdcard/home1.png
```
 
### iPhone Moves
 
| Direction | Steps | Watch for |
| :--- | :--- | :--- |
| iPhone to Android | Use the cable copy during Android setup, or Google's Switch to Android app | Turn off iMessage and FaceTime on the iPhone **before** moving the SIM, or texts from iPhone users go missing. Apple has a web page to deregister a number afterward |
| iPhone to Android | WhatsApp: transfer by cable during setup | Must be done at first setup |
| Android to iPhone | Apple's Move to iOS app during iPhone setup | Apps do not transfer. Purchases do not cross stores |
| Either | Photos through Google Photos or iCloud; contacts and calendar through the Google account | iCloud-only contacts need exporting |
 
## Troubleshooting
 
| Symptom | Cause | Fix |
| :--- | :--- | :--- |
| `adb` is not recognized | Not on PATH | Use the full path, or add the PATH entry and open a new terminal |
| `adb devices` list is empty | Cable, driver, or USB debugging off | Try another cable and port. Check Device Manager. Re-enable USB debugging |
| `unauthorized` | Prompt not accepted | Unlock the phone, accept. If no prompt: Revoke USB debugging authorizations, replug |
| `offline` | Stalled connection | `adb kill-server`, replug |
| `more than one device/emulator` | Several targets | Add `-s SERIAL` |
| `adb server version (NN) doesn't match this client (NN)` | Two different `adb` copies | `where adb`, remove the extra. Phone-suite software often bundles its own |
| `cannot connect to daemon` | Port 5037 in use | `netstat -ano` and look for 5037, close the other program |
| `Permission denied` on a path | Protected area | See [File System Map](#file-system-map) |
| `INSTALL_FAILED_UPDATE_INCOMPATIBLE` | Signature differs from the installed copy | Uninstall first (data is lost) |
| `INSTALL_FAILED_VERSION_DOWNGRADE` | Older version than installed | `adb install -d`, or uninstall first |
| `INSTALL_FAILED_INSUFFICIENT_STORAGE` | Phone is full | `adb shell df -h /data` |
| `INSTALL_FAILED_USER_RESTRICTED` | Maker blocks USB installs | Xiaomi and others: enable **Install via USB** in Developer options |
| Pushed files not visible in apps | Media index not updated | Scan broadcast or restart |
| Wireless connection drops | Phone sleeping or changed network | Reconnect. Wireless debugging ports change each session |
| Phone charges but never appears | USB mode | Notification shade > USB preferences > File transfer |
 
## References
 
- [SDK Platform Tools release notes](https://developer.android.com/tools/releases/platform-tools)
- [Android Debug Bridge user guide](https://developer.android.com/tools/adb)
- [Google USB Driver](https://developer.android.com/studio/run/win-usb)
- [Factory images for Pixel](https://developers.google.com/android/images)
- [Magisk installation instructions](https://topjohnwu.github.io/Magisk/install.html)
- [Samsung Smart Switch](https://www.samsung.com/us/support/owners/app/smart-switch)
- [scrcpy](https://github.com/Genymobile/scrcpy)
 
