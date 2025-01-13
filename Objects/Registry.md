### Windows Registry keys {#RegistryKeys}

| **Description**                                     | **Key Name**                                                                                                      |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| RegEdit Favorites                                   | `HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\Regedit\Favorites`                                        |
| CurrentControlSet\[1]                               | `HKLM\SYSTEM\Select`                                                                                              |
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
| Certificates for User                               | `HKCU_Software\Microsoft\?`                                                                                       |
| Certificates for Local Machine                      | `HKLM_Software\Microsoft\?`                                                                                       |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |

**Note**

[http://en.wikipedia.org/wiki/Regedit#Editing](http://office.microsoft.com/en-us/outlook-help/where-does-microsoft-outlook-2010-save-my-information-and-configurations-HP010354943.aspx#Editing) for additional .REG file format, command-line, and system registry file locations.
