# Referenced Objects that are not files or folders

environmental variables

from registry

network shares and paths

Libraries touched upon here? (More at: [http://www.grimadmin.com/article.php/creating-modifying-windows-7-libraries](http://technet.microsoft.com/en-us/magazine/jj663498.aspx))

note see apendice for shell extension clsid?

### Shell Namespace Extensions <a href="#h.br0a2v347mfz" id="h.br0a2v347mfz"></a>

[http://www.autoitscript.com/autoit3/docs/appendix/clsid.htm](http://technet.microsoft.com/en-us/library/cc770963.aspx)

#### How to call or activate <a href="#h.5ehiahqn5b5a" id="h.5ehiahqn5b5a"></a>

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

`%SystemRoot%\explorer.exe /E,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}`

**My Documents**

`%SystemRoot%\explorer.exe /N,::{450D8FBA-AD25-11D0-98A8-0800361B1103}`

**Recycle Bin**

`%SystemRoot%\explorer.exe /N,::{645FF040-5081-101B-9F08-00AA002F954E}`

**Network Neighborhood**

`%SystemRoot%\explorer.exe /N,::{208D2C60-3AEA-1069-A2D7-08002B30309D}`

**Default Web Browser or Navigator** (IE, Firefox, Safari, Google Chrome)

`%SystemRoot%\explorer.exe /N,::{871C5380-42A0-1069-A2EA-08002B30309D}`

**Computer Search Results Folder**

`%SystemRoot%\explorer.exe /N,::{1F4DE370-D627-11D1-BA4F-00A0C91EEDBA}`

**Network Search Results Folder**

`%SystemRoot%\explorer.exe /N,::{E17D4FC0-5564-11D1-83F2-00A0C90DC849}`

**Web Folders**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{BDEADF00-C265-11D0-BCED-00A0C90AB50F}`

**Control Panel**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}`

**Printers and Faxes**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{2227A280-3AEA-1069-A2DE-08002B30309D}`

**Scanners and Cameras**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{E211B736-43FD-11D1-9EFB-0000F8757FCD}`

**Fonts**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D20EA4E1-3957-11d2-A40B-0C5020524152}`

**Network Connections or My Network Place**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{7007ACC7-3202-11D1-AAD2-00805FC1270E}`

**Administrative Tools**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D20EA4E1-3957-11d2-A40B-0C5020524153}`

**Tasks Scheduler**

`%SystemRoot%\explorer.exe /N,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::{21EC2020-3AEA-1069-A2DD-08002B30309D}\\::{D6277990-4C6A-11CF-8D87-00AA0060F5BF}`

Games

`%SystemRoot%explorer.exe /E,::{ED228FDF-9EA8-4870-83b1-96b02CFE0D52}`

Hyper-V Remote File Browsing (2012 only?)

`The path "::{0907616E-F5E6-48D8-9D61-A91C3D28106D}\HYPER-V-TEST" is to tell shell (explorer or common file dialog) that it is hosting/pointing to the RemoteFileBrowsing shell namespace extension on the HYPER-V-TEST. The guid is Hyper-V remotefilebrowsing shell namespace extension GUID. However, due to the limitation on common file browser, it is not able to translated into "Hyper-V Remote File Browsing".`

Bug and Workaround caused by Audit Object Browsing http://workinghardinit.wordpress.com/2013/01/10/remote-file-browsing-issue-in-windows-server-2012-hyper-v-leaves-results-pane-empty-workaround/

`::{0907616E-F5E6-48D8-9D61-A91C3D28106D}\VM-SERVERNAME\D:\hyper-v\virtual hard disks`

#### All Tasks folder (“God-Mode”) <a href="#h.8as2ptd62m47" id="h.8as2ptd62m47"></a>

`Available in \_ operating systems`

Ways to create the folder

{ed7ba470-8e54-465e-825c-99712043e01c}

**Contents of ‘All Tasks’ folder (Windows 7)**

**Action Center**

Change Customer Experience Improvement Program settings

**Administrative Tools**

Create and format hard disk partitions

**AutoPlay**

**Backup and Restore**

**Color Management**

`**Contents of ‘All Tasks’ folder (Windows Server \_?)**`

**Contents of ‘All Tasks’ folder (Windows 8)**

### Shares <a href="#h.6mgfjeh2d4bo" id="h.6mgfjeh2d4bo"></a>

ADMIN$

C$

IPC$

FAX$

PRINT$

[http://support.microsoft.com/kb/314984](http://support.microsoft.com/kb/314984)

[http://www.itworld.com/security/53406/disabling-hidden-administrative-shares](http://www.itworld.com/security/53406/disabling-hidden-administrative-shares)

More shares found in Active Directory section above

### Windows Registry keys <a href="#h.2tkqexxuulel" id="h.2tkqexxuulel"></a>

| **Description**                                     | **Key Name**                                                                                                      |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| RegEdit Favorites                                   | HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\Regedit\Favorites                                          |
| CurrentControlSet\[1]                               | HKLM\SYSTEM\Select                                                                                                |
| LogonUI                                             | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Authentication\LogonUI                                             |
| List SID & user accounts\[2]                        | HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList                                                     |
| Network Shares                                      | HKLM\SYSTEM\CurrentControlSet\services\LanmanServer\Shares                                                        |
| Environmental variables                             | HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Environment                                                 |
| Local Admin (HKCU)                                  | HKEY\_USERS\S-1-5-21-<3171392789-1724324034-2371106253>-500                                                       |
| Winlogon                                            | HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon                                                        |
| Environmental variables for User                    | HKCU\Environment                                                                                                  |
| Default User settings                               | HKEY\_USERS\\.DEFAULT                                                                                             |
| HKCU Desktop                                        | HKCU\Control Panel\Desktop                                                                                        |
| User Shell Folders                                  | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders                                        |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |
| Start Up                                            | HKCU\Software\Microsoft\Windows\CurrentVersion\Run                                                                |
| Desktop, Wallpaper, Screen saver                    | HKCU\Control Panel\Desktop                                                                                        |
| Screen saver                                        | HKCU\Control Panel\Desktop\SCRNSAVE.EXE                                                                           |
| Screen saver grace period                           | HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\ScreenSaverGracePeriod                                 |
| Wallpaper                                           | HKCU\Control Panel\Desktop\Wallpaper                                                                              |
| Default Printer                                     | HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows                                                         |
| Win7 Printers Folder on Desktop                     | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\\{2227a280-3aea-1069-a2de-08002b30309d} |
| Uninstall                                           | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall                                                          |
| Offline Files                                       | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\NetCache                                                           |
|                                                     |                                                                                                                   |
| ODBC System DSNs                                    | HKLM\SOFTWARE\ODBC\ODBC.INI                                                                                       |
| ODBC User DSNs                                      | HKCU\Software\ODBC\ODBC.INI                                                                                       |
| Do not Block files downloaded from the Internet\[3] | HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Attachments\SaveZoneInformation                           |
| Fix for default Outlook account\[4]                 | HKCU\Software\Microsoft\Office\14.0\Outlook\Options\Mail\NewItemsUseDefaultSendingAccount                         |
|                                                     |                                                                                                                   |
| MAPI, Mail Profiles                                 | HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows Messaging Subsystem\Profiles                            |
|                                                     |                                                                                                                   |
| OOBE                                                |                                                                                                                   |
| SYSTEM\WPA                                          |                                                                                                                   |
|                                                     |                                                                                                                   |
| Shares                                              |                                                                                                                   |
|                                                     |                                                                                                                   |
| Certificates for User                               | HKCU\Software\Microsoft\\?                                                                                        |
| Certificates for Local Machine                      | HKLM\Software\Microsoft\\?                                                                                        |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |
|                                                     |                                                                                                                   |

**Note**

[http://en.wikipedia.org/wiki/Regedit#Editing](http://office.microsoft.com/en-us/outlook-help/where-does-microsoft-outlook-2010-save-my-information-and-configurations-HP010354943.aspx#Editing) for additional .REG file format, command-line, and system registry file locations.

### Environmental Variables <a href="#h.27tpyo2kf7eg" id="h.27tpyo2kf7eg"></a>

`SET`

`SETX.EXE`

`HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Environment`

`HKCU\Environment`

`TEMP, TMP %USERPROFILE%\AppData\Local\Temp`

| ALLUSERSPROFILE         | C:\ProgramData                                        |
| ----------------------- | ----------------------------------------------------- |
| APPDATA                 | C:\Users\\\<UserName>\AppData\Roaming                 |
| CommonProgramFiles      | C:\Program Files\Common Files                         |
| CommonProgramFiles(x86) | C:\Program Files (x86)\Common Files                   |
| CommonProgramW6432      | C:\Program Files\Common Files                         |
| COMPUTERNAME            |                                                       |
| ComSpec                 | C:\Windows\system32\cmd.exe                           |
| FP\_NO\_HOST\_CHECK     | NO                                                    |
| HOMEDRIVE               |                                                       |
| HOMEPATH                |                                                       |
| HOMESHARE               |                                                       |
| LOCALAPPDATA            | C:\Users\\\<UserName>\AppData\Local                   |
| LOGONSERVER             | \\\SERVER                                             |
| NUMBER\_OF\_PROCESSORS  | 4                                                     |
| OS                      | Windows\_NT                                           |
| PATHEXT                 | .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC |
| PROCESSOR\_ARCHITECTURE | AMD64                                                 |
| PROCESSOR\_IDENTIFIER   | Intel64 Family 6 Model 42 Stepping 7, GenuineIntel    |
| PROCESSOR\_LEVEL        | 6                                                     |
| PROCESSOR\_REVISION     | 2a07                                                  |
| ProgramData             | C:\ProgramData                                        |
| ProgramFiles            | C:\Program Files                                      |
| ProgramFiles(x86)       | C:\Program Files (x86)                                |
| ProgramW6432            | C:\Program Files                                      |
| PROMPT                  | $P$G                                                  |
| PSModulePath            | C:\Windows\system32\WindowsPowerShell\v1.0\Modules\\  |
| PUBLIC                  | C:\Users\Public                                       |
| SESSIONNAME             | Console                                               |
| SystemDrive             | C:                                                    |
| SystemRoot              | C:\Windows                                            |
| TEMP                    | C:\Users\\_JSMITH\~1_\AppData\Local\Temp              |
| TMP                     | C:\Users\\_JSMITH\~1_\AppData\Local\Temp              |
| USERDNSDOMAIN           | _MYDOMAIN.COM_                                        |
| USERDOMAIN              | _MYDOMAIN.COM_                                        |
| USERNAME                | \<UserName>                                           |
| USERPROFILE             | C:\Users\\\<UserName>                                 |
| windir                  | C:\Windows                                            |
| windows\_tracing\_flags | 3                                                     |
|                         |                                                       |

#### Additional Common Values <a href="#h.32ephbb6tky6" id="h.32ephbb6tky6"></a>

**OS**

|                 |             |
| --------------- | ----------- |
| Windows XP      |             |
| Windows 2003    |             |
| Windows Vista   |             |
| Windows 7       | Windows\_NT |
| Windows 2008 R2 | Windows\_NT |
| Windows 8       | Windows\_NT |
| Windows 2012    |             |
|                 |             |

`PROCESSOR\_ARCHITECTURE`

Environmental variables unique to Remote Desktop (Terminal Server)

SESSIONNAME=

#### Command Prompt <a href="#h.vfs8cpaz69uc" id="h.vfs8cpaz69uc"></a>

Changing the Prompt in CMD.EXE can use the following variables in addition to environmental variables.

Note: Dynamic variables can be used but are not updated.

| $A  | & (Ampersand)                                                                                                                            |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| $B  | \| (pipe)                                                                                                                                |
| $C  | ( (Left parenthesis)                                                                                                                     |
| $D  | Current date                                                                                                                             |
| $E  | Escape code\[5] (ASCII code 27)                                                                                                          |
| $F  | ) (Right parenthesis)                                                                                                                    |
| $G  | > (greater-than sign)                                                                                                                    |
| $H  | Backspace (erases previous character)                                                                                                    |
| $L  | < (less-than sign)                                                                                                                       |
| $N  | Current drive                                                                                                                            |
| $P  | Current drive and path                                                                                                                   |
| $Q  | = (equal sign)                                                                                                                           |
| $S  | (space)                                                                                                                                  |
| $T  | Current time                                                                                                                             |
| $V  | Windows version number                                                                                                                   |
| $\_ | Carriage return and linefeed                                                                                                             |
| \$$ | $ (dollar sign)                                                                                                                          |
| $+  | **\*** zero or more plus sign (+) characters depending upon the depth of the PUSHD directory stack, one character for each level pushed. |
| $M  | **\*** Displays the remote name associated with the current drive letter or the empty string if current drive is not a network drive.    |

`**\*** Requires Command Extensions are enabled`

See also: The TITLE Command which uses System and User Environmental Variables but not compatible with PROMPT variables.

PROMPT can be set as an environmental variable in Windows 7.

#### Dynamic Environmental Variables <a href="#h.ndj554lbgu8i" id="h.ndj554lbgu8i"></a>

If Command Extensions are enabled, then there are several dynamic environment variables that can be expanded but which don't show up in the list of variables displayed by SET. These variable values are computed dynamically each time the value of the variable is expanded. If the user explicitly defines a variable with one of these names, then that definition will override the dynamic one described below:

| %CD%                    | expands to the current directory string.                                 |
| ----------------------- | ------------------------------------------------------------------------ |
| %DATE%                  | expands to current date using same format as DATE command.               |
| %TIME%                  | expands to current time using same format as TIME command.               |
| %RANDOM%                | expands to a random decimal number between 0 and 32767.                  |
| %ERRORLEVEL%            | expands to the current ERRORLEVEL value                                  |
| %CMDEXTVERSION%         | expands to the current Command Processor Extensions version number.      |
| %CMDCMDLINE%            | expands to the original command line that invoked the Command Processor. |
| %HIGHESTNUMANODENUMBER% | expands to the highest NUMA node number on this machine.                 |
| %0                      | expands to be the path and filename of the current file.                 |
| %1, %2, %3, …           | arguments included on the command line.                                  |

#### PowerShell Variables <a href="#h.dly4nf7wad2" id="h.dly4nf7wad2"></a>

`about\_Environment\_Variables`

[http://technet.microsoft.com/en-us/library/hh847808.aspx](http://technet.microsoft.com/en-us/library/hh847808.aspx)

`PSModulePath=C:\Windows\system32\WindowsPowerShell\v1.0\Modules\\`

`http://msdn.microsoft.com/en-us/library/windows/desktop/dd878326%28v=vs.85%29.aspx`

`\[PS] C:\\>get-variable`

| **Name**                        | **Value**                                                                                          |
| ------------------------------- | -------------------------------------------------------------------------------------------------- |
| $                               | \~\history.csv                                                                                     |
| ?                               | True                                                                                               |
| ^                               | Get-History                                                                                        |
| \_                              |                                                                                                    |
| args                            | {}                                                                                                 |
| CommonConnectFunctions\_Loca... | {res\_0005, res\_0004, res\_0001, res\_0000, res\_0003, res\_0002}                                 |
| ConfigurationPath               | C:\Program Files\Microsoft\Exchange Server\V14\bin\Microsoft.Exchange.Configuration.O...           |
| ConfirmPreference               | High                                                                                               |
| connectedFqdn                   | MYSERVER.mydomain.com                                                                              |
| ConnectFunctions\_LocalizedS... | {res\_0001, res\_0000, res\_0003, res\_0002, res\_0005, res\_0004, res\_0007, res\_0006, res\_...  |
| ConsoleFileName                 |                                                                                                    |
| DebugPreference                 | SilentlyContinue                                                                                   |
| Error                           | {The term 'testpath' is not recognized as the name of a cmdlet, function, script file...           |
| ErrorActionPreference           | Continue                                                                                           |
| ErrorView                       | NormalView                                                                                         |
| exbin                           | C:\Program Files\Microsoft\Exchange Server\V14\bin\\                                               |
| ExecutionContext                | System.Management.Automation.EngineIntrinsics                                                      |
| exinstall                       | C:\Program Files\Microsoft\Exchange Server\V14\\                                                   |
| exrandom                        | System.Random                                                                                      |
| exscripts                       | C:\Program Files\Microsoft\Exchange Server\V14\scripts\\                                           |
| false                           | False                                                                                              |
| FormatEnumerationLimit          | 16                                                                                                 |
| getLiveIDCredCode               | using System;...                                                                                   |
| HOME                            |                                                                                                    |
| Host                            | System.Management.Automation.Internal.Host.InternalHost                                            |
| importResults                   | server.mydomain.com                                                                                |
| input                           | System.Collections.ArrayList+ArrayListEnumeratorSimple                                             |
| LASTEXITCODE                    | 0                                                                                                  |
| ManagementPath                  | C:\Program Files\Microsoft\Exchange Server\V14\bin\Microsoft.Exchange.Management.dll               |
| MaximumAliasCount               | 4096                                                                                               |
| MaximumDriveCount               | 4096                                                                                               |
| MaximumErrorCount               | 256                                                                                                |
| MaximumFunctionCount            | 4096                                                                                               |
| MaximumHistoryCount             | 64                                                                                                 |
| MaximumVariableCount            | 4096                                                                                               |
| MyInvocation                    | System.Management.Automation.InvocationInfo                                                        |
| NestedPromptLevel               | 0                                                                                                  |
| null                            |                                                                                                    |
| OutputEncoding                  | System.Text.ASCIIEncoding                                                                          |
| partialTypeFile                 | C:\Program Files\Microsoft\Exchange Server\V14\bin\Exchange.partial.Types.ps1xml                   |
| PID                             | 8600                                                                                               |
| PROFILE                         | \\\AppServer\Users\Mark McDow\Data\Documents\WindowsPowerShell\Microsoft.PowerShell\_pr...         |
| ProgressPreference              | Continue                                                                                           |
| PSBoundParameters               | {}                                                                                                 |
| PSCulture                       | en-US                                                                                              |
| PSEmailServer                   |                                                                                                    |
| PSHOME                          | C:\Windows\System32\WindowsPowerShell\v1.0                                                         |
| PSSessionApplicationName        | wsman                                                                                              |
| PSSessionConfigurationName      | http://schemas.microsoft.com/powershell/Microsoft.PowerShell                                       |
| PSSessionOption                 | System.Management.Automation.Remoting.PSSessionOption                                              |
| PSUICulture                     | en-US                                                                                              |
| PSVersionTable                  | {CLRVersion, BuildVersion, PSVersion, WSManStackVersion, PSCompatibleVersions, Serial...           |
| PWD                             | C:\\                                                                                               |
| RemoteExchange\_LocalizedStr... | {res\_0003, res\_help\_for\_cmdlet, res\_0005, res\_0007, res\_0009, res\_general\_help, res\_t... |
| remoteSession                   | System.Management.Automation.Runspaces.PSSession                                                   |
| ReportErrorShowExceptionClass   | 0                                                                                                  |
| ReportErrorShowInnerException   | 0                                                                                                  |
| ReportErrorShowSource           | 1                                                                                                  |
| ReportErrorShowStackTrace       | 0                                                                                                  |
| sessionOptionsTimeout           | 180000                                                                                             |
| ShellId                         | Microsoft.PowerShell                                                                               |
| StackTrace                      | at System.Management.Automation.CommandDiscovery.LookupCommandInfo(String commandN...              |
| true                            | True                                                                                               |
| typeFilePath                    | C:\Program Files\Microsoft\Exchange Server\V14\bin\exchange.types.ps1xml                           |
| typeListToCheck                 |                                                                                                    |
| typeLoadResult                  | True                                                                                               |
| VerbosePreference               | SilentlyContinue                                                                                   |
| WarningPreference               | Continue                                                                                           |
| WhatIfPreference                | False                                                                                              |
|                                 |                                                                                                    |

#### Group Policy Management Editor <a href="#h.e930dnr9oo0w" id="h.e930dnr9oo0w"></a>

Preference extensions support Windows environment variables and generate a number of additional process environment variables.

1. Open the Group Policy Management Console. Right-click the Group Policy object (GPO) that contains the preference item that you want to configure, and then click **Edit**.
2. Item-level targeting, Targeting..., New Item, Environment Variable, Name:
`3. Press F3 to display a list of variables from which you can select\[6].`

**Note** By using Registry Match Targeting targeting items, you can define variables at client run-time, and have these control behavior by using the Environment Variable Targeting targeting items or as values in a preference item setting.

Select a Variable

Select a System Defined Variable

| **Variable Name**   | **Description**                                                                                                                       |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| AppDataDir          | The current user’s application data directory.                                                                                        |
| BinaryComputerSid   | The SID of the computer in hexadecimal format.                                                                                        |
| BinaryUserSid       | The SID of the current user in hexadecimal format.                                                                                    |
| CommonAppdataDir    | The "all users" Application Data directory.                                                                                           |
| CommonDesktopDir    | The "all users" Desktop directory.                                                                                                    |
| CommonFavoritesDir  | The "all users" Explorer Favorites directory.                                                                                         |
| CommonProgramsDir   | The "all users" Programs directory.                                                                                                   |
| CommonStartMenuDir  | The "all users" Start Menu directory.                                                                                                 |
| CommonStartUpDir    | The "all users" Startup directory.                                                                                                    |
| ComputerName        | The NetBIOS name of the computer.                                                                                                     |
| CurrentProcessId    | The numeric identity of the main process.                                                                                             |
| CurrentThreadId     | The numeric identity of the main thread.                                                                                              |
| DateTime            | The current time (UTC).                                                                                                               |
| DateTimeEx          | The current time (UTC) with milliseconds.                                                                                             |
| DesktopDir          | The current user’s desktop directory.                                                                                                 |
| DomainName          | The domain name or workgroup of the computer.                                                                                         |
| FavoritesDir        | The current user’s Explorer favorites directory.                                                                                      |
| GphPath             | The path to the history file.                                                                                                         |
| GptpPath            | The path to the configuration file.                                                                                                   |
| GroupPolicyVersion  | The version of the running Group Policy CSE.                                                                                          |
| LastDriveMapped     | The drive letter of the last successful network drive mapping.                                                                        |
| LastError           | The last error code encountered during configuration.                                                                                 |
| LastErrorText       | The last error code text description.                                                                                                 |
| LdapComputerSid     | The SID of the computer in LDAP escaped binary format.                                                                                |
| LdapUserSid         | The SID of the logon user in LDAP escaped binary format.                                                                              |
| LocalTime           | The current local time.                                                                                                               |
| LocalTimeEx         | The current local time with milliseconds.                                                                                             |
| LogonDomain         | The domain of the current user.                                                                                                       |
| LogonServer         | The domain controller that authenticated the current user.                                                                            |
| LogonUser           | The username of the current user.                                                                                                     |
| LogonUserSid        | The SID on the logon user.                                                                                                            |
| MacAddress          | The first detected MAC address on the computer.                                                                                       |
| NetPlacesDir        | The current user’s my network places directory.                                                                                       |
| OsVersion           | The operating system: Windows XP \| Windows Server 2003 \| Windows Server 2003 R2 \| Windows Vista \| Windows Server 2008 \| Unknown. |
| ProgramFilesDir     | The Windows Program Files directory.                                                                                                  |
| ProgramsDir         | The current user’s programs directory.                                                                                                |
| RecentDocumentsDir  | The current user’s recent documents directory.                                                                                        |
| ResultCode          | The client’s exit code.                                                                                                               |
| ResultText          | The client’s exit code text description.                                                                                              |
| ReversedComputerSid | The SID on the computer in reversed byte order hexadecimal format.                                                                    |
| ReversedUserSid     | The SID of the current user in reversed byte order hexadecimal format.                                                                |
| SendToDir           | The current user's Send to directory.                                                                                                 |
| StartMenuDir        | The current user's Start Menu directory.                                                                                              |
| StartUpDir          | The current user's Startup directory.                                                                                                 |
| SystemDir           | The Windows system directory.                                                                                                         |
| SystemDrive         | The name of the drive from which the operating system is running.                                                                     |
| TempDir             | The current user’s temp directory as determined by Windows API.                                                                       |
| TimeStamp           | The time stamp of the configurations being executed.                                                                                  |
| TraceFile           | The path/name of the trace file.                                                                                                      |
| WindowsDir          | The Windows directory.                                                                                                                |

☑ Resolve Variable

**Note**

`You can prevent the resolution of a variable before it is applied to client computers (so that the variable instead of the resolved value appears in the preference setting on client computers). To do this for a preference process variable, clear the **Resolve Variable** check box. This inserts **<>** between the **%** **%** delimiters and the variable name (for example, %\<ProgramFiles>%). Preference extensions remove **< >** characters from the text and leave the unresolved variable. You can also use this syntax with a Windows environment variable.`

`1. [http://technet.microsoft.com/en-us/library/cc783264%28v=ws.10%29.aspx](http://technet.microsoft.com/en-us/library/cc783264\(v=ws.10\).aspx) ↑`
2. [http://support.microsoft.com/kb/154599](http://support.microsoft.com/kb/154599) ↑
3. [http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a](http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a) ↑
4. [http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/](http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/) ↑
`5. See ANSI.SYS [http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm](http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm) ↑`
6. Variables in Preference Items ↑
