# Referenced Objects that are not files or folders

environmental variables

from registry

network shares and paths

Libraries touched upon here? (More at: [http://www.grimadmin.com/article.php/creating-modifying-windows-7-libraries](http://technet.microsoft.com/en-us/magazine/jj663498.aspx))

note see apendice for shell extension clsid?

### Shell Namespace Extensions {#h.br0a2v347mfz" id="h.br0a2v347mfz

[http://www.autoitscript.com/autoit3/docs/appendix/clsid.htm](http://technet.microsoft.com/en-us/library/cc770963.aspx)

#### How to call or activate {#h.5ehiahqn5b5a" id="h.5ehiahqn5b5a

| **Folder**               | **Value for the File\_\_\_'s directory parameter** |
| ------------------------ | -------------------------------------------------- |
| Administrative Tools     | "::{D20EA4E1-3957-11d2-A40B-0C5020524153}"         |
| Briefcase                | "::{85BBD920-42A0-1069-A2E4-08002B30309D}"         |
| Control Panel            | "::{21EC2020-3AEA-1069-A2DD-08002b30309d}"         |
| Fonts                    | "::{D20EA4E1-3957-11d2-A40B-0C5020524152}"         |
| History                  | "::{FF393560-C2A7-11CF-BFF4-444553540000}"         |
| Inbox                    | "::{00020D75-0000-0000-C000-000000000046}"         |
| Microsoft Network        | "::{00028B00-0000-0000-C000-000000000046}"         |
| My Computer              | "::{20D04FE0-3AEA-1069-A2D8-08002B30309D}"         |
| My Documents             | "::{450D8FBA-AD25-11D0-98A8-0800361B1103}"         |
| My Network Places        | "::{208D2C60-3AEA-1069-A2D7-08002B30309D}"         |
| Network Computers        | "::{1f4de370-d627-11d1-ba4f-00a0c91eedba}"         |
| Network Connections      | "::{7007ACC7-3202-11D1-AAD2-00805FC1270E}"         |
| Printers and Faxes       | "::{2227A280-3AEA-1069-A2DE-08002B30309D}"         |
| Programs Folder          | "::{7be9d83c-a729-4d97-b5a7-1b7313c39e0a}"         |
| Recycle Bin              | "::{645FF040-5081-101B-9F08-00AA002F954E}"         |
| Scanners and Cameras     | "::{E211B736-43FD-11D1-9EFB-0000F8757FCD}"         |
| Scheduled Tasks          | "::{D6277990-4C6A-11CF-8D87-00AA0060F5BF}"         |
| Start Menu Folder        | "::{48e7caab-b918-4e58-a94d-505519c795dc}"         |
| Temporary Internet Files | "::{7BD29E00-76C1-11CF-9DD0-00A0C9034933}"         |
| Web Folders              | "::{BDEADF00-C265-11d0-BCED-00A0C90AB50F}"         |

Restore missing functionality to Windows 7

Printers without grouping by port {2227a280-3aea-1069-a2de-08002b30309d}

Network Neighborhood with comments Network.{208d2c60-3aea-1069-a2d7-08002b30309d}

[http://www.mydigitallife.info/command-line-switches-to-display-special-objects-or-folders-when-opening-windows-explorer/](http://www.askvg.com/fix-the-products-we-found-in-your-account-cant-be-used-to-activate-error-message-in-microsoft-office-2013-applications/)

**My Computer**

``%SystemRoot%\explorer.exe /E,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}``

**My Documents**

``%SystemRoot%\explorer.exe /N,::{450D8FBA-AD25-11D0-98A8-0800361B1103}``

**Recycle Bin**

``%SystemRoot%\explorer.exe /N,::{645FF040-5081-101B-9F08-00AA002F954E}``

**Network Neighborhood**

``%SystemRoot%\explorer.exe /N,::{208D2C60-3AEA-1069-A2D7-08002B30309D}``

**Default Web Browser or Navigator** (IE, Firefox, Safari, Google Chrome)

``%SystemRoot%\explorer.exe /N,::{871C5380-42A0-1069-A2EA-08002B30309D}``

**Computer Search Results Folder**

``%SystemRoot%\explorer.exe /N,::{1F4DE370-D627-11D1-BA4F-00A0C91EEDBA}``

**Network Search Results Folder**

``%SystemRoot%\explorer.exe /N,::{E17D4FC0-5564-11D1-83F2-00A0C90DC849}``

**Web Folders**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{BDEADF00-C265-11D0-BCED-00A0C90AB50F}``

**Control Panel**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}``

**Printers and Faxes**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{2227A280-3AEA-1069-A2DE-08002B30309D}``

**Scanners and Cameras**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{E211B736-43FD-11D1-9EFB-0000F8757FCD}``

**Fonts**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D20EA4E1-3957-11d2-A40B-0C5020524152}``

**Network Connections or My Network Place**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{7007ACC7-3202-11D1-AAD2-00805FC1270E}``

**Administrative Tools**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D20EA4E1-3957-11d2-A40B-0C5020524153}``

**Tasks Scheduler**

``%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D6277990-4C6A-11CF-8D87-00AA0060F5BF}``

Games

``%SystemRoot%explorer.exe /E,::{ED228FDF-9EA8-4870-83b1-96b02CFE0D52}``

Hyper-V Remote File Browsing (2012 only?)

``The path "::{0907616E-F5E6-48D8-9D61-A91C3D28106D}\HYPER-V-TEST" is to tell shell (explorer or common file dialog) that it is hosting/pointing to the RemoteFileBrowsing shell namespace extension on the HYPER-V-TEST. The guid is Hyper-V remotefilebrowsing shell namespace extension GUID. However, due to the limitation on common file browser, it is not able to translated into "Hyper-V Remote File Browsing".``

Bug and Workaround caused by Audit Object Browsing `http://workinghardinit.wordpress.com/2013/01/10/remote-file-browsing-issue-in-windows-server-2012-hyper-v-leaves-results-pane-empty-workaround/`

``::{0907616E-F5E6-48D8-9D61-A91C3D28106D}\VM-SERVERNAME\D:\hyper-v\virtual hard disks``

#### All Tasks folder (“God-Mode”) {#h.8as2ptd62m47" id="h.8as2ptd62m47

``Available in \_ operating systems``

Ways to create the folder

{ed7ba470-8e54-465e-825c-99712043e01c}

**Contents of 'All Tasks' folder (Windows 7)**

**Action Center**

Change Customer Experience Improvement Program settings

**Administrative Tools**

Create and format hard disk partitions

**AutoPlay**

**Backup and Restore**

**Color Management**

``**Contents of 'All Tasks' folder (Windows Server \_?)**``

**Contents of 'All Tasks' folder (Windows 8)**

### Shares {#h.6mgfjeh2d4bo" id="h.6mgfjeh2d4bo

ADMIN$

C$

IPC$

FAX$

PRINT$

[http://support.microsoft.com/kb/314984](http://support.microsoft.com/kb/314984)

[http://www.itworld.com/security/53406/disabling-hidden-administrative-shares](http://www.itworld.com/security/53406/disabling-hidden-administrative-shares)

More shares found in Active Directory section above

### Windows Registry keys {#h.2tkqexxuulel" id="h.2tkqexxuulel

| **Description**                                     | **Key Name**                                                                                                      |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| RegEdit Favorites                                   | ``HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\Regedit\Favorites``                                      |
| CurrentControlSet\[1]                               | ``HKLM\SYSTEM\Select``                                                                                            |
| LogonUI                                             | `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Authentication\LogonUI`                                            |
| List SID & user accounts\[2]                        | `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`                                                    |
| Network Shares                                      | `HKLM\SYSTEM\CurrentControlSet\services\LanmanServer\Shares`                                                       |
| Environmental variables                             | `HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Environment`                                                |
| Local Admin (HKCU)                                  | `HKEY\USERS\S-1-5-21-<3171392789-1724324034-2371106253>-500`                                                       |
| Winlogon                                            | `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogo`n                                                       |
| Environmental variables for User                    | `HKCU\Environment`                                                                                                 |
| Default User settings                               | `HKEY\USERS\.DEFAULT`                                                                                             |
| HKCU Desktop                                        | `HKCU\Control Panel\Desktop`                                                                                       |
| User Shell Folders                                  | `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders`                                       |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |
| Start Up                                            | `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`                                                               |
| Desktop, Wallpaper, Screen saver                    | `HKCU\Control Panel\Desktop`                                                                                       |
| Screen saver                                        | `HKCU\Control Panel\Desktop\SCRNSAVE.EXE`                                                                          |
| Screen saver grace period                           | `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\ScreenSaverGracePeriod`                                |
| Wallpaper                                           | `HKCU\Control Panel\Desktop\Wallpaper`                                                                             |
| Default Printer                                     | `HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows`                                                        |
| Win7 Printers Folder on Desktop                     | `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\`<br>`Desktop\NameSpace\{2227a280-3aea-1069-a2de-08002b30309d}`|
| Uninstall                                           | `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`                                                         |
| Offline Files                                       | `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\NetCache`                                                          |
|                                                     |                                                                                                                   |
| ODBC System DSNs                                    | `HKLM\SOFTWARE\ODBC\ODBC.INI`                                                                                      |
| ODBC User DSNs                                      | `HKCU\Software\ODBC\ODBC.INI`                                                                                      |
| Do not Block files downloaded<br> from the Internet\[3] | `HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Attachments\SaveZoneInformation`                          |
| Fix for default Outlook account\[4]                 | `HKCU\Software\Microsoft\Office\14.0\Outlook\Options\Mail\NewItemsUseDefaultSendingAccount`                        |
|                                                     |                                                                                                                   |
| MAPI, Mail Profiles                                 | `HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows Messaging Subsystem\Profiles`                           |
|                                                     |                                                                                                                   |
| OOBE                                                |                                                                                                                   |
| SYSTEM\WPA                                          |                                                                                                                   |
|                                                     |                                                                                                                   |
| Shares                                              |                                                                                                                   |
|                                                     |                                                                                                                   |
| Certificates for User                               | `HKCU\_Software\Microsoft\\?`                                                                                       |
| Certificates for Local Machine                      | `HKLM\_Software\Microsoft\\?`                                                                                       |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |

**Note**

[http://en.wikipedia.org/wiki/Regedit#Editing](http://office.microsoft.com/en-us/outlook-help/where-does-microsoft-outlook-2010-save-my-information-and-configurations-HP010354943.aspx#Editing) for additional .REG file format, command-line, and system registry file locations.

### Environmental Variables {#h.27tpyo2kf7eg" id="h.27tpyo2kf7eg

``1. [http://technet.microsoft.com/en-us/library/cc783264%28v=ws.10%29.aspx](http://technet.microsoft.com/en-us/library/cc783264\(v=ws.10\).aspx) ↑``
2. [http://support.microsoft.com/kb/154599](http://support.microsoft.com/kb/154599) ↑
3. [http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a](http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a) ↑
4. [http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/](http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/) ↑
``5. See ANSI.SYS [http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm](http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm) ↑``
6. Variables in Preference Items ↑
