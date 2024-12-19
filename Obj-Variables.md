### Environmental Variables {#h.27tpyo2kf7eg" id="h.27tpyo2kf7eg


`SET`

`SETX.EXE`

``HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Environment``

``HKCU\Environment``

``TEMP, TMP %USERPROFILE%\AppData\Local\Temp``

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

#### Additional Common Values {#h.32ephbb6tky6" id="h.32ephbb6tky6

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

``PROCESSOR\_ARCHITECTURE``

Environmental variables unique to Remote Desktop (Terminal Server)

SESSIONNAME=

#### Command Prompt {#h.vfs8cpaz69uc" id="h.vfs8cpaz69uc

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

``**\*** Requires Command Extensions are enabled``

See also: The TITLE Command which uses System and User Environmental Variables but not compatible with PROMPT variables.

PROMPT can be set as an environmental variable in Windows 7.

#### Dynamic Environmental Variables {#h.ndj554lbgu8i" id="h.ndj554lbgu8i

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

#### PowerShell Variables {#h.dly4nf7wad2" id="h.dly4nf7wad2

``about\_Environment\_Variables``

[http://technet.microsoft.com/en-us/library/hh847808.aspx](http://technet.microsoft.com/en-us/library/hh847808.aspx)

``PSModulePath=C:\Windows\system32\WindowsPowerShell\v1.0\Modules\\``

``http://msdn.microsoft.com/en-us/library/windows/desktop/dd878326%28v=vs.85%29.aspx``

``\[PS] C:\\>get-variable``

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

#### Group Policy Management Editor {#h.e930dnr9oo0w" id="h.e930dnr9oo0w

Preference extensions support Windows environment variables and generate a number of additional process environment variables.

1. Open the Group Policy Management Console. Right-click the Group Policy object (GPO) that contains the preference item that you want to configure, and then click **Edit**.
2. Item-level targeting, Targeting..., New Item, Environment Variable, Name:
3. Press F3 to display a list of variables from which you can select\[6].

**Note** By using Registry Match Targeting targeting items, you can define variables at client run-time, and have these control behavior by using the Environment Variable Targeting targeting items or as values in a preference item setting.

Select a Variable

Select a System Defined Variable

| **Variable Name**   | **Description**                                                                                                                       |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| AppDataDir          | The current user's application data directory.                                                                                        |
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
| DesktopDir          | The current user's desktop directory.                                                                                                 |
| DomainName          | The domain name or workgroup of the computer.                                                                                         |
| FavoritesDir        | The current user's Explorer favorites directory.                                                                                      |
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
| NetPlacesDir        | The current user's my network places directory.                                                                                       |
| OsVersion           | The operating system: Windows XP \| Windows Server 2003 \|<br> Windows Server 2003 R2 \| Windows Vista \|<br> Windows Server 2008 \| Unknown. |
| ProgramFilesDir     | The Windows Program Files directory.                                                                                                  |
| ProgramsDir         | The current user's programs directory.                                                                                                |
| RecentDocumentsDir  | The current user's recent documents directory.                                                                                        |
| ResultCode          | The client's exit code.                                                                                                               |
| ResultText          | The client's exit code text description.                                                                                              |
| ReversedComputerSid | The SID on the computer in reversed byte order hexadecimal format.                                                                    |
| ReversedUserSid     | The SID of the current user in reversed byte order hexadecimal format.                                                                |
| SendToDir           | The current user's Send to directory.                                                                                                 |
| StartMenuDir        | The current user's Start Menu directory.                                                                                              |
| StartUpDir          | The current user's Startup directory.                                                                                                 |
| SystemDir           | The Windows system directory.                                                                                                         |
| SystemDrive         | The name of the drive from which the operating system is running.                                                                     |
| TempDir             | The current user's temp directory as determined by Windows API.                                                                       |
| TimeStamp           | The time stamp of the configurations being executed.                                                                                  |
| TraceFile           | The path/name of the trace file.                                                                                                      |
| WindowsDir          | The Windows directory.                                                                                                                |

☑ Resolve Variable

**Note**

``You can prevent the resolution of a variable before it is applied to client computers (so that the variable instead of the resolved value appears in the preference setting on client computers). To do this for a preference process variable, clear the **Resolve Variable** check box. This inserts **<>** between the **%** **%** delimiters and the variable name (for example, %\<ProgramFiles>%). Preference extensions remove **< >** characters from the text and leave the unresolved variable. You can also use this syntax with a Windows environment variable.``


5. ``See ANSI.SYS [http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm](http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm) ↑``
6. Variables in Preference Items ↑
