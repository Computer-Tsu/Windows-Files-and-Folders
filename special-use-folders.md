# Special

### Special-use Folders

Including changes from Windows XP to Vista, Windows 7

``Application Data - Roaming C:\Users\\\<UserName>\AppData\Roaming``

``Cookies - Shortcut C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Cookies``

``Favorites C:\Users\Public\Favorites\[1]``

``Libraries - Shortcut C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Libraries``

``Libraries - Shortcut (2) C:\Users\Public\Libraries``

``Local Settings - Local C:\Users\\\<UserName>\AppData\Local``

``My Documents - Documents C:\Users\\\<UserName>\Documents``

``Network Shortcuts - Shortcut "C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Network Shortcuts"``

``Printer Shortcuts - Shortcut "C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Printer Shortcuts"``

``Public Desktop - Shortcut C:\Users\Public\Desktop``

``Public Documents - Shortcut C:\Users\Public\Documents``

``Public Downloads - Shortcut C:\Users\Public\Downloads``

``Public Music - Shortcut C:\Users\Public\Music``

``Public Pictures - Shortcut C:\Users\Public\Pictures``

``Public Recorded TV - Shortcut "C:\Users\Public\Recorded TV"``

``Public Videos - Shortcut C:\Users\Public\Videos``

``Recent Items - Shortcut C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Recent``

``Send to ▶ shortcuts C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\SendTo``

``Start Menu - Shortcut (2) "C:\ProgramData\Microsoft\Windows\Start Menu"``

``Start Menu - Shortcut "C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Start Menu"``

``Templates - Shortcut C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Windows\Templates``

``Default User Profile %SystemDrive%\Users\Default``

``Themes files C:\Users\\\<UserName>\AppData\Local\Microsoft\Windows\Themes``

``Wallpapers C:\Windows\Web\Wallpaper``

``C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar``

``C:\Users\\\<UserName>\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned\StartMenu``

#### Windows Vista/7 Backward Compatible {#h.sh5o97u17lmp" id="h.sh5o97u17lmp

Reparse points, links, junctions, mount points are covered in the File System document.

Warning: RoboCopy (version?) causes a copy-loop with certain /MIR situations.

``DIR C:\Users\\\<USERNAME> /AL to list Reparse Points``

``\<JUNCTION> Application Data \[C:\Users\\\<user name>\AppData\Roaming]``

``\<JUNCTION> Cookies \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Cookies]``

``\<JUNCTION> Local Settings \[C:\Users\\\<user name>\AppData\Local]``

``\<JUNCTION> My Documents \[C:\Users\\\<user name>\Documents]``

``\<JUNCTION> NetHood \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Network Shortcuts]``

``\<JUNCTION> PrintHood \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Printer Shortcuts]``

``\<JUNCTION> Recent \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Recent]``

``\<JUNCTION> SendTo \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\SendTo]``

``\<JUNCTION> Start Menu \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Start Menu]``

``\<JUNCTION> Templates \[C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Templates]``

``DIR C:\Users /AL``

``\<SYMLINKD> All Users \[C:\ProgramData]``

``\<JUNCTION> Default User \[C:\Users\Default]``

``Directory of C:\Users\\_UserName_\AppData\Local``

``\<JUNCTION> Application Data \[C:\Users\\_UserName_\AppData\Local]``

``\<JUNCTION> History \[C:\Users\\_UserName_\AppData\Local\Microsoft\Windows\History]``

``\<JUNCTION> Temporary Internet Files \[C:\Users\\_UserName_\AppData\Local\Microsoft\Windows\Temporary Internet Files]``

``Directory of C:\Users\\_UserName_\Documents``

``\<JUNCTION> My Music \[C:\Users\\_UserName_\Music]``

``\<JUNCTION> My Pictures \[C:\Users\\_UserName_\Pictures]``

``\<JUNCTION> My Videos \[C:\Users\\_UserName_\Videos]``

| **Link**               | **Destination**                                                            |
| ---------------------- | -------------------------------------------------------------------------- |
| Documents and Settings | C:\Users                                                                   |
| All Users              | C:\ProgramData                                                             |
| Default User           | C:\Users\Default                                                           |
| Application Data       | C:\Users\\\<user name>\AppData\Roaming                                     |
| Cookies                | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Cookies           |
| Local Settings         | C:\Users\\\<user name>\AppData\Local                                       |
| My Documents           | C:\Users\\\<user name>\Documents                                           |
| NetHood                | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Network Shortcuts |
| PrintHood              | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Printer Shortcuts |
| Recent                 | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Recent            |
| SendTo                 | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\SendTo            |
| Start Menu             | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Start Menu        |
| Templates              | C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Templates         |

What changes in Windows 8

Shortcuts that no longer work

Shortcuts that still work

``Send To %UserProfile%\AppData\Roaming\Microsoft\Windows\SendTo``

Can also use shell:sendto from Start-Run

### Alternate Data Streams {#h.n04fsvlxp5ss" id="h.n04fsvlxp5ss

More information will be in the File Systems document.

``\[merge section with reserved names, devices, pipes?]``

``filename::datastream \<sp?>``

dir /r

Blocked file downloaded from Internet

Zone.Identifier

how to remove block from multiple files

other common streams

Office document Meta data?

File classification tags?

Zone.Identifier 26 bytes

favicon .url, .website

OECustomProperty .eml

com.dropbox.attributes

AVG .dat files have GUIDs? ex. 36bc5203-fa71-4f47-b52a-d972668bff5d

**Compressed Folders**

Compressed (zipped) Folders Error

``\[Filename] cannot be compressed because it includes characters that cannot be used in a compressed folder such as -. You should rename this file or directory.``

``\- dash``

‘ apostrophe

Unicode characters

### Windows system and configuration files {#h.w944nd5ndp0a" id="h.w944nd5ndp0a

boot.ini

autoexec.nt

``systemroot\system32\autoexec.nt``

``MSDOS.SYS \[Windows 9x]``

IO.SYS

OEM.inf

WIN.INI

SYSTEM.INI

pagefile.sys

hiberfil.sys

``C:\ProgramData \<DRIVE>:\Documents and Settings\All Users\Application Data``

ntuser.pol

Thumbs.db

desktop.ini

``setup.inf \<?>``

Bitlocker

BitLocker Drive Encryption Administration Utilities (only Windows 8, Windows Server 2012)

Manage-bde; Windows PowerShell cmdlets for BitLocker; BitLocker Recovery Password Viewer for Active Directory; BitLocker Network Unlock Provider

``Junctions in C:\ProgramData``

| **Link**         | **Destination**                             |
| ---------------- | ------------------------------------------- |
| Application Data | C:\ProgramData                              |
| Desktop          | C:\Users\Public\Desktop                     |
| Documents        | C:\Users\Public\Documents                   |
| Favorites        | C:\Users\Public\Favorites                   |
| Start Menu       | C:\ProgramData\Microsoft\Windows\Start Menu |
| Templates        | C:\ProgramData\Microsoft\Windows\Templates  |

``C:\ProgramData\Microsoft\Windows\Start Menu``

``C:\ProgramData\\``

└Microsoft

├Assistance

├Crypto

├Device Stage

├DeviceSync

├DRM

├Event Viewer

├HTML Help

├IdentityCRL

├Network

├PlayReady

├RAC

├ServerManager

├User Account Pictures

├Vault

└Windows

#### Volume File System Records {#h.dyvretufswv9" id="h.dyvretufswv9

``C:\System Volume Information``

``C:\System Volume Information\SPP\OnlineMetadataCache``

``{}\_OnDiskSnapshotProp``

``C:\System Volume Information\SPP\SppCbsHiveStore``

``C:\System Volume Information\SPP\SppGroupCache``

``{}\_DriverPackageInfo``

``{}\_WindowsUpdateInfo``

``C:\System Volume Information\Windows Backup\Catalogs\GlobalCatalogLock.dat``

{}

{}{}

{}{}

{}{}

{}{}

MountPointManagerRemoteDatabase

Syscache.hve

Syscache.hve.LOG1

Syscache.hve.LOG2

tracking.log

``C:\Config.Msi``

``C:\MSOCache``

``\[is this mentioned below in the forensics area?]``

#### Start Menu {#h.u87z04jbg8n7" id="h.u87z04jbg8n7

``More details in the Appendice \_ below``

**Windows XP Start Button**

Default user

``Current User C:\Documents and Settings\\_Username_\ ...``

All Users

**Windows 7 Start Orb**

Default user

``Current User C:\Users\\_Username_\AppData\Roaming\Microsoft\Windows\Start Menu``

``All Users C:\ProgramData\Microsoft\Windows\Start Menu``

**Windows 8**

need detail

#### Event Log {#h.pujqf6hynlde" id="h.pujqf6hynlde

wevtvwr.msc

``HKLM\SYSTEM\CurrentControlSet\services\eventlog\Application``

``Default folder C:\Windows\System32\winevt\Logs``

syntax examples using GUI to filter

[http://www.petri.co.il/filtering-and-custom-views-in-vista-event-viewer.htm](http://www.windowsitpro.com/article/remote-computing/remote-command-7227)

NT/2000 Logs

[http://www.eventid.net/show-DocId-5.htm](http://www.eventid.net/show-DocId-5.htm)

**Windows (7) Event Log**

eventcreate Command to add an event to the log

[http://technet.microsoft.com/en-us/library/bb490899.aspx](http://technet.microsoft.com/en-us/library/bb490899.aspx)

WEvtUtil

**Custom Views**

Tip: Create a custom view to search all the event logs.

_Server Roles_

Administrative Events

Microsoft Exchange with Database Availability Group Events

Custom Views can import as Xml files

**Windows Logs**

``Application %SystemRoot%\System32\Winevt\Logs\Application.evtx``

``Security %SystemRoot%\System32\Winevt\Logs\Security.evtx``

``Setup %SystemRoot%\System32\Winevt\Logs\Setup.evtx``

``System %SystemRoot%\System32\Winevt\Logs\System.evtx``

``Forwarded Events %SystemRoot%\System32\Winevt\Logs\ForwardedEvents.evtx``

**Applications and Services Logs**

``ACEEventLog %SystemRoot%\System32\Winevt\Logs\ACEEventLog.evtx``

``Hardware Events %SystemRoot%\System32\Winevt\Logs\HardwareEvents.evtx``

``Internet Explorer %SystemRoot%\System32\Winevt\Logs\Internet Explorer.evtx``

``Key Management Service %SystemRoot%\System32\Winevt\Logs\Key Management Service.evtx``

``Media Center %SystemRoot%\System32\Winevt\Logs\Media Center.evtx``

_Microsoft_

_Windows_

``Microsoft Exchange PSTCapture %SystemRoot%\System32\Winevt\Logs\Microsoft Exchange PSTCapture.evtx``

``Microsoft Office Alerts %SystemRoot%\System32\Winevt\Logs\OAlerts.evtx``

``Windows PowerShell %SystemRoot%\System32\Winevt\Logs\Windows PowerShell.evtx``

Source: Eventlog, Event ID: 1100 System Shutdown

Event ID: 4648 User logon attempted

4624 logon successfull (Type 2 interactive, 3 network)

System, WindowsUpdateClient, 19 update installed successfully

System, EventLog, 6005 System Start

System, EventLog, 6013 Uptime

Time Changed event

track usb device insert [http://www.swiftforensics.com/2012/08/tracking-usb-first-insertion-in-event.html](http://www.autoitscript.com/autoit3/docs/appendix/clsid.htm)

links to repair corrupt [http://www.forensickb.com/2009/01/windows-event-logs.html](http://www.mydigitallife.info/command-line-switches-to-display-special-objects-or-folders-when-opening-windows-explorer/)

forensics detect cleared log books.google.com/books?isbn=1118236084

**Security Auditing**

#### Emergency Management Services {#h.57nrxvjy2dv0" id="h.57nrxvjy2dv0

Windows 2003

To enable Emergency Management Services after setting up a Windows Server 2003 operating system, you must edit the Boot.ini file to enable Windows loader console redirection and Special Administration Console (SAC). The Boot.ini file controls startup; it is located on the system partition root.

Use Bootcfg (Bootcfg.exe) to edit the Boot.ini file.

To view examples of how to edit the Boot.ini file, see "Emergency Management Services" at the Microsoft Windows Resource Kits Web site.

You can enable Emergency Management Services console redirection in the Recovery Console. You do this by editing the Winnt.sif file, located in the Cmdcons folder on the system partition root. Note that the Winnt.sif for the Recovery Console is separate from the floppy disk Winnt.sif file that is referenced in Enabling Emergency Management Services during a new installation.

For specific information about setting Recovery Console Bootcfg parameters for Emergency Management Services, see "Emergency Management Services" at the Microsoft Windows Resource Kits Web site.

``[http://technet.microsoft.com/en-us/library/cc786105%28v=ws.10%29.aspx](http://technet.microsoft.com/en-us/library/cc754361\(v=ws.10\).aspx)``

#### Setup log access {#h.za0t6rs6nzti" id="h.za0t6rs6nzti

``\[DELL only?]``

SAC provides access to the setup logs during GUI-mode Setup. You can press ESC+TAB to switch between the setup logs and SAC. When accessing the setup logs from Emergency Management Services, you can see which portions of Setup have completed and whether any errors have occurred. This is a very useful way to check the progress of your setup and to diagnose setup failures.

The three setup log channels are as follows:

setuplog.txt Monitors setup progress.

setupact.log Displays any warnings during setup.

setuperr.log Displays any errors that might occur during setup.

#### Registry {#h.dv5d16psp8f9" id="h.dv5d16psp8f9

**System**

``HKEY\_Local\_Machine\SYSTEM C:\Windows\System32\config\SYSTEM``

``HKEY\_LOCAL\_MACHINE\SOFTWARE C:\Windows\System32\config\SOFTWARE``

``HKEY\_USERS\\.DEFAULT C:\Windows\System32\config\DEFAULT``

``HKEY\_LOCAL\_MACHINE\SAM, HKEY\_LOCAL\_MACHINE\SECURITY\SAM C:\Windows\System32\config\SAM``

``HKEY\_LOCAL\_MACHINE\SECURITY C:\Windows\System32\config\SECURITY``

**User**

``HKEY\_Current\_User C:\Users\\_\<username>_\NTUSER.DAT``

**Service/System User Account Profile**

``SYSTEM (S-1-5-18) %systemroot%\System32\config\systemprofile\ntuser.dat``

``LOCAL SERVICE (S-1-5-19) C:\Windows\ServiceProfiles\LocalService\NTUSER.DAT``

``NETWORK SERVICE (S-1-5-20) C:\Windows\ServiceProfiles\NetworkService\NTUSER.DAT``

Local Service and Network Service have full profiles including directory tree like a regular user account.

``where is user\software, current\_user?``

NTUSER.INI roaming profile

NTUSER.MAN a ntuser.dat file renamed to become a mandatory profile that the user cannot make changes.

More information about Profiles above/below

``C:\Windows\System32\config\RegBack``

#### System Protected Files {#h.9nh67tqaidkk" id="h.9nh67tqaidkk

**Microsoft (R) Windows (R) Resource Checker Version 6.0**

``System File Checker C:\Windows\System32\sfc.exe``

sfc /verifynow

``Backup copies location %WinDir%\System32\Dllcache\\``

List of files checked by SFC

Catalog location

Process/Service filename/path

Registry key that stores install source

``Logs C:\Windows\Logs\CBS\CBS.log``

``findstr /c:"\[SR]" %windir%\Logs\CBS\CBS.log >"%userprofile%\Desktop\sfcdetails.txt"``

SFCShowProgress registry entry is missing or is set to 1, and the server is set to scan every time that the computer starts. In this situation, WFP waits for a console logon. Therefore, the RPC server does not start until the scan is performed. The computer has no protection during this time.

``HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\SfcScan and others``

[http://support.microsoft.com/kb/222193](http://support.microsoft.com/kb/222193)

#### Reserved names {#h.9nt6fh9kslmx" id="h.9nt6fh9kslmx

CON, PRN, AUX, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, LPT9

**Usernames Prevented**

Some versions cannot create user named “Admin” ?

Administrator, Default, Public, Guest, System

The name cannot be identical to any other user, computer, or group name in the domain. It can contain up to 20 uppercase or lowercase characters except for the following:" / \ \[ ] : ; | = , + \* ? <>

#### Recycle Bin {#h.83kv3dsi6dgx" id="h.83kv3dsi6dgx

``C:\\$Recycle.Bin\\``

``C:\\$Recycle.Bin\S-1-5-21-3171392789-1724324034-2371106253-500``

``Contents renamed to 8.3 files keeping extension and named $\<random alpha-numberic>``

#### System Restore {#h.lb6oo587b0bt" id="h.lb6oo587b0bt

rstrui.exe

``Windows XP C:\System Volume Information\\\_restore{D86480E3-73EF.....D8}\RP1\Snapshot\ etc``

**Manual System Restore Process**

#### Performance Monitoring {#h.yt5odnzmfd6" id="h.yt5odnzmfd6

**perfmon**

traces

captures

event triggers

**taskman**

columns available

network tab always active

reg key

**Resource Monitor**

**Network**

Network Diagnostic wizard

net statistics workstation | server

domain network diagnostic command

**Event Log**

logs, filters, event triggers, forwarding events

Syslog

SNMP

Monitoring Apps:

MS MOM, HP SiteScope, Nagios? Splunk?

**Problem Report**

**Boot log**

**Crashes**

System Event Log, Event ID for a STOP error

See also Emergency Management Services for method, remote connection to monitor

**disable auto-reboot**

F8 on start up

Reg key

GUI

**Memory dump size configuration**

Sizes to choose from (none, Small 256 KB, Kernel)

Change with GUI

Change with registry

Change with boot.ini?

**Memory dump location**

``%SystemRoot%\MEMORY.DMP``

``%SystemRoot%\Minidump``

Overwrite any existing file or not?

Tool to analyze memory dumps

``nirsoft [http://nirsoft.net/utils/blue\_screen\_view.html](http://technet.microsoft.com/en-us/library/cc772829\(WS.10\).aspx)``

sysinternals and others?

**Dr. Watson**

**Debug files**

When you need them

Where they are to be installed

Where to get them

**Services Triggers on failures**

**Event Log triggers**

Uses the scheduled tasks to actually store, but can be created in Event Viewer with wizard?

#### ReadyBoost {#h.2b5x4j2hatjb" id="h.2b5x4j2hatjb

``ReadyBoost.sfcache _\<Flash drive>_\ReadyBoost.sfcache``

Cannot be enabled on Windows Server. Cannot be enabled when Windows is installed on an SSD drive.

#### Offline Files {#h.s645ab5txcss" id="h.s645ab5txcss

``C:\WINDOWS\csc``

"GoOfflineOnSlowLink"=dword:00000000

"SilentForcedAutoReconnect"=dword:00000001

Windows 2000-XP Cachemov.exe

**Troubleshooting**

How to reset

Issues with Folder Redirection GPO

#### CSC {#h.rrf4cjfvzktj" id="h.rrf4cjfvzktj

Certificate Services Client

Certificate Services Client is a core part of Microsoft® Windows® that manages certificate handling, like certificate enrollment, including auto-enrollment and credential roaming.

**DIMS**

This is the former name of credential roaming; it translates to Digital ID Management Service. Credential roaming is now part of the CSC. You may continue to see the acronym "DIMS” because it is used in Windows code such as in file names, registry hives, and the Eventlog.

#### Network {#h.lptrn5tkidnk" id="h.lptrn5tkidnk

``C:\Windows\System32\drivers\etc\hosts``

(Take ownership to edit file)

``C:\Windows\System32\ras``

Registry

``HKLM\System\CurrentControlSet\Services\Winsock``

``HKLM\System\CurrentControlSet\Services\Winsock2``

**Remote Access Server (RAS)**

rasdial.exe

Rasphone.pbk

Phonebook Administrator can be added to servers

**PXE Boot**

WMIC csproduct list /format

**MTU**

symptoms

**diagnostic**

ping command test

``ping -f -l 1024 \<IP Address>``

increase the packet size until the packets fail. Add 28 to get the correct MTU size.

DrTCP

registry key

**Network Tools**

**net.exe**

``net send depreciated with Windows ver (Vista?) or SP \_\_\_ when messenger service was removed/disabled``

MSG.EXE

``requires: HKLM\SYSTEM\CurrentControlSet\Control\TerminalServer\AllowRemoteRPC=1``

net view

net use and net use /delete

net statistics

net services

NET START and NET STOP can be used with any service if you provide the registry key name of display name.

Run 'ipconfig /flushdns' to flush the DNS cache, and 'nbtstat -RR' to flush the NetBIOS name cache.

**netsh.exe**

| **Command** | **Description**                                       |
| ----------- | ----------------------------------------------------- |
| ..          | Goes up one context level.                            |
| ?           | Displays a list of commands.                          |
| abort       | Discards changes made while in offline mode.          |
| add         | Adds a configuration entry to a list of entries.      |
| advfirewall | Changes to the \`netsh advfirewall' context.          |
| alias       | Adds an alias.                                        |
| brachcache  | Changes to the \`netsh branchcache' context.          |
| bridge      | Changes to the \`netsh bridge' context.               |
| bye         | Exits the program.                                    |
| commit      | Commits changes made while in offline mode.           |
| delete      | Deletes a configuration entry from a list of entries. |
| dhcp        | Changes to the \`netsh dhcp' context.                 |
| dhcpclient  | Changes to the \`netsh dhcpclient' context.           |
| dnsclient   | Changes to the \`netsh dnsclient' context.            |
| dump        | Displays a configuration script.                      |
| exec        | Runs a script file.                                   |
| exit        | Exits the program.                                    |
| firewall    | Changes to the \`netsh firewall' context.             |
| help        | Displays a list of commands.                          |
| http        | Changes to the \`netsh http' context.                 |
| interface   | Changes to the \`netsh interface' context.            |
| ipsec       | Changes to the \`netsh ipsec' context.                |
| lan         | Changes to the \`netsh lan' context.                  |
| mbn         | Changes to the \`netsh mbn' context.                  |
| namespace   | Changes to the \`netsh namespace' context.            |
| nap         | Changes to the \`netsh nap' context.                  |
| netio       | Changes to the \`netsh netio' context.                |
| offline     | Sets the current mode to offline.                     |
| online      | Sets the current mode to online.                      |
| p2p         | Changes to the \`netsh p2p' context.                  |
| popd        | Pops a context from the stack.                        |
| pushd       | Pushes current context on stack.                      |
| quit        | Exits the program.                                    |
| ras         | Changes to the \`netsh ras' context.                  |
| rpc         | Changes to the \`netsh rpc' context.                  |
| set         | Updates configuration settings.                       |
| show        | Displays information.                                 |
| trace       | Changes to the \`netsh trace' context.                |
| unalias     | Deletes an alias.                                     |
| wcn         | Changes to the \`netsh wcn' context.                  |
| wfp         | Changes to the \`netsh wfp' context.                  |
| winhttp     | Changes to the \`netsh winhttp' context.              |
| winsock     | Changes to the \`netsh winsock' context.              |
| wlan        | Changes to the \`netsh wlan' context.                 |

**3 netsh commands that may fix a broken Windows network**

Reset TCP/IP Network Stack

netsh int ip reset resetlog.txt

Reset Winsock using netsh. If you have a LSP that is corrupted and causing network connectivity problems, this command should repair that. Note that if you run this command, you may have to re-install several programs that had LSPs installed previously, such as Google Desktop Search, etc.

netsh winsock reset catalog

[http://support.microsoft.com/?kbid=811259](http://technet.microsoft.com/en-us/library/cc742124.aspx?kbid=811259)

Command-line management of Windows Firewall (netsh or netsh advance.. ?)

telnet client not installed by default starting with Windows 7 (include 2008?)

tftp client not installed by default

older versions of windows (NT?) had settings stored ? for services like ftp server (users, default directory), telnet server?, finger?

``\~ftpsvc\~.ckm Annotate FTP directory``

[http://support.microsoft.com/kb/141705](http://go.microsoft.com/fwlink/)

[http://windowsitpro.com/windows-server/jsi-tip-7142-registry-entries-telnet-server-service](http://windowsitpro.com/security/tools-troubleshoot-nap)

[http://windowsitpro.com/windows-server/jsi-tip-0390-registry-entries-ftp-service](http://technet.microsoft.com/en-us/library/cc742142.aspx)

[http://windowsitpro.com/windows/jsi-tip-2385-how-do-i-change-windows-2000-telnet-service-greeting-prompt-etc](http://technet.microsoft.com/en-us/library/cc742154.aspx)

``tlntadmn.exe, %SystemRoot%\system32\Login.cmd``

**Network Monitor**

Sources:

Now free install

SMS Service Pack

trial version

Microsoft Support provided version

Agent can be installed on client or server for remote collection

How to

**Simple TCP-IP Services**

motd file

``_systemroot_\System32\Drivers\Etc\Quotes. A sample quote file is installed with the Simple TCP/IP Services. If this file is missing, the quote service fails.``

**Novell NetWare Client**

available in Windows 2000-XP Pro?

**Enable debugging/logging**

Reg Key

add DWORD

``C:\Windows\Debug?\netlogon.log``

NetSetup.log

PASSWD.LOG

sammui.log?

**SNMP**

On Windows 2000, to collect disk information in perfmon, must also install … then run command...?

diskperf -yv

Most services have nothing to configure beyond the Startup type and Log on account. SNMP can edit Contact, Location, Traps, Security, Services (Physical, Applications, Datalink and subnetwork, Internet, and End-to-End)

**SNMP Registry Keys**

**SNMP Agent Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

SNMP management systems can request the contact person, system location, and network services for this computer by sending an SNMP request.

**SNMP Agent controls**

**Contact**: Provides a location for you to type the name of the person who administers this computer.

**Location**: Provides a location for you to type the physical location of the computer (for example, the building and office number).

**Service**: There are five service-based options from which to choose. SNMP agents provide information about the SNMP host to the SNMP management system:

* **Physical**: Specifies whether this computer manages physical devices, such as a hard disk.
* **Applications**: Specifies whether this computer uses any applications that send data using TCP/IP.
* **Datalink and subnetwork**: Specifies whether this computer manages a bridge.
* **Internet**: Specifies whether this computer is an IP gateway (router).
* **End-to-end**: Specifies whether this computer is an IP host.

**SNMP Security Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

SNMP provides security by using community names and SNMP authentication traps. An SNMP trap is an event notification message sent by the SNMP Trap service running on an SNMP host. The SNMP trap is sent to other SNMP hosts or to an SNMP management system, which are known as trap destinations.

You can restrict SNMP communications for the SNMP agent, allowing it to communicate with only a specific list of communities.

**SNMP Security controls**

**Send authentication trap**: Specifies whether to send an SNMP trap message to all trap destinations if this SNMP host receives an SNMP request from an SNMP host or community that is not listed on the **Security** tab. Authentication is the process of verifying that a host name or address is valid. When the SNMP agent receives a request that does not contain a known community name or that is not sent from a member of the acceptable hosts list, the SNMP agent sends an authentication trap message to one or more trap destinations, indicating the failure of authentication. This check box is selected by default.

**Accepted community names**: Lists the community names whose member SNMP hosts are authenticated to send SNMP requests to this computer. A community name acts as a password that is shared by one or more SNMP hosts.

Accepted community names are used to authenticate incoming messages only. To check outgoing messages, add the SNMP host as a trap destination on the **Traps** tab.

The SNMP Trap service requires at least one community name. **Public** is the default community name that is accepted in all SNMP implementations. You can add multiple community names, and delete or change the default community name. If an SNMP request is received from a community that is not on this list, the request will generate an authentication trap.

**Caution**

If you remove all the community names including the default name **Public**, SNMP will not respond to any community names presented.

* **Add**: Adds a community name and associated permissions to the list of communities that can send SNMP requests to this SNMP host. Use the following permission levels to specify how this SNMP host processes SNMP requests from a selected community:
  * **None**: Prevents this host from processing any SNMP requests.
  * **Notify**: Allows this host to send only SNMP traps to the community.
  * **Read Only**: Prevents this host from processing SNMP SET requests. SNMP managed objects have default values specified by the agent. Some applications may request to modify these values with the SNMP SET command.
  * **Read Write**: Allows this host to process SNMP SET requests.
  * **Read Create**: Allows this host to create new entries in the SNMP tables.
* **Edit**: Provides a dialog box to edit the selected community name and its permissions.
* **Remove**: Removes the selected community name from the list.

**Accept SNMP packets from any host**: Specifies that all SNMP packets from all SNMP hosts belonging to any community listed in **Accepted community names** are processed. No SNMP packets are rejected on the basis of the host name or IP address of the source host or the list of acceptable hosts. This check box is selected by default.

**Accept SNMP packets from these hosts**: Lists the SNMP hosts and SNMP management systems that can send SNMP requests to this SNMP host. This setting provides a higher level of security than use of a community name, which can contain a large group of hosts. You can add the names of any SNMP host or SNMP management system that belong to any community listed in **Accepted community names**. Only SNMP packets received from the hosts in this list are accepted. All other SNMP messages are rejected, and then authentication traps are sent.

* **Add**: Adds a specific SNMP host name or SNMP management system to the list of acceptable sources.
* **Edit**: Provides a dialog box to edit computer name or IP address of the selected SNMP host.
* **Remove**: Removes the selected SNMP host or SNMP management system from the list.

**SNMP Traps Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

An SNMP trap is an event notification message sent by the SNMP Trap service running on an SNMP host. The SNMP trap is sent to other SNMP hosts or to an SNMP management system, which are known as trap destinations.

If SNMP traps are required, one or more community names must be specified. Trap destinations can be specified as host names or IP addresses.

**SNMP Trap controls**

**Community name**: Provides a location for you to type or select a community name that you want used by the trap destinations. A community name acts as a password that is shared by one or more SNMP hosts. The SNMP agent can only send SNMP trap messages to SNMP hosts that use a known community name. Community names listed on the **Traps** tab are used only to authenticate outgoing SNMP trap messages. To authenticate all incoming SNMP trap messages, configure this SNMP host on the **Security** tab.

**Add to list**: Adds a typed community name to the **Community name** list.

**Remove from list**: Removes the selected community name from the **Community name** list.

**Trap destinations**: Lists trap destinations, which are SNMP management systems that receive SNMP trap messages from any SNMP host in the selected community.

**Add**: Adds an SNMP management system to the list of trap destinations for the selected community.

**Edit**: Provides a dialog box to edit the host name or IP address of the selected trap destination.

**Remove**: Removes the selected SNMP management system from the list of trap destinations for the selected community.

**Additional references**

For more information about SNMP, see[ ](http://technet.microsoft.com/en-us/library/cc755189.aspx?LinkId=66006)[Simple Network Management Protocol](http://technet.microsoft.com/en-us/library/cc742081.aspx?LinkId=66006) in TCP/IP Fundamentals for Windows in the Microsoft TechNet Technical Library at http://go.microsoft.com/fwlink/?LinkId=66006.

``mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/80366ac5-42bd-42e9-8169-83696087e091.htm``

``mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/e2c0fd7c-286c-4b02-a33b-8ed1780a681c.htm``

``mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/68219299-c666-4737-ae36-3de0b3dd76cb.htm``

**MIB (management information base)**

compile with mibcc.exe

[http://support.microsoft.com/kb/131776](http://support.microsoft.com/kb/131776)

``C:\Windows\System32\\``

accserv.mib

authserv.mib

dhcp.mib

ftp.mib

hostmib.mib

[http.mib](http.mib)

inetsrv.mib

ipforwd.mib

lmmib2.mib

mcastmib.mib

``mib\_ii.mib``

msft.mib

msipbtp.mib

msiprip2.mib

rfc2571.mib

smi.mib

wins.mib

| **File Name** | **Description** | **OID** |
| ------------- | --------------- | ------- |
| accserv.mib   |                 |         |
| authserv.mib  |                 |         |
| dhcp.mib      |                 |         |
| ftp.mib       |                 |         |
| hostmib.mib   |                 |         |
| http.mib      |                 |         |
| inetsrv.mib   |                 |         |
| ipforwd.mib   |                 |         |
| lmmib2.mib    |                 |         |
| mcastmib.mib  |                 |         |
| mib\_ii.mib   |                 |         |
| msft.mib      |                 |         |
| msipbtp.mib   |                 |         |
| msiprip2.mib  |                 |         |
| rfc2571.mib   |                 |         |
| smi.mib       |                 |         |
| wins.mib      |                 |         |

[http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4a168955-4982-44d5-8a18-e252d37a3557.mspx?mfr=true](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4a168955-4982-44d5-8a18-e252d37a3557.mspx?mfr=true)

**OID to detect the state of a windows service**

address of object identifier you can monitor Windows Services

No know OID for detecting hardware or hardware changes, use WMI. Script can pull list and then compare later for any changes. No known event trigger for hardware changes?

**Loopback Adapter**

purpose

how to install

how to install Windows 8

add hardware, manual, select Network, Microsoft

**Network Access Protection (NAP)**

What is it? is it 802.x? RADIUS? 3rd-party hardware?

What components are needed on server?

Is it a role or feature?

What components needed on client?

**Troubleshooting NAP**

[http://windowsitpro.com/security/tools-troubleshoot-nap](http://technet.microsoft.com/en-us/library/cc732010.aspx)

netsh

event log

log directory

Scripts

script location

network paths

Portal, sandbox, updates/rectify

scripts to detect Patches, Anti-Virus?

**Browsing Network**

net view

Explorer and shell extensions

Network Neighborhood (shortcuts appear under My Computer)

My Network Places

extra columns (description, MAC, IP)

PnP, Media Player sharing

Windows 7 (domain added make a difference?)

Name, Category, Workgroup, Network location, Discovery Method, MAC Address, IP Address

Category (Computer, Media Devices, Printers)

Discovery Method (WSD, NetBIOS, SSDP)

**Windows 7/Windows 2008R2 using shell extension**

Name, Type, Comments, Network Transport, Offline Status, Offline Availability

Type (Root, Computer, Domain, Share)

Network Transport (Microsoft Windows Network)

**Sites that can be pinged**

[www.google.com](http://technet.microsoft.com/en-us/library/cc731038.aspx)

8.8.8.8

8.8.4.4

``verified as of \[Publication Date]``

_space provided for writing notes_

_Suggest writing some addresses on back, inside cover_

#### Windows Media Center Shell {#h.yizyj8bzbqyu" id="h.yizyj8bzbqyu

``Tip: remember to put C:Windows\ehome``

in your Path under Computer -> System Properties -> Advanced -> Environment Variables

#### Startup and Logon Process {#h.4yvwy3wv5cst" id="h.4yvwy3wv5cst

Bitlocker involvement with boot?

Boot.ini

Bootsector file

UsrLogon.cmd

Autoexec

win.ini ?

_See Active Directory section for logon scripts_

_See Group Policy for User and Computer start and exit scripts_

StartUp group

**Run Registry Keys**

**Detail List**

**From Sysinternals LoadOrder:**

_Start Value (Image path)_

_Group name (Service)_

``Boot (system32\drivers)``

WdfLoadGroup (Wdf01000)

Boot Bus Extender (ACPI, msisadrv, pci, vdrvroot, partmgr)

System Bus Extender (volmgr, volmgrx, mountmgr)

SCSI Miniport (iaStor, amdxata)

FSFilter Infrastructure (FltMgr)

FSFilter Bottom (FileInfo)

Filter (CLFS, PxHlpa64)

Base (KSecDD, CNG, pcw)

``File System (Fs\_Rec)``

NDIS Wrapper (NDIS)

Cryptography (KSecPkg)

``PNP\_TDI (Tcpip)``

``\[Anti-Virus]``

(Disk)

PnP Filter (fvevol)

``\[hwpolicy]``

Network (Mup)

(PBADRV)

PnP Filter (rdyboost)

(spldr)

(volsnap)

``System (system32\drivers)``

SCSI CDROM Class (cdrom)

Base (Null, Beep)

Video Save (VgaSave, RDPCDD, RDPENCDD, RDPREFMP)

File system (Msfs, Npfs)

``PNP\_TDI (tdx, \[Anti-Virus], NetBT, AFD)``

NDIS (WfpLwf, Psched, nm3)

NetBIOSGroup (NetBIOS)

Extended base (Serial)

``\[Anti-Virus]``

(blbdrive)

Network (CSC, DfsC)

(discache, mssmbios, nsiproxy)

Network (rdbss)

(TermDD, Wanarpv6)

``Automatic (%SystemRoot%\system32)``

FSFilter Virtualization (luafv)

COM Infrastructure (DcomLaunch, RpcEptMapper, RpcSs)

Event Log (AMD External Events Utility, eventlog)

Audio Group (AudioEndpointBuilder, AudioSrv)

``ProfSvc\_Group (CscService, grpsvc, ProfSvc, SENS, Themes)``

UIGroup (UxSms)

``MS\_WindowsLocalValidation (SamSs)``

...

**From Sysinternals Autoruns:**

Boot Execute

``HKLM\System\CurrentControlSet\Control\Session Manager\BootExecute``

``HKLM\System\CurrentControlSet\Control\ServiceControlManagerExtension``

Services

``HKLM\System\CurrentControlSet\Services``

Logon

``HKLM\System\CurrentControlSet\Control\Terminal Server\Wds\rdpwd\StartupPrograms``

``HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Userinit``

``HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\VmApplet``

``HKLM\Software\Microsoft\Windows\CurrentVersion\Group Policy\Scripts\Startup``

``HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Shell``

``HKLM\SYSTEM\CurrentControlSet\Control\SafeBoot\AlternateShell``

``HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run``

``HKLM\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Run``

``C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup``

``C:\Users\Username\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup``

``HKCU\Software\Microsoft\Windows\CurrentVersion\Run``

``HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce``

Sidebar Gadgets

``C:\Users\Username\AppData\Local\Microsoft\Windows Sidebar\Settings.ini``

Scheduled Tasks

**Services normally running**

| **Image Name**            | **Description**                                       | **Command Line**                                                                                                                                                                                                                                                    |
| ------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| System                    | NT Kernel & System                                    | C:\Windows\system32\ntoskrnl.exe                                                                                                                                                                                                                                    |
| smss.exe                  | Windows Session Manager                               | \SystemRoot\System32\smss.exe                                                                                                                                                                                                                                       |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k DcomLaunch                                                                                                                                                                                                                       |
| csrss.exe                 | Client Server Runtime Process                         | %SystemRoot%\system32\csrss.exe ObjectDirectory=\Windows SharedSection=1024,20480,768 Windows=On SubSystemType=Windows ServerDll=basesrv,1 ServerDll=winsrv:UserServerDllInitialization,3 ServerDll=winsrv:ConServerDllInitialization,2 ServerDll=sxssrv,4 ProfileC |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k RPCSS                                                                                                                                                                                                                            |
| wininit.exe               | Windows Start-Up Application                          | wininit.exe                                                                                                                                                                                                                                                         |
| csrss.exe                 | Client Server Runtime Process                         | %SystemRoot%\system32\csrss.exe ObjectDirectory=\Windows SharedSection=1024,20480,768 Windows=On SubSystemType=Windows ServerDll=basesrv,1 ServerDll=winsrv:UserServerDllInitialization,3 ServerDll=winsrv:ConServerDllInitialization,2 ServerDll=sxssrv,4 ProfileC |
| winlogon.exe              | Windows Logon Application                             | winlogon.exe                                                                                                                                                                                                                                                        |
| services.exe              | Services and Controller app                           | C:\Windows\system32\services.exe                                                                                                                                                                                                                                    |
| lsass.exe                 | Local Security Authority Process                      | C:\Windows\system32\lsass.exe                                                                                                                                                                                                                                       |
| lsm.exe                   | Local Session Manager Service                         | C:\Windows\system32\lsm.exe                                                                                                                                                                                                                                         |
| atiesrxx.exe              | AMD External Events Service Module                    | C:\Windows\system32\atiesrxx.exe                                                                                                                                                                                                                                    |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted                                                                                                                                                                                                    |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k regsvc                                                                                                                                                                                                                           |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted                                                                                                                                                                                                     |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k netsvcs                                                                                                                                                                                                                          |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k GPSvcGroup                                                                                                                                                                                                                       |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LocalService                                                                                                                                                                                                                     |
| atieclxx.exe              | AMD External Events Client Module                     | atieclxx                                                                                                                                                                                                                                                            |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k NetworkService                                                                                                                                                                                                                   |
| spoolsv.exe               | Spooler SubSystem App                                 | C:\Windows\System32\spoolsv.exe                                                                                                                                                                                                                                     |
| upeksvr.exe               | Fingerprint Server Process for Vista                  | "C:\Program Files\Common\SPBA\upeksvr.exe"                                                                                                                                                                                                                          |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LocalServiceAndNoImpersonation                                                                                                                                                                                                   |
| snmp.exe                  | SNMP Service                                          | C:\Windows\System32\snmp.exe                                                                                                                                                                                                                                        |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork                                                                                                                                                                                                            |
| armsvc.exe \*32           | Adobe Acrobat Update Service                          | "C:\Program Files (x86)\Common Files\Adobe\ARM\1.0\armsvc.exe"                                                                                                                                                                                                      |
| dwm.exe                   | Desktop Window Manager                                | "C:\Windows\System32\Dwm.exe"                                                                                                                                                                                                                                       |
| mDNSResponder.exe         | Bonjour Service                                       | "C:\Program Files\Bonjour\mDNSResponder.exe"                                                                                                                                                                                                                        |
| inetinfo.exe              | Internet Information Services                         | C:\Windows\system32\inetsrv\inetinfo.exe                                                                                                                                                                                                                            |
| IPROSetMonitor.exe        | Intel® PROSet Monitoring Service                      | C:\Windows\system32\IPROSetMonitor.exe                                                                                                                                                                                                                              |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k HPZ12                                                                                                                                                                                                                            |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k ipripsvc                                                                                                                                                                                                                         |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k HPZ12                                                                                                                                                                                                                            |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k LPDService                                                                                                                                                                                                                       |
| TCPSVCS.EXE               | TCP/IP Services Application                           | C:\Windows\System32\tcpsvcs.exe                                                                                                                                                                                                                                     |
| taskhost.exe              | Host Process for Windows Tasks                        | "taskhost.exe"                                                                                                                                                                                                                                                      |
| conhost                   | Console Windows Host                                  | \\??\C:\Windows\system32\conhost.exe "12270050711036878941764404406-1950549039-509943657-6949245256654769161811869455                                                                                                                                               |
| wlcrasvc.exe              | Windows Live Mesh Remote Desktop Service              | "C:\Program Files\Windows Live\Mesh\wlcrasvc.exe"                                                                                                                                                                                                                   |
| WLIDSVC.EXE               | Microsoft® Windows Live ID Service                    | "C:\Program Files\Common Files\Microsoft Shared\Windows Live\WLIDSVC.EXE"                                                                                                                                                                                           |
| SearchIndexer.exe         | Microsoft Windows Search Indexer                      | C:\Windows\system32\SearchIndexer.exe /Embedding                                                                                                                                                                                                                    |
| OSPPSVC.EXE               | Microsoft Office Software Protection Platform Service | "C:\Program Files\Common Files\Microsoft Shared\OfficeSoftwareProtectionPlatform\OSPPSVC.EXE"                                                                                                                                                                       |
| WLIDSVCM.EXE              | Microsoft® Windows Live ID Service Monitor            | WLIDSvcM.exe 3260                                                                                                                                                                                                                                                   |
| svchost.exe               | Host Process for Windows Services                     | C:\Windows\system32\svchost.exe -k NetworkServiceNetworkRestricted                                                                                                                                                                                                  |
| mobsync.exe               | Microsoft Sync Center                                 | C:\Windows\System32\mobsync.exe -Embedding                                                                                                                                                                                                                          |
| PresentationFontCache.exe | PresentationFontCache.exe                             | C:\Windows\Microsoft.Net\Framework64\v3.0\WPF\PresentationFontCache.exe                                                                                                                                                                                             |
| svchost.exe               | Host Process for Windows Service                      | C:\Windows\system32\svchost.exe -k SDRSVC                                                                                                                                                                                                                           |
| csrss.exe                 | Client Server Runtime Process                         | %SystemRoot%\system32\csrss.exe ObjectDirectory=\Windows SharedSection=1024,20480,768 Windows=On SubSystemType=Windows ServerDll=basesrv,1 ServerDll=winsrv:UserServerDllInitialization,3 ServerDll=winsrv:ConServerDllInitialization,2 ServerDll=sxssrv,4 ProfileC |
| splwow64.exe              | Print driver host for 32bit applications              | C:\Windows\splwow64.exe 12288                                                                                                                                                                                                                                       |
| WmiPrvSE.exe              | WMI Provider Host                                     | C:\Windows\system32\wbem\wmiprvse.exe                                                                                                                                                                                                                               |
| svchost.exe               | Host Process for Windows Service                      | C:\Windows\system32\svchost.exe -k imgsvc                                                                                                                                                                                                                           |
| explorer.exe              | Windows Explorer                                      | C:\Windows\explorer.exe /factory,{75dff2b7-6936-4c06-a8bb-676a7b00b24b} -Embedding                                                                                                                                                                                  |
| vds.exe                   | Virtual Disk Service                                  | C:\Windows\System32\vds.exe                                                                                                                                                                                                                                         |
| dinotify.exe              | Windows Device Installation                           | "C:\Windows\System32\dinotify.exe" pnpui.dll,SimplifiedDINotification                                                                                                                                                                                               |

Services can be tagged with various startup types of classes.

``HKLM\SYSTEM\CurrentControlSet\services``

``CurrentControlSet\Control\ServiceGroupOrder``

DWORD Start, Type

| Name                      |   | Start in Safe Mode? | Can run in Safe Mode? | Registry value       | Availability Type |
| ------------------------- | - | ------------------- | --------------------- | -------------------- | ----------------- |
| Boot                      |   |                     |                       | 0                    | Drivers           |
|                           |   |                     |                       | 1                    | Drivers           |
| Automatic                 |   |                     |                       | 2                    | Services          |
| Automatic (Delayed Start) |   |                     |                       | 2 (different Type ?) | Services          |
| Manual                    |   |                     |                       | 3                    | Services          |
| Disabled                  |   |                     |                       | 4                    | Drivers,Services  |

Error Control and other entries [http://support.microsoft.com/kb/103000](http://en.wikipedia.org/wiki/Cmd.exe)

Error Type value, If error, can OS startup proceed?

See Install Apps in Safe Mode for allowing installs in safe mode

``HKLM\SYSTEM\CurrentControlSet\Control\SafeBoot\Minimal\MSIServer``

**Order of preference of file extensions for execution**

,.EXE, .COM, .BAT, .CMD, .PIF ...

Found in Registry key

backward compatibility in WIN.INI ?

Environmental variable

PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC

**Vulnerabilities, Malware, Virus**

Another list of files Microsoft deems risky is the Blocked Outlook Attachments list.

Due to the way the Windows operating system parses names with spaces, a first match can be abused to execute a planted program.

``C:\Program.exe``

Stealthy places to hide executables or triggers

[https://isc.sans.edu/diary/Wipe+the+drive!++Stealthy+Malware+Persistence+-+Part+4/15460](https://isc.sans.edu/diary/Wipe+the+drive!++Stealthy+Malware+Persistence+-+Part+4/15460)

**Reassociate .EXE file extension**

If double-click on shortcut, or single click on start menu won’t open, try right-click Open

How to repair .EXE (.LNK?) after hijack by malware

``What the EXE registry key looks like (CLASSES ROOT exefile ?), HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\\.exe\OpenWithList``

copy an EXE to .COM to run a program

SCRNSVR.EXE

replace the screen saver with CMD.EXE to get a command prompt with system-level privileges.

Scheduled Tasks

plant a task to open CMD interactive running in System context

Test anti-virus by using the EICAR.com file.

``X 5 O ! P % @ A P \[ 4 \ P Z X 5 4 ( P ^ ) 7 C C ) 7 } $``

E I C A R - S T A N D A R D - A N T I V I R U S - T E S T - F I L E !

``$ H + H \*``

#### PowerShell {#h.ji072fdo4adz" id="h.ji072fdo4adz

**PowerShell ISE**

``$Profile C:\Users\\_Username_\Documents\WindowsPowerShell\Microsoft.PowerShell\_profile.ps1``

``PSModule... env var. C:\Windows\system32\WindowsPowerShell\v1.0\Modules\\``

signing PowerShell scripts can be done with Digital Certificate for VBA Projects

``C:\Windows\System32\WindowsPowerShell\v1.0\Modules>tree``

Folder PATH listing for volume OS

Volume serial number is A23D-B9F3

C:.

├───FailoverClusters

│ ├───en

│ ├───en-US

│ └───zh-TW

├───GroupPolicy

│ ├───de-DE

│ ├───en-US

│ └───zh-TW

├───NetworkLoadBalancingClusters

│ ├───de

│ ├───de-DE

│ ├───en

│ ├───en-US

│ └───zh-TW

├───PSDiagnostics

├───TroubleshootingPack

│ └───en-US

└───WebAdministration

└───en-US

``C:\Windows\System32\WindowsPowerShell\v1.0\Modules>``

**file list**

GroupPolicy.format.ps1xml

GroupPolicy.psd1

Microsoft.GroupPolicy.Commands.dll-Help.xml

...

bin location for v1 - v3

``C:\Windows\System32\WindowsPowerShell\v1.0\\``

PowerShell 3.0 Task Scheduler storage folder for job definitions

``C:\Users\\_\<UserName>_\Appdata\Local\Microsoft\Windows\PowerShell\ScheduledJobs``

Import and Export http://www.petri.co.il/export-import-powershell-scheduled-jobs.htm

``HKLM\software\microsoft\powershell\1\shellids\Microsoft.powershell``

[http://www.trainsignal.com/blog/jeff-hicks-powershell-challenge-day-4-final-day](http://www.trainsignal.com/blog/jeff-hicks-powershell-challenge-day-4-final-day)

**PowerShell-based Administrative Tools**

see also the Remote section above?

Windows PowerShell Modules

``%SystemRoot%\system32\WindowsPowerShell\v1.0\powershell.exe -NoExit -ImportSystemModules``

Active Directory Module for Windows PowerShell

``%windir%\system32\WindowsPowerShell\v1.0\powershell.exe -noexit -command import-module ActiveDirectory``

Exchange Management Shell

``C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -noexit -command ". 'C:\Program Files\Microsoft\Exchange Server\V14\bin\RemoteExchange.ps1'; Connect-ExchangeServer -auto"``

``C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -noexit -command ". 'C:\Program Files\Microsoft\Exchange Server\V14\bin\RemoteExchange.ps1'; Connect-ExchangeServer -ServerFQDN Exchange.Domain.com"``

Can also be run in ISE

``[http://technet.microsoft.com/en-us/library/dd297932%28v=exchg.141%29.aspx](http://technet.microsoft.com/en-us/library/cc742041.aspx)``

iSCSI management cmdlets for Windows PowerShell

**PowerShell Pack**

PowerShell Pack is available as part of the Windows 7 Resource Kit.

DotNet Explore loaded types, find commands that can work with a type, and explore how you can use PowerShell, DotNet and COM together

FileSystem Monitor files and folders, check for duplicate files, and check disk space

IsePack Supercharge your scripting in the Integrated Scripting Environment with over 35 shortcuts

PSCodeGen Generates PowerShell scripts, C# code, and P/Invoke

PSImageTools Convert, rotate, scale, and crop images and get image metadata

PSRSS Harness the FeedStore from PowerShell

PSSystemTools Get Operating System or Hardware Information

PSUserTools Get the users on a system, check for elevation, and start-processaadministrator

TaskScheduler List scheduled tasks, create or delete tasks

WPK Create rich user interfaces quickly and easily from Windows PowerShell. Think HTA, but easy. Over 600 scripts to help you build quick user interfaces

**Desired State Configuration (DSC)**

Uses PowerShell applied by GPO to set and maintain system settings and configuration. (Requires Windows 8 and Server 2012)

#### Desktop Themes {#h.38xy6wy5k3lf" id="h.38xy6wy5k3lf

**Personalize Control Panel GPO**

Path to Visual Style:

To select Aero type:

``%windir%\resources\Themes\Aero\aero.msstyles``

To select a different visual style, type:

``ie: \\\\\<server>\share\Corp.msstyles``

To select Windows Classic, leave the box

above blank and enable this setting

``C:\Users\\\<UserName>\AppData\Microsoft\Windows\\...Themes?``

``C:\Windows\Resources``

``C:\Windows\Web\Wallpaper``

``C:\Windows\Cursors``

``C:\Windows\Media``

**Change Your Picture**

The picture you choose will appear on the Welcome screen and on the Start menu.

``C:\ProgramData\Microsoft\User Account Pictures\Default Pictures\\``

``C:\ProgramData\Microsoft\User Account Pictures\Username.dat``

``C:\ProgramData\Microsoft\User Account Pictures\User.bmp``

**Icons**

``C:\Windows\system32\url.dll``

``C:\Windows\System32\explorer.exe (C:\Windows\explorer.exe)``

``C:\Windows\System32\moricons.dll``

``C:\Windows\System32\shell32.dll``

``C:\Windows\System32\imageres.dll``

``C:\Program Files\Internet Explorer\iexplore.exe``

pifmgr.dll

accessibilitycpl.dll

ddores.dll

gameux.dll

mmcndmg?

mmres.dll

netcenter.dll

netshell?

networkexplorer.dll

pnidui.dll

sensorscpl.dll

setupapi.dll

wmploc?

wpdshext.dll

**Wallpaper**

IE

``C:\Users\\_UserName_\AppData\Roaming\Microsoft\Internet Explorer\Internet Explorer Wallpaper.bmp``

#### Out-of-Box Experience {#h.dn9tu1me6fvq" id="h.dn9tu1me6fvq

**First boot background music**

``C:\WINDOWS\system32\oobe\images\title.wma``

**Reset Windows back to First-boot**

``C:\Windows\System32\sysprep\sysprep.exe``

USAGE: sysprep.exe \[/quiet] \[/generalize] \[/audit | /oobe] \[/reboot | /shutdown | /quit] \[/unattend:\<filename>]

If no command-line arguments are provided, a graphical user interface is used to select the desired mode of sysprep operation.

#### Deploying Windows {#h.bvne4mhxkpgs" id="h.bvne4mhxkpgs

Deploying is also in the Server Features area

RIS, WIM

**OEM folder**

**answer file**

#### Windows Upgrade {#h.fp1pnt29yzyp" id="h.fp1pnt29yzyp

``C:\Users\Username\AppData\Local\Apps\Windows 7 USB DVD Download Tool\\``

``C:\Windows\System32\migwiz.lnk %windir%\system32\migwiz\migwiz.exe``

``C:\Windows\System32\migwiz\migwiz.exe``

User State Migration Tool (USMT)

3rd-party

**Windows 8 Upgrade Assistant**

``C:\ESD\Windows\Sources``

**Folders created from upgrade process**

``C:\Windows.old\[2]``

``C:\Windows.old\Documents and Settings``

``C:\Windows.old\Program Files``

``C:\Windows.old\Windows``

``C:\Windows.old\\?``

**Windows 8.1 Update**

[http://support.microsoft.com/kb/2919355](http://technet.microsoft.com/en-us/library/cc742070.aspx)

``\[April 2014]``

#### Windows Activation {#h.phwfv5lu9ajc" id="h.phwfv5lu9ajc

see also volume activation in another section (under domain, volume activation tools?)

**Windows Activation Utilities**

slmgr.vbs

slui.exe

slmgr.vbs /ipk XXXXX-XXXXX-XXXXX-XXXXX-XXXXX

slmgr.vbs /ato

**Windows Activation Client**

slui.exe 3 change product key (require elevated command prompt?) or activate Enterprise edition

slui.exe 4 manually perform telephone activation

**Registry Keys**

``HKLM\SYSTEM\WPA``

``HKLM\Software\Microsoft\Windows\CurrentVersion\Setup\OOBE\MediaBootInstall``

**Software Licensing Management Tool**

**slmgr.vbs**

[https://social.technet.microsoft.com/forums/windows/en-US/ae88055e-8484-4580-99e8-80af956da67d/change-mak-to-kms-via-slmgr-upk](http://msdn2.microsoft.com/en-us/library/ms984439.aspx)

MGATool

[http://go.microsoft.com/fwlink/?linkid=52012](http://msdn2.microsoft.com/en-us/library/ms984439.aspx?linkid=52012)

KMS troubleshooting

``[http://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx](http://technet.microsoft.com/en-us/library/cc786105\(v=ws.10\).aspx)``

#### Windows Updates {#h.i1j7n0ux0g6y" id="h.i1j7n0ux0g6y

``C:\Windows\\$NTUninstallKB_nnnnnnn_$``

``C:\Windows\ie8``

``C:\Windows\\$hf\_mig$``

wuauclt /detectnow

chain updates

More command line switches?

**slipstream updates**

See also Deployment?

How to slipstream hotfixes that replace pre-existing driver files

[http://support.microsoft.com/kb/814847](http://support.microsoft.com/kb/814847)

3rd party tools

``http://en.wikipedia.org/wiki/List\_of\_remastering\_software``

nLite

RT Se7ev Lite

Autopatcher

RyanVM

#### Install/Uninstall cache {#h.xasz4mskijht" id="h.xasz4mskijht

``? C:\WINDOWS\Installer\[3] is this for programs or patches?``

``C:\MSOCache\All Users\\``

``C:\Windows\Downloaded Installations\\{``

``Web Platform Installer? \<UserName>\AppData\Local\Microsoft\WebSetup``

(MSOCache mentioned elsewhere)

**Example**

**msiexec.exe**

``msiexec /i %LogonServer%\netlogon\PSTCaptureAgent.msi``

common setup.exe switches

see below

msizap for uninstall

**Install apps in safe mode**

``HKLM\SYSTEM\CurrentControlSet\Control\SafeBoot\Minimal\\``

and/or

``HKLM\SYSTEM\CurrentControlSet\Control\SafeBoot\Network\MSIServer``

``REG\_SZ MSIServer=Service``

``REG ADD “HKLM\SYSTEM\CurrentControlSet\Control\SafeBoot\Minimal\MSIServer” /VE /T REG\_SZ /F /D "Service" && net start msiserver``

See also 3rd-arty app SafeMSI

HotFixes in Safe mode

Windows Update Service (Wuauserv)

#### Scheduled Tasks {#h.wx4y24ic2ga3" id="h.wx4y24ic2ga3

``C:\Windows\System32\Tasks``

AT registry key:

**at.exe**

Uses Schedule service

The syntax for specifying days is:

M Tu W Th F Sa Su

**schtasks.exe**

use /V1 to create task on remote XP computer from Vista or above.

#### Windows Backup {#h.7vaxonnn2u22" id="h.7vaxonnn2u22

MediaID.bin

GlobalCatalog.wbcat

**NTBackup**

For use as a scheduled task

Command line switches

``Selection Scripts (\*.bks)``

``C:\Documents and Settings\\%Username%\Local Settings\Application Data\Microsoft\Windows NT\NTBackup\data``

Log Results

``C:\Documents and Settings\\%Username%\Local Settings\Application Data\Microsoft\Windows NT\NTBackup\data\backup01.log``

``Files excluded for all users by default\[4]:``

| **Filename**                                                                          | **Application**                                                                                      |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| \\\*.crmlog                                                                           | Microsoft Writer (Bootable State)                                                                    |
| \hiberfil.sys                                                                         | Power Management                                                                                     |
| \Pagefile.sys                                                                         | Memory Page File                                                                                     |
| \System Volume Information\\\*.{7cc467ef-6865-4831-853f-2a4817fd1bca}ALT              | VSS Service Alternate DB                                                                             |
| \System Volume Information\\\*.{7cc467ef-6865-4831-853f-2a4817fd1bca}DB               | VSS Service DB                                                                                       |
| \System Volume Information\\\*{3808876B-C176-4e48-B7AE-04046E6CC752}                  | VSS Default Provider                                                                                 |
| \System Volume Information\DFSR\\\*                                                   | DFSR Database                                                                                        |
| \System Volume Information\MountPointManagerRemoteDatabase                            | Mount Manager                                                                                        |
| C:\Documents and Settings\All Users\Application Data\Microsoft\Network\Downloader\\\* | BITS\_metadata                                                                                       |
| C:\Documents and Settings\All Users\DRM\\\*                                           | DRM                                                                                                  |
| C:\Documents and Settings\\%Username%\index.dat                                       | Internet Explorer                                                                                    |
| C:\Documents and Settings\\%Username%\Local Settings\Temp\2\\\*                       | Temporary Files                                                                                      |
| C:\Windows\csc\\\*                                                                    | Client Side Cache                                                                                    |
| C:\WINDOWS\Debug\\\*                                                                  | Winlogon debug                                                                                       |
| C:\WINDOWS\netlogon.chg                                                               | Netlogon                                                                                             |
| C:\WINDOWS\Registration\\\*.clb                                                       | Microsoft Writer (Bootable State)                                                                    |
| C:\WINDOWS\repair\asr.err                                                             | ASR Error File                                                                                       |
| C:\WINDOWS\repair\asr.log                                                             | ASR Log File                                                                                         |
| C:\WINDOWS\SoftwareDistribution\\\*                                                   | SUS Client                                                                                           |
| C:\WINDOWS\system32\CatRoot2\\\*                                                      | Catalog Database                                                                                     |
| C:\WINDOWS\system32\LServer\\\*                                                       | TermServLicensing                                                                                    |
| C:\WINDOWS\system32\MSDtc\MSDTC.LOG                                                   | MS Distributed Transaction Coordinator                                                               |
| C:\WINDOWS\system32\MSDtc\trace\dtctrace.log                                          | MS Distributed Transaction Coordinator                                                               |
| C:\WINDOWS\Tasks\schedlgu.txt                                                         | Task Scheduler                                                                                       |
| \<drive:path>\DfsrPrivate\\\*                                                         | DFSR Replicated Folder {2AB0DFB4-7B9C-4EAE-A77C-1AFF95B5EE9A}-{8AE2FC0A-37BA-4801-A8A6-0A69DF4502EE} |
| \<drive:path>\DfsrPrivate\ConflictedAndDeleted\\\*                                    | DFSR Replicated Folder {2AB0DFB4-7B9C-4EAE-A77C-1AFF95B5EE9A}-{8AE2FC0A-37BA-4801-A8A6-0A69DF4502EE} |
| \<drive:path>\DfsrPrivate\Staging\\\*                                                 | DFSR Replicated Folder {2AB0DFB4-7B9C-4EAE-A77C-1AFF95B5EE9A}-{8AE2FC0A-37BA-4801-A8A6-0A69DF4502EE} |
| S\system32\MSDtc\trace\dtctrace.log                                                   | DRM                                                                                                  |

``HKLM\SYSTEM\CurrentControlSet\Control\BackupRestore\FilesNotToBackup``

``HKLM\SYSTEM\CurrentControlSet\Control\BackupRestore\KeysNotToRestore``

``HKLM\SYSTEM\CurrentControlSet\Control\BackupRestore\FilesNotToSnapshot``

Is there also a HKCU key?

**Windows Server Backup**

``Wbadmin replaces ntbackup\[5]``

[http://technet.microsoft.com/en-us/library/cc770340.aspx](http://technet.microsoft.com/en-us/library/cc770340.aspx)

| **Subcommand**                                                                                                                | **Description**                                                                                                                                                                                                                                                                                    |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Wbadmin enable backup                                                                                                         | <p>Configures and enables a daily backup schedule.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                         |
| Wbadmin disable backup                                                                                                        | <p>Disables your daily backups.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                                            |
| Wbadmin start backup                                                                                                          | Runs a one-time backup. If used with no parameters, uses the settings from the daily backup schedule.                                                                                                                                                                                              |
| Wbadmin stop job                                                                                                              | Stops the currently running backup or recovery operation.                                                                                                                                                                                                                                          |
| Wbadmin get versions                                                                                                          | Lists details of backups recoverable from the local computer or, if another location is specified, from another computer.                                                                                                                                                                          |
| [Wbadmin get items](http://msdn2.microsoft.com/en-us/library/ms984439.aspx)                                                   | Lists the items included in a specific backup.                                                                                                                                                                                                                                                     |
| [Wbadmin start recovery](http://technet.microsoft.com/en-us/library/cc753116.aspx)                                            | <p>Runs a recovery of the volumes, applications, files, or folders specified.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                              |
| [Wbadmin get status](http://technet.microsoft.com/en-us/library/cc771903.aspx)                                                | Shows the status of the currently running backup or recovery operation.                                                                                                                                                                                                                            |
| [Wbadmin get disks](http://www.google.com/)                                                                                   | <p>Lists disks that are currently online.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                                  |
| [Wbadmin start systemstaterecovery](http://en.wikipedia.org/wiki/Regedit)                                                     | <p>Runs a system state recovery.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                                           |
| [Wbadmin start systemstatebackup](http://blogs.technet.com/b/askperf/archive/2010/03/02/windows-7-where-are-my-printers.aspx) | <p>Runs a system state backup.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                                             |
| [Wbadmin delete systemstatebackup](http://www.undocprint.org/formats/winspool/spl)                                            | <p>Deletes one or more system state backups.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                                                                                                                               |
| [Wbadmin start sysrecovery](http://technet.microsoft.com/en-us/library/cc731865.aspx)                                         | Runs a recovery of the full system (at least all the volumes that contain the operating system's state). _This subcommand applies only to Windows Server 2008, and it is only available if you are using the Windows Recovery Environment._                                                        |
| [Wbadmin restore catalog](http://technet.microsoft.com/en-us/library/cc742060.aspx)                                           | <p>Recovers a backup catalog from a specified storage location in the case where the backup catalog on the local computer has been corrupted.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p>                                                                              |
| [Wbadmin delete catalog](http://technet.microsoft.com/en-us/library/cc731038.aspx)                                            | <p>Deletes the backup catalog on the local computer. Use this command only if the backup catalog on this computer is corrupted and you have no backups stored at another location that you can use to restore the catalog.</p><p><em>This subcommand applies only to Windows Server 2008.</em></p> |

#### Fax {#h.pbyfyfrqt3za" id="h.pbyfyfrqt3za

``MSFax "C:\ProgramData\Microsoft\Windows NT\MSFax"``

Fax Printer

Fax Printer Port

How many modems does each OS support? (Win2k, Win2k3, Win 2k8, SBS)

#### OEM Branding {#h.wwy0nqh6y4fd" id="h.wwy0nqh6y4fd

``C:\Windows\Setup\scripts\\``

``C:\Windows\System32\oem``

See also Deployment, OEM

#### Printing {#h.k1vmmpaque47" id="h.k1vmmpaque47

``C:\Windows\System32\spool\PRINTERS``

Special Shell folder to view all printers in Windows 7 without them being consolidated by port.

If you have two printers with different settings (color/black-white, or default tray) and same port (USB or TCPIP)

{2227a280-3aea-1069-a2de-08002b30309d}

[http://blogs.technet.com/b/askperf/archive/2010/03/02/windows-7-where-are-my-printers.aspx](http://technet.microsoft.com/en-us/library/cc731094.aspx)

You will need the right PCL/PostScript viewer to read .spl files

[http://www.undocprint.org/formats/winspool/spl](http://technet.microsoft.com/en-us/library/cc772355.aspx)

``prnproc$ C:\Windows\system32\spool\PRTPROCS Printer Drivers``

``print$ C:\Windows\system32\spool\drivers Printer Drivers``

Windows Server 2003 R2 can manage printers as 2003 or 2003R2

``The R2 Print Management C:\WINDOWS\PMCSnap\printmanagement.msc``

findnetprinters.dll

fnprinters.com

fnprinters.exe

pmcsnap.DLL

ppcsnap.dll

printmanagement.msc

puiobj.DLL

pushprinterconnections.exe

**Stuck job**

You may have a print job stuck in the spool, or one that crashes the spool service.

1. Stop the print spool with (net stop spooler) if it is running
2. delete the spd file
3. Start the print spooler (net start spool)

``Print Spooler C:\Windows\System32\spool\PRINTERS``

``Printer Drivers C:\Windows\system32\spool\DRIVERS\x64\3\\``

``Inf Path C:\Windows\System32\DriverStore\FileRepository\\...\\...inf``

**UNC path for shared printer drivers**

``print$ C:\Windows\System32\spool\drivers``

**Terminal Server key fix for no/cannot set default printer**

``HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Device``

Forms

Ports

[http://technet.microsoft.com/en-us/library/cc771846.aspx](http://technet.microsoft.com/en-us/library/cc771846.aspx)

| **Command**                                                                                                                                      | **Description**                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| [Lpq](http://technet.microsoft.com/en-us/library/cc730696.aspx)                                                                                  | Displays the status of a print queue on a computer running Line Printer Daemon (LPD).                                                      |
| [Lpr](http://technet.microsoft.com/en-us/library/cc742050.aspx)                                                                                  | Sends a file to a computer or printer sharing device running the Line Printer Daemon (LPD) service in preparation for printing.            |
| [Net print](http://technet.microsoft.com/en-us/library/cc771976.aspx)                                                                            | Displays information about a specified printer queue, displays information about a specified print job, or controls a specified print job. |
| [Print](http://technet.microsoft.com/en-us/library/cc731623.aspx)                                                                                | Sends a text file to a printer.                                                                                                            |
| [Prncnfg.vbs](http://technet.microsoft.com/en-us/library/cc730914.aspx)                                                                          | Configures or displays configuration information about a printer.                                                                          |
| [Prndrvr.vbs](http://www.irongeek.com/i.php)                                                                                                     | Adds, deletes, and lists printer drivers.                                                                                                  |
| [Prnjobs.vbs](http://en.wikipedia.org/wiki/Cmd.exe)                                                                                              | Pauses, resumes, cancels, and lists print jobs.                                                                                            |
| [Prnmngr.vbs](http://technet.microsoft.com/en-us/library/cc731241.aspx)                                                                          | Adds, deletes, and lists printers or printer connections, in addition to setting and displaying the default printer.                       |
| [Prnport.vbs](http://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) | Creates, deletes, and lists standard TCP/IP printer ports, in addition to displaying and changing port configuration.                      |
| [Prnqctl.vbs](http://technet.microsoft.com/en-us/library/cc771131.aspx)                                                                          | Prints a test page, pauses or resumes a printer, and clears a printer queue.                                                               |
| [Pubprn.vbs](http://www.petri.co.il/filtering-and-custom-views-in-vista-event-viewer.htm)                                                        | Publishes a printer to the Active Directory directory service.                                                                             |
| [Rundll32 printui.dll,PrintUIEntry](https://computername:8098/)                                                                                  | Enables you to automate the installation and configuration of printers using scripts or the command prompt.                                |

``rundll32 printui.dll,PrintUIEntry /ga /c\\\machine /n\\\machine\printer /j"LanMan Print Services"``

``rundll32 printui.dll,PrintUIEntry /ga /n"\\\AppServer\OKI C530 Admin" /j"LanMan Print Services"``

**Backup or Migrate Printers**

Resource Kit? Tool to backup all drivers and shared printers to file and can restore or import them to another server/PC.

The Microsoft Printer Migrator (Printmig.exe) utility, included in Windows NT 4.0 Resource Kit Supplement 3

``%Systemroot%\System32\Spool\Pm\Pm.CAB``

Vista and later, Administrative Tools, Print Management. Right-click the Print server, choose Export printers to a file...

``C:\Windows\System32\spool\tools>printbrm.exe -?``

Error: A single mode must be selected!

Access the Backup Recovery Migration tool through a command line interface.

PrintBrm -B|R|Q \[-S \<server>] -F \<file> \[-D \<directory>] \[-O FORCE] \[-P ALL|ORIG] \[-NOBIN] \[-LPR2TCP] \[-C \<config file>] \[-NOACL] \[-?]

``\-B Backup the server to the specified file``

``\-R Restore the configuration in the file to the server``

``\-Q Query the server or the backup file``

``\-S \<server name> Target server``

``\-F \<file name> Target backup File``

``\-D \<directory> Unpack the backup file to (with -R) or repack a backup file from (with -B) the given directory``

``\-O FORCE Force overwriting of existing objects``

\-P ALL|ORIG Publish all printers in directory, or publish printers that were published originally

``\-NOBIN Omit the binaries from the backup``

``\-LPR2TCP Convert LPR ports to Standard TCP/IP ports on restore``

``\-C \<file name> Use the specified configuration file for BRM``

``\-NOACL Remove ACLs from print queues on restore``

``\-? Display this help``

``C:\Windows\System32\spool\tools>``

**Print Separator Page**

pcl.sep

pscript.sep

sysprint.sep

sysprtj.sep

[http://www.windowsnetworking.com/kbase/WindowsTips/WindowsXP/AdminTips/Network/SharedprinterseparatorpageforWindows2000andWindowsXP.html](http://technet.microsoft.com/en-us/library/cc753907.aspx)

| **File Name** | **Description** |
| ------------- | --------------- |
| pcl.sep       |                 |
| pscript.sep   |                 |
| sysprint.sep  |                 |
| sysprtj.sep   |                 |

**Sample PostScript file to test printer:**

**Troubleshooting Vista shared printer installation**

Add Local printer, local port, enter UNC path

#### Windows Wireless Config {#h.rf1lkh2esmia" id="h.rf1lkh2esmia

(Move to Networking?)

Registry key of remembered Wi-Fi connections

``HKLM\SOFTWARE\Microsoft\WZCSVC\Parameters\Interfaces ?``

Wireless setup disk config file

AUTORUN.INF

setupSNK.exe

``\SMRTNTKY\\``

``\DEVICE\\``

fcw.ico

MessageB.txt

WSETTING.TXT

WSETTING.WFC

#### Windows logon password {#h.34sklueb7143" id="h.34sklueb7143

**Windows password recovery disk**

**Credential Manager**

Back up vault

``Credential Backup Files (\*.crd)``

#### Encrypting File System {#h.l1u6dqphtt0n" id="h.l1u6dqphtt0n

Manage your file encryption certificates

rekeywiz.exe EFS REKEY wizard

#### ODBC {#h.mgj5021muc2a" id="h.mgj5021muc2a

folder path: DSN files

``registry: HKLM\SOFTWARE\ODBC\ODBC.INI``

also a user key

#### Windows update {#h.uv4v6warfqpm" id="h.uv4v6warfqpm

**command to trigger search for updates**

wuauclt.exe /detectnow (two other places in this document?)

**Sites to add to Internet Explorer Trusted Zone**

``URLs:\[6]``

``* https://\*.microsoft.com``
* https://download.windowsupdate.com
* https://update.microsoft.com/windowsupdate
``* http://\*.update.microsoft.com``
``* https://\*.update.microsoft.com``
* http://download.windowsupdate.com

Homegroup setup disk?

ICS (Internet Connection Sharing) setup disk?

Migration Wizard (i.e. XP to XP) (Migration mentioned elsewhere in this document? Upgrade Windows)

RegBack from Windows 2000 Server?

#### TWAIN {#h.bnu5zbmyy5s2" id="h.bnu5zbmyy5s2

``C:\Windows\twain\_32``

Registry:

#### Accessibility/Ease of Access {#h.cwdx4l9w5eyj" id="h.cwdx4l9w5eyj

Windows XP

Windows key+U

| press SHIFT key 5 times                     | Sticky Keys            | Press keyboard shortcuts (such as CTRL+ALT+DEL) one key at a time.                                                 |
| ------------------------------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------ |
| left ALT+left SHIFT+NUM LOCK                | Mouse Keys             | Use the numeric keypad to move the mouse around the screen.                                                        |
| hold down the NUM LOCK key for 5 seconds    | Toggle Keys            | Hear a tone when you press CAPS LOCK, NUM LOCK, or SCROLL LOCK.                                                    |
| hold down the right SHIFT key for 8 seconds | Filter Keys            | Ignore or slow down drief or repeated keystrokes and adjust keyboard repeat rates.                                 |
| left ALT+left SHIFT+PRINT SCREEN            | High Contrast theme    |                                                                                                                    |
| Windows key+ +                              | Magnifier              | Magnifier zooms in anywhere on the screen, and makes everything in that area larger.                               |
|                                             | Use speech recognition | Speak into a microphone to control the computer, open programs, and dictate text.                                  |
|                                             | Use On-Screen Keyboard | Type using the mouse or another pointing device such as a joystick by selecting keys from a picture of a keyboard. |
|                                             |                        | Activate a window by hovering over it with the mouse                                                               |
|                                             | Sound Sentry           | Turn on visual notifications for sounds                                                                            |
|                                             | Narrator               |                                                                                                                    |

Windows 7

snap windows

Prevent windows from being automatically arranged when moved to the edge of the screen.

Underline keyboard shortcuts and access keys has been moved to Make it easier to use keyboard shortcuts.

sethc.exe - Sticky Keys

Magnify.exe

Narrator.exe

**Registry keys to disable and prevent accidental activation.**

**How to turn off an accessibility feature that was accidently turned on**

Enable Java Access Bridge

Java Access Bridge, from Oracle, Inc. providing Assistive Technology access to Java applications

### Programs without icons or shortcuts {#h.7d98ixsg8utn" id="h.7d98ixsg8utn

32-bit vs 64-bit

Which apps run 32-bit as default on 64-bit installation?

ODBC, Media Player, IE

``odbcad32.exe %windir%\SysWOW64\odbcad32.exe``

``Problem Step Recorder C:\Windows\System32\PSR.exe and/or C:\Windows\SysWOW64``

``msconfig C:\Windows\System32 \[Win7] or ? \[WinXP]``

god-mode folder Everything.{ED7BA470-8E54-465E-825C-99712043E01C}

(Paths don’t work to launch program...)

``Reliability Monitor C:\Windows\explorer.exe /factory,{ceff45ee-c862-41de-aee2-a022c81eda92} -Embedding``

``Reliability Monitor - Shortcut search-ms:displayname=%20Search%20programs%20and%20files\&crumb=System.Generic.String%3Areli\&crumb=location:%3A%3A{DAF95313-E44D-46AF-BE1B-CBACEA2C3065}\View reliability history``

Problem Reports

``explorer shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\0\\::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageProblems``

To Make Documents as Default Folder to Open by Windows Explorer upon Launching

``%SystemRoot%\explorer.exe /n,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}``

To Make Computer as Default Folder to Open by Windows Explorer upon Launching

``%SystemRoot%\explorer.exe /n,::{450D8FBA-AD25-11D0-98A8-0800361B1103}``

``C:\Windows``

bfsvc.exe Boot File Servicing Utility

explorer.exe

fveupdate.exe BitLocker Drive Encryption Servicing Utility

HelpPane.exe Microsoft Help and Support

hh.exe Microsoft HTML Help Executable

notepad.exe

regedit.exe Registry Editor

splwow64.exe Print driver host for 32bit applications

system.ini

``twunk\_16.exe``

``twunk\_32.exe Twain.dll Client’s 32-Bit Thunking Server``

win.ini

winhlp32.exe

write.exe Windows Write

**Explorer.exe Command Line Syntax**

``%SystemRoot%\explorer.exe \[/n]\[/e]\[,/root],X,\[\[/Select],Y]``

X specifies the object, and optionally with sub-object Y. /e switch shows the left Windows Explorer tree view navigation pane together with the right pane in list view, while /n hides the left navigation pane. When the /root parameter is present, Explorer.exe will explore the root object (X) and objects belonging to X. On the other hand, when the /root switch is not present, Explorer.exe explores the object X, its children, and other Explorer objects as well. /Select switch puts the focus on a file or folder.

For example:

``%SystemRoot%\explorer.exe /N,%WinDir%\System32,/Select,%WinDir%\System32\Ping.exe``

``Command aboves will explore the \Windows\System32 folder and put the focus on the ping.exe program.``

#### MMC {#h.kzqvf7icqgpe" id="h.kzqvf7icqgpe

mmc.exe

mmc /a

``\[there is an MMC section under Remote access admin tools section]``

snap-ins (MSC)

| **Snap-in**                                     | **Filename**                           | **Description**                                                                                                                                                                                                                 | **Source**                     |
| ----------------------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| Active Directory Domains and Trusts             |                                        | You can use the Active Directory Domains and Trusts snap-in to manage Active Directory domains and trusts.                                                                                                                      |                                |
| Active Directory Schema                         |                                        | View and edit the Active Directory Schema                                                                                                                                                                                       |                                |
| Active Directory Sites and Services             |                                        | View and manage Sites and Services. Sites define the topology and schedules used for Active Directory Domain Services replication. Services permits administration of certain enterprise-wide Active Directory Domain Services. |                                |
| Active Directory Users and Computers            |                                        | Active Directory Users and Computers allows management of users, groups, organizational units, and all other AD DS objects.                                                                                                     |                                |
| ActiveX Control                                 |                                        | The ActiveX Control snap-in enables you to add an MMC node with a results view containing an ActiveX control.                                                                                                                   |                                |
| ADSI Edit                                       |                                        | A low level Active Directory Services Interface editor.                                                                                                                                                                         |                                |
| Authorization Manager                           |                                        | The Authorization Manager allows you to set role-based permissions for Authorization Manager-enabled applications.                                                                                                              |                                |
| Certificate Templates                           |                                        | The Certificate Templates snap-in allows you to create and manage certificate templates.                                                                                                                                        |                                |
| Certificates                                    |                                        | The Certificates snap-in allows you to browse the contents of the certificate stores for yourself, a service, or a computer.                                                                                                    |                                |
| Certification Authority                         |                                        | Allows you to configure certification authority properties and to manage certificates issued by this CA.                                                                                                                        |                                |
| Component Services                              |                                        | Component Services (COM+) management tool.                                                                                                                                                                                      |                                |
| Computer Management                             |                                        | Computer management and related system tools.                                                                                                                                                                                   |                                |
| Details Template Editor                         |                                        | Allows management of Exchange Server 2010 Details Templates.                                                                                                                                                                    |                                |
| Device Manager                                  |                                        | You can use Device Manager to view a list of hardware devices installed on your computer and set properties for each device.                                                                                                    |                                |
| DFS Management                                  |                                        | Manages DFS Namespaces and DFS Replication.                                                                                                                                                                                     |                                |
| DHCP                                            |                                        | The DHCP snap-in is used to configure and manage the Dynamic Host Configuration Protocol (DHCP) service.                                                                                                                        |                                |
| Disk Management                                 |                                        | Dynamic disk and volume management provided to Microsoft by VERITAS Software Corporation.                                                                                                                                       |                                |
| DNS                                             |                                        | You can use the DNS snap-in to administer a DNS server                                                                                                                                                                          |                                |
| Enterprise PKI                                  |                                        | The Enterprise PKI snap-in assists in the health monitoring and maintenance of an Enterprise PKI hierarchy.                                                                                                                     |                                |
| Event Viewer                                    |                                        | View monitoring and troubleshooting messages from windows and other programs.                                                                                                                                                   |                                |
| Exchange Server 2010                            |                                        | Allows management of all aspects of an Exchange system.                                                                                                                                                                         |                                |
| Failover Cluster Manager                        |                                        | Manages Windows Failover Clusters                                                                                                                                                                                               |                                |
| Failover Cluster Manager Host                   |                                        | This snap-in hosts extension snap-ins that are used for managing highly available cluster roles and features. Do not add to the MMC console manually.                                                                           |                                |
| File Server Resource Manager                    |                                        | Manages directory quotas, file screens, and storage reports for Windows file servers.                                                                                                                                           |                                |
| Folder                                          |                                        | The Folder snap-in adds a folder node to the tree. This can be used to organize your snap-in console.                                                                                                                           |                                |
| Group Policy Management                         |                                        | <p>© 2007 Microsoft Corporation. All rights reserved. This product is licensed.</p><p>Allows management of Group Policy across sites, domains, and organizational units within one or more forests.</p>                         | Is this the new one?           |
| Group Policy Management Editor                  |                                        | This snap-in allows you to edit Group Policy Objects which can be linked to a Site, Domain, or Organizational Unit in the Active Directory or stored on a computer.                                                             |                                |
| Group Policy Object Editor                      |                                        | This snap-in allows you to edit the local Group Policy Objects stored on a computer.                                                                                                                                            |                                |
| Group Policy Starter GPO Editor                 |                                        | This snap-in allows you to edit Group Policy Starter GPOs.                                                                                                                                                                      |                                |
| Hyper-V Manager                                 |                                        | Hyper-V Manager provides management access to your virtualization platform.                                                                                                                                                     |                                |
| Internet Information Services (IIS) 6.0 Manager |                                        | This snap-in administers the Microsoft Internet Information Services (IIS) 6.0                                                                                                                                                  |                                |
| Internet Information Services (IIS) Manager     |                                        | The IIS Manager allows you to manage the Web Application Server.                                                                                                                                                                |                                |
| IP Security Monitor                             |                                        | The IP Security Monitor snap-in is used to monitor the status of IP Security                                                                                                                                                    |                                |
| IP Security Policy Management                   |                                        | Internet Protocol Security (IPsec) Administration. Manage IPsec policies for secure communication with other computers.                                                                                                         |                                |
| Link to Web Address                             |                                        | The Link to Web Address snap-in enables you to add an MMC node with a Web page in the results view.                                                                                                                             |                                |
| Local Users and Groups                          |                                        | Manages Local Users and Groups                                                                                                                                                                                                  |                                |
| Microsoft Deployment Workbench                  |                                        | The Microsoft Deployment Workbench is used to assist with the deployment of Microsoft Windows.                                                                                                                                  |                                |
| NAP Client Configuration                        |                                        | Configures and manages NAP Client Configuration settings                                                                                                                                                                        |                                |
| Online Responder Management                     |                                        | Enables the configuration, monitoring and management of revocation checking services based on the OCSP protocol.                                                                                                                |                                |
| Performance Monitor                             |                                        | Performance Monitor                                                                                                                                                                                                             |                                |
| Print Management                                | C:\WINDOWS\PMCSnap\printmanagement.msc | Print Management is a Microsoft Management Console (MMC) snap-in that is used to manage print servers and printers.                                                                                                             | Win2003R2 & others             |
| Public Folder Management Console                |                                        | Allows management of Exchange Server 2010 public folders. © 2010 Microsoft Corporation. All rights reserved.                                                                                                                    | Exchange 2010 Server Tools\<?> |
| Queue Viewer                                    |                                        | Manage Exchange mail queues.                                                                                                                                                                                                    |                                |
| Remote Desktop Services Manager                 |                                        | Manage Remote Desktop Services sessions                                                                                                                                                                                         |                                |
| Remote Desktops                                 |                                        | Allows you to connect to remote computers                                                                                                                                                                                       |                                |
| Resultant Set of Policy                         |                                        | This snap-in allows you to view the Resultant Set of Policy for a user on a machine. The snap-in can be used to view policy that has been applied as well as predict what policy would be applied to a user on a machine.       |                                |
| Scan Management                                 |                                        | Scan Management is a Microsoft Management Console (MMC) snap-in that you can use to manage scan servers, scan processes, and scanners.                                                                                          |                                |
| Security Configuration and Analysis             |                                        | Security Configuration and Analysis is an MMC snap-in that provides security configuration and analysis for Windows computers using security template files.                                                                    |                                |
| Security Templates                              | where are the templates?               | Security Templates is an MMC snap-in that provides editing capabilities for security template files.                                                                                                                            |                                |
| Server Manager                                  |                                        | Get an overview of the status of this server, perform top management tasks, and add or remove server roles and features.                                                                                                        |                                |
| Services                                        |                                        | Starts, stops, and configures Windows services.                                                                                                                                                                                 |                                |
| Share and Storage Management                    |                                        | Manages Shares and Volumes.                                                                                                                                                                                                     |                                |
| Shared Folders                                  |                                        | Displays shared folders, current sessions, and open files.                                                                                                                                                                      |                                |
| Storage Explorer                                |                                        | Displays and manages the elements of a SAN.                                                                                                                                                                                     |                                |
| Storage Manager for SANs                        |                                        | Manages SAN Storage.                                                                                                                                                                                                            |                                |
| Task Scheduler                                  |                                        | Schedule computer tasks to run automatically.                                                                                                                                                                                   |                                |
| TPM Management                                  |                                        | The Trusted Platform Module (TPM) Management snap-in allows you to configure and manage the TPM security hardware.                                                                                                              |                                |
| Windows Firewall with Advanced Security         |                                        | Configure policies that provide enhanced network security for Windows computers.                                                                                                                                                |                                |
| Windows System Resource Manager                 |                                        | Manages CPU and/or Working Sets for groups of processes on Microsoft Windows Server.                                                                                                                                            |                                |
| WMI Control                                     |                                        | Allows configuration and control of the Windows Management Instrumentation (WMI) service.                                                                                                                                       |                                |

**Extensions for Snap-ins**

Active Directory Sites and Services has available extension Group Policy Object Editor

``Active Directory Users and Computers has available extensions Group Policy Object Editor, Remote Desktop Services - Extension, 3rd-party add-on Extension to AD User and Computer for EmployeeID and photo\<?>``

Certification Authority has available extension CA Certificate Template Settings

Component Services has DTC MMC Property-sheet extension, DTC MMC Snap-in

Computer Management has Device Manager extension, DHCP Extension, Disk Management Extension, Event Viewer, Internet Information Services (IIS) Manager, Local Users and Groups, Performance Monitor Extension, Services Extension, Shared Folders Extension, Task Scheduler, WMI Control

DNS (cannot edit) has Classic Event Viewer Extension, Services Extension

Event Viewer has Classic Event Viewer Extension

``Exchange Server 2010 has four Exchange Server 2010 Extensions \[Try disabling and see what changes]``

Failover Cluster Manager has Failover Cluster Extensions, Failover Cluster Resource Extensions

Failover Cluster Manager Host has DHCP Extension, Print Management

``Group Policy Management Editor has Administrative Templates (Computers)\*, Administrative Templates (Users)\*, Extended View, Folder Redirection Editor (Users), Group Policy Application Settings\*, Group Policy Computer Control Panel\*, Group Policy Drive Settings\*, Group Policy Environment Settings\*, Group Policy File Settings\*, Group Policy Folder Settings\*, Group Policy Ini File Settings\*, Group Policy Printers Settings\*, Group Policy Registry Settings\*, Group Policy Shortcut Settings\*, Group Policy User Control Panel\*, Internet Explorer Maintenance, Name Resolution Policy, Name Resolution Policy \[?], Policy-based QoS (Computers), Policy-based QoS (Users), Pushed Printer Connection Extension (Computers)\*, Pushed Printer Connection Extension (Users)\*, Scripts (Logon/Logoff)\*, Scripts (Startup/Shutdown)\*, Security Settings\*, Software Installation (Computers), Software Installation (Users)``

Group Policy Object Editor has ...

Internet Information.6.. has ASP.NET Management Extension, Extended View, SMTP Protocol

Local Users and Groups has Remote Desktop Services - Extension

Online Responder Management has Online Responder security settings

Print Management has Print Queue View Extension

Resultant Set of Policy has ...

Server Manager has ...?

Services has Extended View, Services Dependencies, Snmp Snapin Extension

Shared Folders has no extensions but View: (All, Sessions, Shares, Open Files)

Windows System Resource Manager has ...?

#### Group Policy Starter GPO {#h.nv2rc87kyld1" id="h.nv2rc87kyld1

Starter GPOs can be stored in the Active Directory.

Starter GPOs in domain

| **Starter GPOs**             |   | **Comment**                                                                                                                                                                                          |
| ---------------------------- | - | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows XP SP2 SSFL Computer |   | This Starter GPO contains the computer Group Policy settings recommended for the Specialized Security Limited Functionality (SSLF) client environment described in the Windows XP security guide.    |
| Windows XP SP2 EC User       |   | This Starter GPO contains the user Group Policy settings recommended for the Enterprise Client (EC) environment described in the Windows XP security guide.                                          |
| Windows Vista EC User        |   | This Starter GPO contains the user Group Policy settings recommended for the Enterprise Client (EC) environment described in the Windows Vista security guide.                                       |
| Windows Vista SSLF Computer  |   | This Starter GPO contains the computer Group Policy settings recommended for the Specialized Security Limited Functionality (SSLF) client environment described in the Windows Vista security guide. |
| Windows Vista EC Computer    |   | This Starter GPO contains the computer Group Policy settings recommended for the Enterprise Client (EC) environment described in the Windows Vista security guide.                                   |
| Windows Vista SSLF User      |   | This Starter GPO contains the user Group Policy settings recommended for the Specialized Security Limited Functionality (SSLF) client environment described in the Windows Vista security guide.     |
| Windows XP SP2 EC Computer   |   | This Starter GPO contains the computer Group Policy settings recommended for the Enterprise Client (EC) environment described in the Windows XP security guide.                                      |
| Windows XP SP2 SSLF User     |   | This Starter GPO contains the user Group Policy settings recommended for the Specialized Security Limited Functionality (SSLF) client environment described in the Windows XP security guide.        |

For more information about each of these settings, see the Windows XP Security Guide ([http://go.microsoft.com/fwlink/?LinkID=121854](http://technet.microsoft.com/en-us/library/cc753708.aspx?LinkID=121854)).

For more information about each of these settings, see the Windows Vista Security Guide (http://go.microsoft.com/fwlink/?LinkID=121852).

``Also in C:\Windows\inf\StarterGPOs``

Security Templates default file list, description, location

``...\Documents\Security\Templates``

INF files

``\Windows\security\templates\policies``

``\Windows\ServiceProfiles\\``

LocalService

NetworkService

Task Manager

Firewall netsh

``RegEdt32\[7]``

charmap

telnet (not installed by default after Windows XP/2003) (Mentioned in Network section?)

``%windir%\system32\defrag.exe -c``

``\ntbackup.exe\[8] -``

``C:\Windows\system32\mstsc.exe (switches?)``

clipboard viewer

sysinfo (windows ver ?)

sysinfo (office)

#### Power Configuration commands {#h.94pstocdhes6" id="h.94pstocdhes6

#### Network commands {#h.ojix9vvv3poa" id="h.ojix9vvv3poa

arp

ipconfig

nbtstat

netstat

nslookup

ping

pathping

route

tracert

hostname

whoami

ipconfig release, renew, flush

winipcfg.exe, wntipcfg.exe (Windows 9x?) (win 2000 reskit)

arp clear, set temp for connecting with device using unknown IP

route print, route add -p

These are covered in the NTFS document

cacls, icacls, attrib, cipher, compact, expand, takeown, robocopy

(expand or compress see http://gnuwin32.sourceforge.net/packages/mscompress.htm)

diskpart, format, fsutil, label, defrag

SubInACL.exe (Windows Server 2003 Resource Kit)

SystemInfo.exe

SC for service control manager

#### From Windows Installation Media {#h.adq3uwum6lrg" id="h.adq3uwum6lrg

Microsoft Windows Support Tools

The Windows CD has a Support folder (see below 5 or 6 pages)

Microsoft Windows 2000, Windows XP, Windows Server 2003 and Windows Server 2003 R2

``Windows XP Setup CD, and then locate the Support\Tools folder``

### Remote {#h.j40pvknrtwar" id="h.j40pvknrtwar

**telnet**

ssh. do different versions of telnet have different security?

**powershell**

[http://technet.microsoft.com/en-us/library/dd819505.aspx](http://technet.microsoft.com/en-us/library/dd819505.aspx)

**rsexec?**

[http://stackoverflow.com/questions/3412911/r-exe-rcmd-exe-rscript-exe-and-rterm-exe-whats-the-difference](https://docs.google.com/a/blackchambers.net/document/d/1A9JS-1G0uQMZu8TCnpwCcTVZDw-3lpqf-E-b7eX6xj4/edit)

rcmd (NT4 ResKit), remote

[http://www.windowsitpro.com/article/remote-computing/remote-command-7227](http://technet.microsoft.com/en-us/library/cc754415.aspx)

[http://blogs.msdn.com/b/shamit/archive/2005/03/12/394650.aspx](http://blogs.msdn.com/b/shamit/archive/2005/03/12/394650.aspx)

**winrs**

winrs –r:_ServerName_ cmd.exe

**psexec**

psexec and more http://serverfault.com/questions/32489/remote-command-execution-on-windows-2003-server

**at/schtasks**

GUI

**mmc & msc**

**RDP (tsclient)**

**Web-based (IIS hosted admin tools)**

Server Manager, Roles, Streaming Media Services

Application Center

Active Directory Web Services (ADWS on 2008 R2)

IIS (5.0, ...)

Exchange Server (2010, ...) fqdn/ecp

Team Foundation Server (2012, ...)

Virtual Server 2005

Windows Server 2003 [https://ComputerName:8098](http://technet.microsoft.com/en-us/library/cc755162.aspx)

WSUS (2.0, not 3.0)

### Windows Server 2012 Core {#h.yk3ya590575f" id="h.yk3ya590575f

sconfig.cmd

``\[menu or screenshot]``

sc services

``C:\Windows\System32\SCRegEdit.wsh enable or disable Remote Desktop and configure Windows Update``

``C:\Windows\System32\GatherNetworkInfo.vbs``

netdom.exe change hostname or join domain

netsh.exe change IP address, firewall

net.exe add/remove users, connect to network drives

pnputil drivers

drvinst drivers

diskraid RAID volumes

ServerManagerCmd.exe

MSInfo32.exe

Regedit.exe and Regedt32.exe

secedit.exe

TimeDate.cpl

timezone.cpl change the time and time zone

Intl.cpl

iscsicpl.exe connect to shared storage over iSCSI (starting with Windows Server 2008 R2)

iscsicli.exe connect to shared storage over iSCSI (starting with Windows Server 2008)

Some features/roles not available. 2008 Core can't be converted, 2012 can change core, full, minimal interfaces.

### Other System Apps {#h.ir4cbyik87yo" id="h.ir4cbyik87yo

#### from System Configuration (msconfig), Tools, Launch {#h.42y7kg8yl6nl" id="h.42y7kg8yl6nl

| **Tool Name**                   | **Description**                                                 |
| ------------------------------- | --------------------------------------------------------------- |
| About Windows                   | C:\Windows\system32\winver.exe                                  |
| Change UAC Settings             | C:\Windows\System32\UserAccountControlSettings.exe              |
| Action Center                   | C:\Windows\System32\wscui.cpl                                   |
| Windows Troubleshooting         | C:\Windows\System32\control.exe /name Microsoft.Troubleshooting |
| Computer Management             | C:\Windows\System32\compmgmt.msc                                |
| System Information              | C:\Windows\System32\msinfo32.exe                                |
| Event Viewer                    | C:\Windows\System32\eventvwr.exe                                |
| Programs                        | C:\Windows\System32\appwiz.cpl                                  |
| System Properties               | C:\Windows\System32\control.exe system                          |
| Internet Options                | C:\Windows\System32\inetcpl.cpl                                 |
| Internet Protocol Configuration | C:\Windows\System32\cmd.exe /k %windir%\system32\ipconfig.exe   |
| Performance Monitor             | C:\Windows\System32\perfmon.exe                                 |
| Resource Monitor                | C:\Windows\System32\resmon.exe                                  |
| Task Manager                    | C:\Windows\System32\taskmgr.exe                                 |
| Command Prompt                  | C:\Windows\System32\cmd.exe                                     |
| Registry Editor                 | C:\Windows\System32\regedt32.exe                                |
| Remote Assistance               | C:\Windows\System32\msra.exe                                    |
| System Restore                  | C:\Windows\System32\rstrui.exe                                  |

#### Windows Sysinternals {#h.fnxkrjgzgwxc" id="h.fnxkrjgzgwxc

[http://technet.microsoft.com/en-us/sysinternals/bb545021.aspx](http://technet.microsoft.com/en-us/sysinternals/bb545021.aspx)

**GUI Tools**

| **Name**                     | **Description**                      | **Path**            |
| ---------------------------- | ------------------------------------ | ------------------- |
| AccessEnum                   |                                      | AccessEnum.exe      |
| Active Directory Explorer    | Active Directory Editor              | ADExplorer.exe      |
| Autoruns                     | Autostart program viewer             | autoruns.exe        |
| BGInfo                       | BGInfo - Wallpaper text configurator | Bginfo.exe          |
| Cacheset                     | Cache Set                            | Cacheset.exe        |
| DebugView                    |                                      | Dbgview.exe         |
| Desktops                     | Sysinternals Desktops                | Desktops.exe        |
| Disk Monitor                 | Disk Monitor                         | Diskmon.exe         |
| Disk2Vhd                     | Disk to VHD converter                | disk2vhd.exe        |
| DiskView                     | Sysinternals Diskview                | DiskView.exe        |
| Insight for Active Directory | Active directory LDAP monitor        | ADInsight.exe       |
| LoadOrder                    |                                      | LoadOrd.exe         |
| Pagefile Defragger           | System defragmenter                  | pagedfrg.exe        |
| PortMonitor                  | Portmon/EE                           | portmon.exe         |
| Process Explorer             | Sysinternals Process Explorer        | procexp.exe         |
| Process Monitor              |                                      | Procmon.exe         |
| RAMMap                       | RamMap - physical memory analyzer    | RAMMap.exe          |
| RootkitRevealer              | Rootkit detection utility            | RootkitRevealer.exe |
| ShareEnum                    |                                      | ShareEnum.exe       |
| ShellRunas                   | Run as different user                | ShellRunas.exe      |
| TCPView                      | TCP/UDP endpoint viewer              | Tcpview.exe         |
| VMMap                        | Vmmap - process memory analyzer      | vmmap.exe           |
| WinObj                       | Sysinternals Winobj                  | Winobj.exe          |
| ZoomIt                       | Sysinternals Screen Magnifier        | ZoomIt.exe          |

#### Windows Support Tools {#h.iuxzcmw86mkw" id="h.iuxzcmw86mkw

From Windows Installation Media

The Windows CD has a Support folder (see above 1 or 2 pages)

Microsoft Windows 2000, Windows XP, Windows Server 2003 and Windows Server 2003 R2

64-bit Windows XP, Windows Server 2003

**Windows 2000 Service Pack 4**

**Windows XP Service Pack 2**

**Windows Server 2003 Service Pack 2**

WinDiff

NetDiag

MsiZap Windows Installer Zapper

Msicuu.exe Windows Installer CleanUp Utility

### Resource Kits from MS Press {#h.j6lm75oroq3a" id="h.j6lm75oroq3a

ResKit

32-bit only (Some tools that are also in the Support Tools may have x64 versions on the 64-bit media)

| **Product/Topic**                                         | **Contents**            | **Updates/Versions**     |
| --------------------------------------------------------- | ----------------------- | ------------------------ |
| Windows 3.0                                               |                         |                          |
| MS-DOS 6.22                                               |                         |                          |
| Windows 3.1                                               |                         |                          |
| Windows 3.? (WFWG ?)                                      |                         |                          |
| Windows 95                                                | Documentation and Tools |                          |
| Windows 98                                                | Documentation and Tools |                          |
| Windows NT (Workstation & Server)                         |                         |                          |
| Windows NT 3.51                                           |                         | 2 Supplements for Server |
| Windows NT 4.0 (Workstation & Server)                     | Docs, Tools, 3rd party  | 4 supplements for Server |
| Windows 2000 (Professional & Server)                      |                         | 1 supplement for Server  |
| Windows XP                                                |                         |                          |
| Windows 2003                                              |                         |                          |
| Windows XP Professional Resource Kit, Third Edition (SP2) |                         |                          |
| Windows Vista                                             |                         |                          |
| Windows Server 2008                                       |                         |                          |
| Windows Vista, Second Edition (SP1)                       |                         |                          |
| Windows 7                                                 |                         |                          |
| PowerShell Pack                                           |                         |                          |

Windows XP

Windows 2000

Windows Server 2003

Windows Administration Resource Kit

IIS

SQL?

Exchange?

Group Policy

Windows security

Active Directory

Terminal Services

Internet Information Services 7

Office

Internet Explorer

Windows Media

Internet Information Services

Back Office

and several server products such as SharePoint and Microsoft Exchange Server

### Popular Applications {#h.8dwdprfc5vfh" id="h.8dwdprfc5vfh

#### Internet Explorer {#h.6ottd7anoz6k" id="h.6ottd7anoz6k

Windows 7 (IE version 9)

``C:\Users\\_\<user name>_\Downloads``

``C:\Users\\_\<UserName>_\AppData\Local\Microsoft\Windows\Temporary Internet Files``

``C:\Windows\Downloaded Program Files``

Internet Explorer Temp Folder (IE Cache)

``C:\Users\\_\<user name>_\AppData\Local\Microsoft\Windows\Temporary Internet Files``

IE Cookies

``C:\Users\\_\<user name>_\AppData\Roaming\Microsoft\Windows\Cookies``

Good to export this file using IE, File, Export when moving a user to another computer.

Internet Explorer History

``C:\Users\\_\<user name>_\AppData\Local\Microsoft\Windows\History``

IE Typed URLs

``HKCU\Software\Microsoft\Internet Explorer\TypedUrls``

``not be 100% certain, google Julie Amero``

Internet Explorer Forms AutoComplete

``HKCU\Software\Microsoft\Internet Explorer\IntelliForms\Storage1``

obfuscated form

Internet Explorer Password AutoComplete

``HKCU\Software\Microsoft\Internet Explorer\IntelliForms\Storage2``

obfuscated form

**Links and Shortcuts**

``C:\Users\\_\<UserName>_\Links``

Windows XP

``C:\Documents and Settings\\_\<UserName>_\Application Data\Microsoft\Internet Explorer\Quick Launch``

Must also enable the Toolbar, right click Toolbars, select

Windows 7

``%APPDATA%\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar``

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Taskband``

**Internet Explorer image in web page, Set as background**

``C:\Users\\_UserName_\AppData\Roaming\Microsoft\Internet Explorer\Internet Explorer Wallpaper.bmp``

**Internet Security Properties, Sites, Add website to the zone**

What sites/locations are classified automatically

Local

Local Intranet

Internet/Untrusted

URL Wildcard Sequence:

Examples of valid patterns:

``\*://\*.microsoft.com``

``http://\*.microsoft.co.jp``

ftp://157.54.23.41/

``file:\\\localsvr\share``

``\*://157.54.100-200.\*``

Examples of invalid patterns:

``http://microsoft.\*.com``

``ftp://\*``

Windows Update URLs to add to Trusted

Outlook Emails and Attachments classified under which Security Zone?

**Content Adviser**

URLs to add for viewing system files in MMC

``about:\_?\_``

**Internet Explorer Administration Kit**

.ins automatic configuration file for customized browser configuration settings created with the Profile Manager

#### Windows Live {#h.6kn930frdot9" id="h.6kn930frdot9

``C:\Program Files (x86)\Common Files\Windows Live\\.cache\\``

#### Outlook Express {#h.x4vc95c6dnco" id="h.x4vc95c6dnco

**Outlook Express E-Mail Storage**

``C:\Documents and Settings\Username\Local\Application Data\Identities``

**Outlook Express Address Book Contacts**

``Address Book used by Outlook Express\[9]``

``C:\Documents and Settings\\_\<UserName>_\Application Data\Microsoft\Address Book``

``Do other applications use it? Outlook, Windows? (\*.pab, \*.wab)``

#### Microsoft Office {#h.xcy11a3h6km8" id="h.xcy11a3h6km8

Components

See Appendix

**Installation Files or CD**

setup.exe /?

Setup Controller Command-Line Help

/? - Display this command-line help

/admin - Launch the Office Customization Tool

``/adminfile \<admin file> - Specify a customization patch of folder containing a customization patch``

``/config \<config file> - Specify a config.xml file``

``/modify \<product ID> - Enter Maintenance Mode for a product``

``/repair \<product ID> - Repair a product``

``/uninstall \<product ID> - Uninstall a product``

What are the product IDs?

**Changes to Installation**

Excel auto save now included, used to require manual selection

Outlook Social Connector still requires manual install of 3rd-party add ons

Does converters and graphics filters affect file preview of .GIF, .JPG?

OCR tools removed from 64-bit. Were part of discontinued Picture/Imaging Manager? Some work arounds include installing Sharepoint designer? or using OneNote and TIF file?

**How To Outlook LDAP directory to use AD**

Add account, Address Books tab, Microsoft LDAP Directory

Server Name: FQDN to server

Logon Information

This server requires me to log on: Checked (User Name and Password can be left blank)

Require Secure Password Authentication (SPA) Checked

More Settings ... button

Connection tab

Display Name: The name of the address book your users will see

Connection Details: no change needed

Search tab

Specify the maximum number of entries you want to return after a successful search: 200

Search Base, Custom: dc=domainname,dc=com

Enable Browsing (requires server support)

**Differences with Service Pack 1**

``Office 2010 Standard with SP1 has the following additional files in the .\Updates folder``

clientshared32muisp1-en-us.msp

clientshared32wwsp1-x-none.msp

clientsharedmuisp1-en-us.msp

officesuitemuisp1-en-us.msp

officesuitewwsp1-x-none.msp

proofingsp1-en-us.msp

proofsp1-en-us.msp

proofsp1-es-es.msp

proofsp1-fr-fr.msp

README.TXT

**Microsoft Office Customization Tool**

As of Microsoft Office 2010, there is no separate download

`SETUP.EXE /admin to open Office Customization Tool`

``Creates a .MSP file to be placed in the .\Updates folder``

Windows Live has Skydrive? which will replicate certain office settings to other computers.

These settings include dictionary, word.dot?, ...

Recently Opened Office Docs

``C:\Users\\_\<user name>_\AppData\Roaming\Microsoft\Office\Recent``

**Recovered Office files**

``C:\Users\\_\<UserName>_\AppData\Local\Microsoft\Office\UnsavedFiles``

**Connect to database and execute SQL**

``Microsoft Query "C:\Program Files\Microsoft Office\Office14\MSQRY32.EXE"``

**Custom Dictionary**

``C:\Users\\_\<UserName>_\AppData\Roaming\Microsoft\UProof\CUSTOM.DIC``

**Dictionary (.dic)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\UProof``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\UProof``

**Templates (.oft)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\Templates``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Templates``

**Templates**

**Add-Ons**

**Data Connections**

``C:\Program Files\Microsoft Office\Office14\QUERIES``

MSN MoneyCentral Investor Currency Rates.iqy

MSN MoneyCentral Investor Major Indicies.iqy

MSN MoneyCentral Investor Stock Quotes.iqy

``\[...]\Documents\My Data Sources\\_ServerName_\__SQLInstance_ _DatabaseName_.odc``

**Visual Basic for Applications**

``VBA settings migration\[10]``

In Office 2010, Visual Basic for Applications (VBA) 6.0 was updated to VBA 7.0. VBA 7.0 settings were reset to their defaults after migration instead of automatically repopulating. This occurred because the registry settings for VBA are in a different hive in Office 2010, as shown in the following table.

Office 2000 through Office 2007

``HKCU\SOFTWARE\Microsoft\VBA\6.0\Common``

Office 2010

``HKCU\SOFTWARE\Microsoft\VBA\7.0\Common``

| Office 9 through Office 12 | HKCU\SOFTWARE\Microsoft\VBA\6.0\Common |
| -------------------------- | -------------------------------------- |
| Office 14                  | HKCU\SOFTWARE\Microsoft\VBA\7.0\Common |

To correct this problem, copy the VBA 6.0 registry keys from the 6.0 hive to the 7.0 hive.

**Digital Certificate for VBA**

can also be used to sign PowerShell and documents such as Access databases and installers

``C:\\... usage/switches``

**other cert tools**

**Document Inspector**

customize the Document Inspector by adding Inspector modules

**Microsoft Visio**

``* In Windows 7 and Windows Vista, the **My Shapes** directory is located at C:\Users\\_yourname_\Documents\My Shapes.``
``* In Windows XP and earlier, the **My Shapes** directory is located at C:\Documents and Settings\\_yourname_\My Documents\My Shapes.``

**Microsoft Office 2013 Activation**

[http://www.askvg.com/fix-the-products-we-found-in-your-account-cant-be-used-to-activate-error-message-in-microsoft-office-2013-applications/](http://technet.microsoft.com/en-us/library/cc771151.aspx)

trying to activate the product using your Windows Live ID (Microsoft account) or Office 365 account credentials, the product doesn't get activated

Don't activate the product using your account credentials. Just enter your product key manually to activate Office 2013 copy.

You can follow these simple steps to fix the problem and successfully activate Office 2013 in your system:

**1.** Open **Control Panel** and click on **Programs and Features** icon.

**2.** Now click on **Microsoft Office 2013** entry given in the list and then click on **Change** button given in the toolbar.

**3.** It'll open Office 2013 setup wizard and will show following options to select:

* Add or Remove Features
* Repair
* Remove
* Enter a Product Key

manually uninstall product keys installed by Preview version of Office 2013

``CD C:\Program Files\Microsoft Office\Office15``

cscript ospp.vbs /dstatus

Note down the **last 5 characters of product keys** given in each section.

Now run following command for each product key:

``cscript ospp.vbs /unpkey:_last\_5\_characters\_of\_product\_key_``

For example if the last 5 characters of one product key are ABCDE, then run following command:

cscript ospp.vbs /unpkey:ABCDE

uninstall all existing versions of Office from your system and then reinstall Office 2013. Now it should activate itself without any problem.

**Microsoft Office 2007-2013 File Format**

XML, 'Open Document'

File extensions: DOCX, XLSX, ...

are actually zip files, if extension changed to ZIP, then XML files and folders can be extracted

Sample:

C:.

``│ \[Content\_Types].xml``

│

├───customXml

│ │ item1.xml

│ │ itemProps1.xml

│ │

``│ └───\_rels``

│ item1.xml.rels

│

├───docProps

│ app.xml

│ core.xml

│

├───word

│ │ document.xml Contains the content

│ │ fontTable.xml

│ │ settings.xml

│ │ styles.xml

│ │ stylesWithEffects.xml

│ │ webSettings.xml

│ │

│ ├───theme

│ │ theme1.xml

│ │

``│ └───\_rels``

│ document.xml.rels

│

``└───\_rels``

.rels

#### Microsoft Outlook {#h.41zogueol3x2" id="h.41zogueol3x2

Outlook-specific

Exchange (SMTP):

``HKLM\SOFTWARE\Microsoft\Exchange\ContentFilter\ "ArchiveSCL"=dword:00000001``

see also: [http://office.microsoft.com/en-us/outlook-help/where-does-microsoft-outlook-2010-save-my-information-and-configurations-HP010354943.aspx](http://technet.microsoft.com/en-us/library/cc732406.aspx)

**64-bit edition**

``Tell if the Outlook 2010 is a 32-bit or 64-bit installation\[11]``

``HKLM\Software\Microsoft\Office\14.0\Outlook``

Bitness: x86 or x64

``IF EXIST "%ProgramFiles%\Microsoft Office\Office14\outlook.exe"``

``or "%ProgramFiles(x86)%\Microsoft Office\Office14\outlook.exe"``

``Social Connectors and other Add-ons are specific to 32 or 64-bit editions. 32-bit compiled add-ons will not work in 64-bit office. See Microsoft notes on this \[Link here]``

``Calendar settings, Working Hours\[12]``

``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefStart``

``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefEnd``

**Outlook command line switches**

``cannot use "%ProgramFiles%\Microsoft Office\Office14\outlook.exe" /?``

``sWITCHES DETAILED IN Appendix \_?\_``

.PRF file for Outlook profile

outlook.exe /importprf MigrateEmail.PRF

**Security and Attachment file types**

``Attachment file types blocked by Outlook\[13] in the Group 1``

Another published Link to Microsoft’s most up to date list

The following table identifies the file types that Outlook blocks by default.

| **File name extension** | **File type**                                                           |
| ----------------------- | ----------------------------------------------------------------------- |
| .ade                    | Access Project Extension (Microsoft)                                    |
| .adp                    | Access Project (Microsoft)                                              |
| .app                    | Executable Application                                                  |
| .asp                    | Active Server Page                                                      |
| .bas                    | BASIC Source Code                                                       |
| .bat                    | Batch Processing                                                        |
| .cer                    | Internet Security Certificate File                                      |
| .chm                    | Compiled HTML Help                                                      |
| .cmd                    | DOS CP/M Command File, Command File for Windows NT                      |
| .cnt                    | Help file index                                                         |
| .com                    | Command                                                                 |
| .cpl                    | Windows Control Panel Extension (Microsoft)                             |
| .crt                    | Certificate File                                                        |
| .csh                    | csh Script                                                              |
| .der                    | DER Encoded X509 Certificate File                                       |
| .exe                    | Executable File                                                         |
| .fxp                    | FoxPro Compiled Source (Microsoft)                                      |
| .gadget                 | Windows Vista gadget                                                    |
| .hlp                    | Windows Help File                                                       |
| .hpj                    | Project file used to create Windows Help File                           |
| .hta                    | Hypertext Application                                                   |
| .inf                    | Information or Setup File                                               |
| .ins                    | IIS Internet Communications Settings (Microsoft)                        |
| .isp                    | IIS Internet Service Provider Settings (Microsoft)                      |
| .its                    | Internet Document Set, Internet Translation                             |
| .js                     | JavaScript Source Code                                                  |
| .jse                    | JScript Encoded Script File                                             |
| .ksh                    | UNIX Shell Script                                                       |
| .lnk                    | Windows Shortcut File                                                   |
| .mad                    | Access Module Shortcut (Microsoft)                                      |
| .maf                    | Access (Microsoft)                                                      |
| .mag                    | Access Diagram Shortcut (Microsoft)                                     |
| .mam                    | Access Macro Shortcut (Microsoft)                                       |
| .maq                    | Access Query Shortcut (Microsoft)                                       |
| .mar                    | Access Report Shortcut (Microsoft)                                      |
| .mas                    | Access Stored Procedures (Microsoft)                                    |
| .mat                    | Access Table Shortcut (Microsoft)                                       |
| .mau                    | Media Attachment Unit                                                   |
| .mav                    | Access View Shortcut (Microsoft)                                        |
| .maw                    | Access Data Access Page (Microsoft)                                     |
| .mda                    | Access Add-in (Microsoft), MDA Access 2 Workgroup (Microsoft)           |
| .mdb                    | Access Application (Microsoft), MDB Access Database (Microsoft)         |
| .mde                    | Access MDE Database File (Microsoft)                                    |
| .mdt                    | Access Add-in Data (Microsoft)                                          |
| .mdw                    | Access Workgroup Information (Microsoft)                                |
| .mdz                    | Access Wizard Template (Microsoft)                                      |
| .msc                    | Microsoft Management Console Snap-in Control File (Microsoft)           |
| .msh                    | Microsoft Shell                                                         |
| .msh1                   | Microsoft Shell                                                         |
| .msh2                   | Microsoft Shell                                                         |
| .mshxml                 | Microsoft Shell                                                         |
| .msh1xml                | Microsoft Shell                                                         |
| .msh2xml                | Microsoft Shell                                                         |
| .msi                    | Windows Installer File (Microsoft)                                      |
| .msp                    | Windows Installer Update                                                |
| .mst                    | Windows SDK Setup Transform Script                                      |
| .ops                    | Office Profile Settings File                                            |
| .osd                    | Application virtualized with Microsoft SoftGrid Sequencer               |
| .pcd                    | Visual Test (Microsoft)                                                 |
| .pif                    | Windows Program Information File (Microsoft)                            |
| .plg                    | Developer Studio Build Log                                              |
| .prf                    | Windows System File                                                     |
| .prg                    | Program File                                                            |
| .pst                    | MS Exchange Address Book File, Outlook Personal Folder File (Microsoft) |
| .reg                    | Registration Information/Key for W95/98, Registry Data File             |
| .scf                    | Windows Explorer Command                                                |
| .scr                    | Windows Screen Saver                                                    |
| .sct                    | Windows Script Component, Foxpro Screen (Microsoft)                     |
| .shb                    | Windows Shortcut into a Document                                        |
| .shs                    | Shell Scrap Object File                                                 |
| .ps1                    | Windows PowerShell                                                      |
| .ps1xml                 | Windows PowerShell                                                      |
| .ps2                    | Windows PowerShell                                                      |
| .ps2xml                 | Windows PowerShell                                                      |
| .psc1                   | Windows PowerShell                                                      |
| .psc2                   | Windows PowerShell                                                      |
| .tmp                    | Temporary File/Folder                                                   |
| .url                    | Internet Location                                                       |
| .vb                     | VBScript File or Any VisualBasic Source                                 |
| .vbe                    | VBScript Encoded Script File                                            |
| .vbp                    | Visual Basic project file                                               |
| .vbs                    | VBScript Script File, Visual Basic for Applications Script              |
| .vsmacros               | Visual Studio .NET Binary-based Macro Project (Microsoft)               |
| .vsw                    | Visio Workspace File (Microsoft)                                        |
| .ws                     | Windows Script File                                                     |
| .wsc                    | Windows Script Component                                                |
| .wsf                    | Windows Script File                                                     |
| .wsh                    | Windows Script Host Settings File                                       |
| .xnk                    | Exchange Public Folder Shortcut                                         |

**Cache mode vs Offline Access**

**Autocomplete**

Auto-Complete List (File, Options, Mail, Send Messages, Empty Auto-Complete List)

``.NK2 see NirSoft\[14]``

Outlook Contacts Auto-Complete List

The Auto-Complete List is a feature which displays suggestions for names and e-mail addresses as you begin to type them. These suggestions are possible matches from a list of names and e-mail addresses from the e-mail messages that you have sent.

In Outlook 2010, the Auto-Complete List file (.nk2) is discontinued. The Auto-Complete List entries are now saved in your Microsoft Exchange Server mailbox or for POP3, IMAP, or Hotmail & Windows Live accounts, in the Outlook Data File (.pst) for your account.

Temp folder for Outlook attachments

``HKCU\Software\Microsoft\Office\12.0\Outlook\Security``

``C:\Users\\_\<UserName>_\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook\\_\<random value>_\\``

**Personal Storage and Offline Storage**

**Outlook Data File .PST**

``Earlier Outlook on XP, C:\Documents and Settings\\\<UserName>\Local Settings\Application Data\Microsoft\Outlook``

``Earlier Outlook on Vista C:\Users\\_user_\AppData\Local\Microsoft\Outlook``

``For Outlook 2010, C:\Users\\\<Username>\Documents\Outlook``

Offline Outlook Mailbox

``C:\Users\\_\<user name>_\AppData\Local\Microsoft\Outlook\outlook.ost``

**Outlook Data File .OST**

If you enable use Cached Exchange Mode or to work offline, items in your Exchange mailbox are copied in an offline Outlook Data File (.ost)

``Outlook on XP, C:\Documents and Settings\\_\<UserName>_\Local Settings\Application Data\Microsoft\Outlook``

``Outlook on Vista C:\Users\\_user_\AppData\Local\Microsoft\Outlook``

**Outlook Archive**

``Outlook 2010 stores PST in Documents\Email folder?``

**Microsoft Outlook Inbox Repair Tool**

``PST file repair "C:\Program Files\Microsoft Office\Office14\SCANPST.EXE"``

**Outlook Temp directory**

``for opening attachments C:\Users\\_\<UserName>_\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook``

**Outlook logging (troubleshooting)**

``Diagnostics log location\[15] (File, Options, Advanced, Other, Enable troubleshooting logging)``

The calendar log file is a binary file that cannot be read without a conversion process. Contact Microsoft Support.

MAPI (Exchange), POP3, and SMTP log file:

``* Windows Vista & 7 - c:\Users\\_user name_\AppData\Local\Temp\Outlook Logging\OPMLog.log``
``* Windows XP - c:\Documents and Settings\\_user name_\Local Settings\Temp\Outlook Logging\OPMLog.log``
``* %temp%\olkas\yymmdd-time-fb.log ?``

IMAP transport name is similar to:

``* Windows Vista & 7 - c:\Users\\_user name_\AppData\Local\Temp\Outlook Logging\IMAP-ExampleCom-07\_19\_2012-14\_03\_44\_865.log``
``* Windows XP - c:\Documents and Settings\\_user name_\Local Settings\Temp\Outlook Logging\IMAP-ExampleCom-07\_19\_2012-14\_03\_44\_865.log``

Outlook Profile

``HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows Messaging Subsystem\Profiles``

Microsoft Outlook Configuration Analyzer Tool 2.0 (OCAT)

**Outlook Autodiscover**

Ctrl+Right click on Outlook icon in System Tray

Test E-mail AutoConfiguration...

**Personal Address Book (.PAB)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Local\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Local Settings\Application Data\Microsoft\Outlook``

Personal Address Books (.pab) are not supported in Outlook 2010. When you upgrade to Outlook 2010, you are prompted to import any .pab file into Contacts. If you choose not to import the .pab file when you first run Outlook 2010, you can import it later by using the **Import** command in the Microsoft Office Backstage view.

**Offline Address Book**

The Offline Address Book (.oab) is used by Microsoft Exchange Server accounts. It contains information, such as names, e-mail address, titles, and office locations, from the Global Address List (GAL) on the server that runs Exchange.

You do not have to back up or restore this file. This is file is created and updated automatically.

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Local\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Local Settings\Application Data\Microsoft\Outlook``

**Navigation Pane settings (.xml)**

This file includes information about the contents of the Navigation Pane.

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Outlook\\_profile name_.xml``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Outlook\\_profile name_.xml``

**Registered Microsoft Exchange extensions (.dat)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Local\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Local Settings\Application Data\Microsoft\Outlook``

**Rules (.rwz)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Outlook``

**Note** If you upgraded to Outlook 2010 from a version of Outlook earlier than Microsoft Outlook 2002, you might have an .rwz file on your computer's hard disk drive. The .rwz file is no longer needed, and the information about rules is now kept on the server running Microsoft Exchange, and in the Outlook Data File (.pst) for POP3 and IMAP e-mail accounts. You can delete the file.

If you use the Rules Import and Export feature, the default location for .rwz files is your **Documents** folder.

**Print styles (Outlprnt with no extension)**

``**Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Outlook``

**Signatures (.rtf, .txt, .htm)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\Signatures``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Signatures``

A signature named “Company default” will generate the following files and folder structure.

``C:\Users\UserName\AppData\Roaming\Microsoft\Signatures\\``

├Company default.htm

├Company default.rtf

├Company default.txt

``└Company default\_files\\``

├colorschememapping.xml

├filelist.xml

└themedata.thmx

**Stationery (.htm)**

If installed, and personal or computer-wide.

``**Windows 7 and Windows Vista** _drive_:\Program Files\Common Files\Microsoft Shared\Stationery``

``**Windows 7 and Windows Vista 64-bit with Outlook 2010 32-bit** _drive_:\Program Files (x86)\Common Files\Microsoft Shared\Stationery``

``**Windows XP** _drive_:\Program Files\Common Files\Microsoft Shared\Stationery``

``C:\Users\UserName\AppData\Roaming\Microsoft\Stationery``

**Custom forms**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Local\Microsoft\Forms``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Local Settings\Application Data\Microsoft\Forms``

Forms

``Program Files\\\<Office folder>\Office 14\Forms\\\<language ID>``

.ico, cfg, see SCL.CFG commonly used for Exchange/Outlook spam confidence level

**Send/Receive settings (.srs)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\AppData\Roaming\Microsoft\Outlook``

``**Windows XP** _drive_:\Documents and Settings\\_user_\Application Data\Microsoft\Outlook``

``\<Profile Name>.srs``

**Message (.msg, .htm, .rtf)**

``**Windows 7 and Windows Vista** _drive_:\Users\\_user_\Documents``

``**Windows XP** _drive_:\Documents and Settings\\_user_\My Documents``

**.PRF file for Outlook profile**

``"%ProgramFiles%\Microsoft Office\Office14\outlook.exe" /importprf %LogonServer%\NETLOGON\MigrateEmail.PRF``

``"%ProgramFiles(x86)%\Microsoft Office\Office14\outlook.exe" /importprf %LogonServer%\NETLOGON\MigrateEmail.PRF``

Use[ ](http://technet.microsoft.com/en-us/library/cc772168.aspx#heading=h.96ds1q77m2pr)[Microsoft Office Customization Tool](http://technet.microsoft.com/en-us/library/cc753151.aspx#heading=h.96ds1q77m2pr) for creating Outlook Profiles (.PRF)

**MAPI Tools**

MFCMAPI

MRMAPI

#### Microsoft Media Player {#h.w3s6l6576v3j" id="h.w3s6l6576v3j

Files recently accessed by Windows Media Player

``HKCU\Software\Microsoft\MediaPlayer\Player\RecentFileList``

(XP Only?)

#### Microsoft Media Center {#h.3whiub1u4n16" id="h.3whiub1u4n16

Windows 8 Media Center includes DVD playing CODEC, not Blu-Ray, and codec doesn’t work for Media Player.

Program schedule downloads directory

Recorded show directory

DRM files for moving recorded content

How to Backup and Restore Windows Media Player DRM Licenses or Media Usage Rights

[http://www.mydigitallife.info/how-to-backup-and-restore-windows-media-player-drm-licenses-or-media-usage-rights/](http://www.mydigitallife.info/how-to-backup-and-restore-windows-media-player-drm-licenses-or-media-usage-rights/)

[http://www.mydigitallife.info/individualize-windows-media-player-wmp-for-fairuse4wm-and-invalid-license-error/](http://www.mydigitallife.info/individualize-windows-media-player-wmp-for-fairuse4wm-and-invalid-license-error/)

#### Mozilla Firefox {#h.4gaxhfbgx3zj" id="h.4gaxhfbgx3zj

**User Profile**

``C:\Users\\\<UserName>\AppData\Roaming\Mozilla\Firefox\Profiles``

``%APPDATA%\Mozilla\Firefox\Profiles\\``

**Bookmarks**

``Firefox bookmarks (favorites)\[16]``

The places.sqlite file contains all your Firefox bookmarks and the list of all the websites you’ve visited.

**Custom Dictionary**

``C:\users\\\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\\\[unique-alphanumeric-string].default\persdict.dat``

``C:\Documents and Settings\\\[username]\ApplicationData\Mozilla\Firefox\Profiles\\\[unique-alphanumeric-string].default\persdict.dat``

Firefox:

``C:\Users\\\<user name>\AppData\Local\Mozilla\Firefox\Profiles\\\<some profile number>.default\\``

``\*.sqllite files``

SQLLiteStudio or http://www.sqlite.org/cvstrac/wiki?p=ManagementTools

Firefox Cached Pages

``C:\Users\\\<user name>\AppData\Local\Mozilla\Firefox\Profiles\\\<some profile number>.default\Cache``

[http://www.securityfocus.com/infocus/1832](http://www.securityfocus.com/infocus/1832)

Firefox Form History File

``C:\Users\\\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\\\<some profile number>.default\formhistory.sqlite``

Firefox Passwords File

``C:\Users\\\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\\\<some profile number>.default\signons.sqlite``

Firefox Cookies

``C:\Users\\\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\\\<some profile number>.default\cookies.sqlite``

#### Adobe Flash Player {#h.itnceweu7188" id="h.itnceweu7188

Flash Cookies Location

``C:\Users\\\<username>\AppData\Roaming\Macromedia\Flash Player\\#SharedObjects\\\<random value>\\``

Adobe Flash Player Update Configuration

Adobe Flash Player Background Updater

``C:\Windows\System32\Macromed\Flash\mms.cfg``

``C:\Windows\SysWOW64\Macromed\Flash\mms.cfg``

``Administrator Guide\[17]``

#### Apple iTunes {#h.79jwcyc34i7c" id="h.79jwcyc34i7c

``Beginning with new installations of version 10.? C:\Users\UserName\Music\iTunes\iTunes Media``

``Music C:\Users\UserName\Music\iTunes\iTunes Media\Music``

AudioBooks

``Pickup Folder (Automatically add to itunes) C:\Users\UserName\Music\iTunes\iTunes Media\Automatically Add to iTunes``

Books

Podcasts

iTunes U

Movies

TV Shows

``Compilations C:\Users\UserName\Music\iTunes\iTunes Media\Music\Compilations``

Apps

``Device backups C:\Users\UserName\AppData\Roaming\Apple Computer\MobileSync\Backup\78193d251bbc7f3bb18de246a16b8fe6ceba2cf7\ and .\Manifest.mbdb``

``Device firmware updates C:\Users\\_UserName_\AppData\Roaming\Apple Computer\iTunes\iPod Software Updates``

``Apple Software Updates C:\Users\\_UserName_\AppData\Local\Apple\Apple Software Update``

``iTunes Library files (\*.itl)\[18] \[sql lite] C:\Users\\_UserName_\Music\iTunes\iTunes Library.itl``

``iTunes Library file XML C:\Users\\_UserName_\Music\iTunes\iTunes Music Library.xml``

``Cover images C:\Users\\_UserName_\Music\iTunes\Album Artwork``

``the iTunes configuration files (delete the “SC Info.sidb” file)\[19]``

``* The preference files for Windows Vista and 7\[20] live here:\``
``C:\Users\username\AppData\Local\Apple Computer\iTunes\``
``C:\Users\username\AppData\Roaming\Apple Computer\iTunes``
``* In Windows XP and 2000 the iTunes preference files\[21] are here:\``
``C:\Documents and Settings\username\Application Data\Apple Computer\iTunes\``
``C:\Documents and Settings\username\Local Settings\Application Data\Apple Computer\iTunes``
``* In Windows XP and 2000 the iTunes configuration files\[22] are here:\``
``C:\Documents and Settings\All Users\Application Data\Apple Computer\iTunes\SC Info``

Devices

``C:\Users\UserName\AppData\Local\Apple Computer\iTunes\iPodDevices.xml``

**iCloud**

``Photostream My Pictures\Photostream\My Photostream ?``

**Safari**

#### Java (Sun/Oracle) {#h.ol8w38ugj79h" id="h.ol8w38ugj79h

**Offline MSI Installer files**

``Java doesn’t provide downloads of MSI files. They can be located here during/after installation\[23]``

``C:\Users\\\<user>\AppData\LocalLow\Sun\Java\jre1.7.0\_09\jre1.7.0\_09.msi``

``C:\Documents and Settings\\\<user>\Local Settings\ApplicationData\Sun\Java\jre1.6.0\_37\_x64\jre1.6.0\_37.msi``

**Autoupdate Registry key**

``HKLM\SOFTWARE\JavaSoft\Java Update\Policy\EnableJavaUpdate=0``

``HKLM\SOFTWARE\WOW6432Node\JavaSoft\Java Update\Policy\EnableJavaUpdate=0``

**Java Temporary files**

``Jar file cache\[24] (Good to clean in case of virus?)``

``Java 6 or 7, Windows Vista or above C:\Users\UserName\AppData\LocalLow\Sun\Java\Deployment\cache``

**High-Security Option**

Security files area for getting higher level security certificates.

Also settings to help protect from exploits

``HKCU\Software\AppDataLow\Software\JavaSoft\DeploymentProperties\\"deployment.security.level"="HIGH"``

``Setting the Security Level of the Java Client\[25]``

``jre-7u10-windows-i586.exe with flags: /s WEB\_JAVA=1 WEB\_JAVA\_SECURITY\_LEVEL=H``

**Install**

Download site: http://java.com/en/download/manual.jsp

Admin guide:

Command Line: (see msiexec)

Windows ® Installer. V 5.0.7601.17514

``msiexec /Option \<Required Parameter> \[Optional Parameter]``

Install Options

\</package | /i> \<Product.msi>

Installs or configures a product

``/a \<Product.msi>``

Administrative install - Installs a product on the network

/j\<u|m> \<Product.msi> \[/t \<Transform List>] \[/g \<Language ID>]

Advertises a product - m to all users, u to current user

\</uninstall | /x> \<Product.msi | ProductCode>

Uninstalls the product

Display Options

/quiet

Quiet mode, no user interaction

/passive

Unattended mode - progress bar only

/q\[n|b|r|f]

Sets user interface level

n - No UI

b - Basic UI

r - Reduced UI

f - Full UI (default)

/help

Help information

Restart Options

/norestart

Do not restart after the installation is complete

/promptrestart

Prompts the user for restart if necessary

/forcerestart

Always restart the computer after installation

Logging Options

/l\[i|w|e|a|r|u|c|m|o|p|v|x|+|!|\*] \<LogFile>

i - Status messages

w - Nonfatal warnings

e - All error messages

a - Start up of actions

r - Action-specific records

u - User requests

c - Initial UI parameters

m - Out-of-memory or fatal exit information

o - Out-of-disk-space messages

p - Terminal properties

v - Verbose output

x - Extra debugging information

``\+ - Append to existing log file``

! - Flush each line to the log

``\* - Log all information, except for v and x options``

``/log \<LogFile>``

``Equivalent of /l\* \<LogFile>``

Update Options

``/update \<Update1.msp>\[;Update2.msp]``

Applies update(s)

/uninstall \<PatchCodeGuid>\[;Update2.msp] /package \<Product.msi | ProductCode>

Remove update(s) for a product

Repair Options

/f\[p|e|c|m|s|o|d|a|u|v] \<Product.msi | ProductCode>

Repairs a product

p - only if file is missing

o - if file is missing or an older version is installed (default)

e - if file is missing or an equal or older version is installed

d - if file is missing or a different version is installed

c - if file is missing or checksum does not match the calculated value

a - forces all files to be reinstalled

u - all required user-specific registry entries (default)

m - all required computer-specific registry entries (default)

s - all existing shortcuts (default)

v - runs from source and recaches local package

Setting Public Properties

``\[PROPERTY=PropertyValue]``

Consult the Windows ® Installer SDK for additional documentation on the

command line syntax.

Copyright © Microsoft Corporation. All rights reserved.

Portions of this software are based in part on the work of the Independent JPEG Group.

#### Dell {#h.1toqrykete5x" id="h.1toqrykete5x

Get/Convert Service Tag and Express Service Code

Default folder for extracted drivers

Digital Line Detect

``Internet Name Lookup helper \<sp>``

#### HP {#h.276naol8b2it" id="h.276naol8b2it

Default folder for extracted drivers (SPnnnn files and printer drivers)

### Microsoft Servers and Windows Services {#h.9myl42igo6cu" id="h.9myl42igo6cu

``See appendix \_ for list of all Windows components, features, roles``

#### DNS Server {#h.eit8y2gyf1cb" id="h.eit8y2gyf1cb

``C:\Windows\System32\dns``

``C:\Windows\System32\dns\backup``

**DNS Server Tools**

Ddnscmd.exe

**Backup/Export AD integrated zone to text file**

``DnsCmd \<ServerName> /ZoneExport \<ZoneName> \<ZoneExportFile>``

**Enable GlobalNames zone support**

dnscmd . /config /enableglobalnamessupport 1

``HKLM\SYSTEM\CurrentControlSet\services\DNS\Parameters\EnableGlobalNamesSupport = 1``

#### DHCP Server {#h.sd91ba4gx9g2" id="h.sd91ba4gx9g2

``%systemroot%\System32\dhcp\backup``

``HKLM\SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters``

**DHCP Server Tools**

DHCP Server Tools includes the DHCP Management Console, the DHCP Server cmdlet module for Windows Powershell, and the **Netsh** command-line tool.

#### Exchange, SMTP, POP3 Servers {#h.p2aanbf91fkj" id="h.p2aanbf91fkj

``C:\inetpub\mailroot``

``C:\inetpub\mailroot\Badmail must be manually cleaned or spam will fill disk``

``C:\inetpub\mailroot\Drop local delivery\[26]``

``C:\inetpub\mailroot\Pickup starting point for outgoing mail\[27]``

``C:\inetpub\mailroot\Queue``

``C:\Windows\System32\LogFiles\SMTPSVC1 SMTP logs``

ex??????.log files

POP3 mailboxes

**ESEUTIL**

``C:\Program Files\Microsoft\Exchange Server\V14\Bin``

Extensible Storage Engine Utilities for Microsoft(R) Exchange Server

Version 14.02

Copyright (C) Microsoft Corporation. All Rights Reserved.

DESCRIPTION: Database utilities for the Extensible Storage Engine for Microsoft(R) Exchange Server.

MODES OF OPERATION:

``Defragmentation: ESEUTIL /d \<database name> \[options]``

``Recovery: ESEUTIL /r \<logfile base name> \[options]``

``Integrity: ESEUTIL /g \<database name> \[options]``

``Checksum: ESEUTIL /k \<file name> \[options]``

``Repair: ESEUTIL /p \<database name> \[options]``

``File Dump: ESEUTIL /m\[mode-modifier] \<filename>``

``Copy File: ESEUTIL /y \<source file> \[options]``

``Restore: ESEUTIL /c\[mode-modifier] \<path name> \[options]``

<<<<< Press a key for more help >>>>>

D=Defragmentation, R=Recovery, G=inteGrity, K=checKsum,

P=rePair, M=file duMp, Y=copY file, C=restore

``\=>``

#### Windows Update Server {#h.vhis7vg15mnt" id="h.vhis7vg15mnt

Paths

Shares

Default websites and ports

[http 8530](http 8530)

[https 8531](https 8531)

**Windows Server Update Services Tools**

Windows Server Update Services Tools include the Windows Server Update Services snap-in, WSUS.msc

**WUS SQL Database Tools**

WsusDBHideHidden.sql

``WsusDBMaintenance.sql _Source\[28]_``

``"c:\Program Files\Microsoft SQL Server\90\Tools\binn\SQLCMD.EXE" -S np:\\\\.\pipe\MSSQL$MICROSOFT##SSEE\sql\query -I -i C:\WSUS\WsusDBHideHidden.sql``

``sqlcmd -S np:\\\\.\pipe\MSSQL$MICROSOFT##SSEE\sql\query -I -i C:\WSUS\WsusDBMaintenance.sql``

Windows Client see the other section above?

wuauclt /detectnow

#### Windows Deployment {#h.lxlw5an1cug7" id="h.lxlw5an1cug7

Windows Deployment Role/Feature (WDS)

Windows Automated Installation Kit (WAIK)

MDT

#### PXE {#h.dp9pnycutc7w" id="h.dp9pnycutc7w

DHCP options

**UUID & GUID**

[https://scriptimus.wordpress.com/2012/03/28/mdt-2012-tip-getting-uuid-serialnumber/](https://scriptimus.wordpress.com/2012/03/28/mdt-2012-tip-getting-uuid-serialnumber/)

The last set may often be the MAC address

**Convert**

``\[8 hex]-\[4 hex]-\[4 hex]-\[4 hex]-\[12 hex] (16 bytes?)``

Reverse the octet order in the first three words

1F2E3D4C-1234-5678-90AB-00CDEF001234

4C3D2E1F-3412-7856-90AB-00CDEF001234

AD Users and Computers

Managed Computer

**AD Schema Attributes**

Change AD Computer object to managed computer

Change the GUID/UUID of existing managed computer object

WMI filters

WMIC

### File Sharing, Storage Stuff {#h.d3i2arq2h23v" id="h.d3i2arq2h23v

**File and Storage Services Tools**

File Services Tools include the following: Share and Storage Management Tools; Distributed File System Tools; File Server Resource Manager Tools; Services for NFS Administration Tools; iSCSI management cmdlets for Windows PowerShell

``\- Distributed File System Tools include the DFS Management snap-in, and the **Dfsradmin.exe**, **Dfsrdiag.exe**, **Dfscmd.exe**, **Dfsdiag.exe**, and **Dfsutil.exe** command-line tools.``

``\- File Server Resource Manager tools include the File Server Resource Manager snap-in, and the **Dirquota.exe**, **Filescrn.exe**, and **Storrept.exe** command line tools.``

``\- Share and Storage Management Tools include the Share and Storage Management snap-in.``

#### Distributed File System (DFS) {#h.amxths7cmdmm" id="h.amxths7cmdmm

.DFSFolderLink

**Distributed File System Replication**

DFS Admin Tools listed above/below?

DFS Replication of shared folders will create a temp workspace folder

``\<JUNCTION> D:\UserData\DfsrPrivate \[D:\System Volume Information\DFSR\Private\\{2AB0DFB4-7B9C-4EAE-A77C-``

1AFF95B5EE9A}-{957BE5CA-9DF9-45C1-8916-7B610DA0C897}]

Directory contents:

ConflictAndDeletedManifest.xml

``\<DIR> ConflictAndDeleted``

``\<DIR> Deleted``

``\<DIR> Installing``

``\<DIR> Staging``

#### Storage Manager {#h.jqv43byvq6fi" id="h.jqv43byvq6fi

**Storage Manager for SANs Tools**

Storage Manager for SANs Tools include the Storage Manager for SANs snap-in and the **Provisionstorage.exe** command-line tool.

#### File Server Resource Manager {#h.kt2oarqrjvle" id="h.kt2oarqrjvle

**Default File Groups**

| **File Groups**            | **File Extensions**                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Audio and Video Files\[29] | aac, aif, aiff, asf, asx, au, avi, flac, m3u, mid, midi, mov, mp1, mp2, mp3, mp4, mpa, mpe, mpeg, mpeg2, mpeg3, mpg, ogg, qt, qtw, ram, rm, rmi, rmvb, snd, swf, vob, wav, wax, wma, wmv, wvx                                                                                                                                                                                                                                                                                    |
| Backup Files               | bak, bck, bkf, old                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Compressed Files\[30]      | ace, arc, arj, bhx, bz2, cab, gz, gzip, hpk, hqx, jar, lha, lzh, lzx, pak, pit, rar, sea, sit, sqz, tgz, uu, uue, z, zip, zoo                                                                                                                                                                                                                                                                                                                                                    |
| E-mail Files               | eml, idx, mbox, mbx, msg, ost, otf, pab, pst                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Executable Files\[31]      | bat, cmd, com, cpl, exe, inf, js, jse, msh, msi, msp, ocx, pif, pl, ps1, scr, vb, vbs, wsf, wsh                                                                                                                                                                                                                                                                                                                                                                                  |
| Image Files                | bmp, dib, eps, gif, img, jfif, jpe, jpeg, jpg, pcx, png, ps, psd, raw, rif, spiff, tif, tiff                                                                                                                                                                                                                                                                                                                                                                                     |
| Office Files\[32]          | accdb, accde, accdr, accdt, adn, adp, doc, docm, docx, dot, dotm, dotx, grv, gsa, gta, mad, maf, mda, mda, mda, mdb, mde, mdf, mdf, mdm, mdt, mdw, mdw, mdw, mdz, mpd, mpp, mpt, obt, odb, one, onepkg, pot, potm, potx, ppa, ppam, pps, ppsm, ppsx, ppt, pptm, pptx, pub, pwz, rqy, rtf, rwz, sldm, sldx, slk, thmx, vdx, vsd, vsl, vss, vst, vsu, vsw, vsx, vtx, wbk, wri, xla, xlam, xlb, xlc, xld, xlk, xll, xlm, xls, xlsb, xlsm, xlsx, xlt, xltm, xltx, xlv, xlw, xsf, xsn |
| System Files               | acm, dll, ocx, sys, vxd                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Temporary Files            | \*.temp, \*.tmp, \~\*                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Text Files\[33]            | asc, text, txt                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Web Page Files\[34]        | asp, aspx, cgi, css, dhtml, hta, htm, html, mht, php, php3, shtml, url                                                                                                                                                                                                                                                                                                                                                                                                           |

Audio and Video Files:

``\*.aac, \*.aif, \*.aiff, \*.asf, \*.asx, \*.au, \*.avi, \*.flac, \*.m3u, \*.mid, \*.midi, \*.mov, \*.mp1, \*.mp2, \*.mp3, \*.mp4, \*.mpa, \*.mpe, \*.mpeg, \*.mpeg2, \*.mpeg3, \*.mpg, \*.ogg, \*.qt, \*.qtw, \*.ram, \*.rm, \*.rmi, \*.rmvb, \*.snd, \*.swf, \*.vob, \*.wav, \*.wax, \*.wma, \*.wmv, \*.wvx``

Backup Files

``\*.bak, \*.bck, \*.bkf, \*.old``

Compressed Files

``\*.ace, \*.arc, \*.arj, \*.bhx, \*.bz2, \*.cab, \*.gz, \*.gzip, \*.hpk, \*.hqx, \*.jar, \*.lha, \*.lzh, \*.lzx, \*.pak, \*.pit, \*.rar, \*.sea, \*.sit, \*.sqz, \*.tgz, \*.uu, \*.uue, \*.z, \*.zip, \*.zoo``

E-mail Files

``\*.eml, \*.idx, \*.mbox, \*.mbx, \*.msg, \*.ost, \*.otf, \*.pab, \*.pst``

Executable Files

``\*.bat, \*.cmd, \*.com, \*.cpl, \*.exe, \*.inf, \*.js, \*.jse, \*.msh, \*.msi, \*.msp, \*.ocx, \*.pif, \*.pl, \*.ps1, \*.scr, \*.vb, \*.vbs, \*.wsf, \*.wsh``

Image Files

``\*.bmp, \*.dib, \*.eps, \*.gif, \*.img, \*.jfif, \*.jpe, \*.jpeg, \*.jpg, \*.pcx, \*.png, \*.ps, \*.psd, \*.raw, \*.rif, \*.spiff, \*.tif, \*.tiff``

Office Files

``\*.accdb, \*.accde, \*.accdr, \*.accdt, \*.adn, \*.adp, \*.doc, \*.docm, \*.docx, \*.dot, \*.dotm, \*.dotx, \*.grv, \*.gsa, \*.gta, \*.mad, \*.maf, \*.mda, \*.mda, \*.mda, \*.mdb, \*.mde, \*.mdf, \*.mdf, \*.mdm, \*.mdt, \*.mdw, \*.mdw, \*.mdw, \*.mdz, \*.mpd, \*.mpp, \*.mpt, \*.obt, \*.odb, \*.one, \*.onepkg, \*.pot, \*.potm, \*.potx, \*.ppa, \*.ppam, \*.pps, \*.ppsm, \*.ppsx, \*.ppt, \*.pptm, \*.pptx, \*.pub, \*.pwz, \*.rqy, \*.rtf, \*.rwz, \*.sldm, \*.sldx, \*.slk, \*.thmx, \*.vdx, \*.vsd, \*.vsl, \*.vss, \*.vst, \*.vsu, \*.vsw, \*.vsx, \*.vtx, \*.wbk, \*.wri, \*.xla, \*.xlam, \*.xlb, \*.xlc, \*.xld, \*.xlk, \*.xll, \*.xlm, \*.xls, \*.xlsb, \*.xlsm, \*.xlsx, \*.xlt, \*.xltm, \*.xltx, \*.xlv, \*.xlw, \*.xsf, \*.xsn``

System Files

``\*.acm, \*.dll, \*.ocx, \*.sys, \*.vxd``

Temporary Files

``\*.temp, \*.tmp, \~\*``

Text Files

``\*.asc, \*.text, \*.txt``

Web Page Files

``\*.asp, \*.aspx, \*.cgi, \*.css, \*.dhtml, \*.hta, \*.htm, \*.html, \*.mht, \*.php, \*.php3, \*.shtml, \*.url``

Disk Images

iso, gi, c2d, 2 hyperv, vmware, ima, img

NFS

[http://technet.microsoft.com/en-us/library/cc770454.aspx](http://technet.microsoft.com/en-us/library/cc770988.aspx)

| **Command** | **Description**                                                          |
| ----------- | ------------------------------------------------------------------------ |
| mapadmin    | Manage User Name Mapping for Microsoft Services for Network File System. |
| Mount       | Mount Network File System (NFS) network shares.                          |
| Nfsadmin    | Manage Server for NFS and Client for NFS.                                |
| Nfsshare    | Control Network File System (NFS) shares.                                |
| Nfsstat     | Display or reset counts of calls made to Server for NFS.                 |
| Rpcinfo     | List programs on remote computers.                                       |
| Showmount   | Display mounted directories.                                             |
| Unmount     | Remove Network File System (NFS)-mounted drives.                         |

#### SQL Server {#h.1en0w8gl2q7f" id="h.1en0w8gl2q7f

Microsoft SQL Server

Windows Internal Database

**SQL Server version history**

| **Version** | **Name**           |
| ----------- | ------------------ |
| 6.0         | SQL Server 6.0     |
| 6.5         | SQL Server 6.5     |
| 7.0         | SQL Server 7.0     |
| 8.0         | SQL Server 2000    |
| 9.0         | SQL Server 2005    |
| 10          | SQL Server 2008    |
| 10.5        | SQL Server 2008 R2 |
| 11.0        | SQL Server 2012    |

**SQL Management Tools**

``"c:\Program Files\Microsoft SQL Server\90\Tools\binn\SQLCMD.EXE"``

#### SharePoint {#h.v31lk48cf6c9" id="h.v31lk48cf6c9

#### IIS ? {#h.adamcyip80i2" id="h.adamcyip80i2

#### Failover Clustering {#h.hyg6m1b0ihj0" id="h.hyg6m1b0ihj0

**Failover Clustering Tools**

Failover Cluster Manager, Failover Clusters (Windows PowerShell Cmdlets), MSClus, Cluster.exe

#### Hyper-V {#h.v0kdxulmxd6x" id="h.v0kdxulmxd6x

Default directory for .VHD files

file name for snapshot(s)

**Hyper-V Tools**

Hyper-V Tools include the Hyper-V Manager snap-in and the Virtual Machine Connection remote access tool.

**Windows XP Mode**

default install directory under current user

**App-V**

#### Network Load Balancing {#h.uivr0wjw8tqn" id="h.uivr0wjw8tqn

**Network Load Balancing Tools**

Network Load Balancing Tools include the Network Load Balancing Manager; Network Load Balancing Windows PowerShell Cmdlets; and the NLB.exe and WLBS.exe Command Line Tools.

#### Remote Desktop Services (Terminal Services/RDP) {#h.2qdbmtub0dzw" id="h.2qdbmtub0dzw

``Remote Desktops (%windir%\system32\tsmmc.msc /s) is a great admin tool. It gives one-click access to every server or PC you add to its console.``

**Connect to console with this switch**

A few programs won’t install in a term session, connect on the console.

mstsc.exe /v:myserver /admin

**Remote Desktop Services Tools**

Remote Desktop Services Tools include the Remote Desktop snap-ins; RD Gateway Manager, tsgateway.msc; RD Licensing Manager, licmgr.exe; RD Licensing Diagnoser, lsdiag.msc.

Server Manager should be used for administration of all other RDS role services except RD Gateway and RD Licensing.

[http://technet.microsoft.com/en-us/library/cc725766.aspx](http://technet.microsoft.com/en-us/library/cc725766.aspx)

| **Command**                                                                                                                                           | **Description**                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [Change](http://technet.microsoft.com/en-us/library/cc753982.aspx)                                                                                    | Changes Remote Desktop Session Host (RD Session Host) server settings for logons, COM port mappings, and install mode. |
| [Change logon](http://technet.microsoft.com/en-us/library/cc753586.aspx)                                                                              | Enables or disables logons from client sessions on an RD Session Host server, or displays current logon status.        |
| [Change port](http://technet.microsoft.com/en-us/library/cc752988.aspx)                                                                               | Lists or changes the COM port mappings to be compatible with MS-DOS applications.                                      |
| [Change user](http://technet.microsoft.com/en-us/library/cc770454.aspx)                                                                               | Changes the install mode for the RD Session Host server.                                                               |
| [Chglogon](http://technet.microsoft.com/en-us/library/cc731033.aspx)                                                                                  | Enables or disables logons from client sessions on an RD Session Host server, or displays current logon status.        |
| [Chgport](http://technet.microsoft.com/en-us/library/cc731935.aspx)                                                                                   | Lists or changes the COM port mappings to be compatible with MS-DOS applications.                                      |
| [Chgusr](http://technet.microsoft.com/en-us/library/cc772217.aspx)                                                                                    | Changes the install mode for the RD Session Host server.                                                               |
| [Flattemp](http://technet.microsoft.com/en-us/library/cc730899.aspx)                                                                                  | Enables or disables flat temporary folders.                                                                            |
| [Logoff](http://download.microsoft.com/download/3/b/a/3ba6d659-6e39-4cd7-b3a2-9c96482f5353/Managing%20Roaming%20User%20Data%20Deployment%20Guide.doc) | Logs off a user from a session on an RD Session Host server and deletes the session from the server.                   |
| [Msg](http://technet.microsoft.com/en-us/library/cc725793.aspx)                                                                                       | Sends a message to a user on an RD Session Host server.                                                                |
| [Mstsc](http://technet.microsoft.com/en-us/library/cc732443.aspx)                                                                                     | Creates connections to RD Session Host servers or other remote computers.                                              |
| [Qappsrv](http://nirsoft.net/utils/blue\_screen\_view.html)                                                                                           | Displays a list of all RD Session Host servers on the network.                                                         |
| [Qprocess](http://support.microsoft.com/)                                                                                                             | Displays information about processes that are running on an RD Session Host server.                                    |
| [Query](http://technet.microsoft.com/en-us/library/cc731280.aspx)                                                                                     | Displays information about processes, sessions, and RD Session Host servers.                                           |
| [Query process](http://technet.microsoft.com/en-us/library/cc732101.aspx)                                                                             | Displays information about processes that are running on an RD Session Host server.                                    |
| [Query session](http://windowsitpro.com/windows-server/jsi-tip-0390-registry-entries-ftp-service)                                                     | Displays information about sessions on an RD Session Host server.                                                      |
| [Query termserver](http://technet.microsoft.com/en-us/library/cc771687.aspx)                                                                          | Displays a list of all RD Session Host servers on the network.                                                         |
| [Query user](http://technet.microsoft.com/en-us/library/cc730932.aspx)                                                                                | Displays information about user sessions on an RD Session Host server.                                                 |
| [Quser](http://technet.microsoft.com/en-us/library/cc725942.aspx)                                                                                     | Displays information about user sessions on an RD Session Host server.                                                 |
| [Qwinsta](http://msdn2.microsoft.com/en-us/library/ms984439.aspx)                                                                                     | Displays information about sessions on an RD Session Host server.                                                      |
| [Rdpsign](http://technet.microsoft.com/en-us/library/cc754763.aspx)                                                                                   | Enables you to digitally sign a Remote Desktop Protocol (.rdp) file.                                                   |
| [Reset session](http://support.microsoft.com/kb/103000)                                                                                               | Enables you to reset (delete) a session on an RD Session Host server.                                                  |
| [Rwinsta](http://technet.microsoft.com/en-us/library/cc754785.aspx)                                                                                   | Enables you to reset (delete) a session on an RD Session Host server.                                                  |
| [Shadow](http://technet.microsoft.com/en-us/library/cc754583.aspx)                                                                                    | Enables you to remotely control an active session of another user on an RD Session Host server.                        |
| [Tscon](http://technet.microsoft.com/en-us/library/cc731503.aspx)                                                                                     | Connects to another session on an RD Session Host server.                                                              |
| [Tsdiscon](https://social.technet.microsoft.com/forums/windows/en-US/ae88055e-8484-4580-99e8-80af956da67d/change-mak-to-kms-via-slmgr-upk)            | Disconnects a session from an RD Session Host server.                                                                  |
| [Tskill](http://technet.microsoft.com/en-us/library/cc754256.aspx)                                                                                    | Ends a process running in a session on an RD Session Host server.                                                      |
| [Tsprof](http://www.mydigitallife.info/control-windows-media-player-behaviour-with-command-line-parameters/)                                          | Copies the Remote Desktop Services user configuration information from one user to another.                            |

``\[redo to avoid links from copy/paste?]``

|   |   |
| - | - |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |

Remote App default directory

Remote Desktop Services Licensing Directory

**.RDP File Format**

Starting with RDP version ? (client/server), the .RDP file is now text-based.

``\[Link to source describing all the options available]``

#### Volume Activation {#h.yl23qe3sqda0" id="h.yl23qe3sqda0

Manage Volume Activation, vmw.exe

KMS ?

[http://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx](http://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)

#### Windows System Resource Manager {#h.dnmcr4ij37je" id="h.dnmcr4ij37je

**Windows System Resource Manager Tools**

Windows System Resource Manager Tools include the Windows System Resource Manager snap-in and the **Wsrmc.exe** command-line tool.

### Additional Microsoft Software for Administrators {#h.p8wcbfrqxajt" id="h.p8wcbfrqxajt

#### Microsoft Desktop Optimization Pack (MDOP) {#h.48cbquejjjps" id="h.48cbquejjjps

**Advanced Group Policy Management (AGPM)**

Microsoft AGPM provides comprehensive change control and improved management for Group Policy objects.

**Application Virtualization (App-V)**

Microsoft App-V allows you to make applications available to end user computers without having to install the applications directly on those computers.

**Diagnostics and Recovery Toolset (DaRT)**

Microsoft DaRT lets you diagnose and repair a system that has problems starting or has other issues.

Can only get through Software Assurance of Windows Volume License

**Microsoft BitLocker Administration and Monitoring (MBAM)**

MBAM provides a simplified administrative interface to BitLocker drive encryption.

**Microsoft Enterprise Desktop Virtualization (MED-V)**

MED-V allows you to easily create, deliver and manage corporate Virtual PC images on any Windows-based desktop.

**User Experience Virtualization (UE-V)**

Microsoft UE-V enable users to keep their Windows and application experience regardless of what device they use to access Windows and those applications.

#### Microsoft Toolkits {#h.3o2gmdy1l31e" id="h.3o2gmdy1l31e

WAIK

MAP

MDT

MBSA

USMT

MACP

MSCM

#### Admin Tools {#h.h2168v27zqo8" id="h.h2168v27zqo8

Chart: Version, runs on client ver, manages server ver

**Hyper-V**

Manage 2012 Hyper-V from Windows 8

Hyper-V Manager 2008 cannot manage Hyper-V 2012.

Management tool is not in RSAT and already part of the available features.

**Windows 2012/8 Server Manager Managing Downlevel (2008) Servers**

Installing PowerShell https://technet.microsoft.com/en-us/library/hh847837.aspx

#### Services for Unix (SFU) {#h.b35elgivool4" id="h.b35elgivool4

#### SQL Management {#h.zca1z5j5agb0" id="h.zca1z5j5agb0

#### Administrative {#h.zfvb2ac5uxa1" id="h.zfvb2ac5uxa1

Microsoft Assessment and Planning (MAP) Toolkit performs audits and discovery of operating systems, Exchange & SQL servers

Microsoft Baseline Security Analyzer

Microsoft IT Environment Health Scanner

AD Replication Status Tool

Microsoft Network Monitor

Microsoft Active Directory Topology Diagrammer

Office Viewers and Converters, Microsoft Mathematics

Microsoft Enhanced Mitigation Experience Toolkit (EMET)

lock down lab tool, no longer supported

#### Programming and Development {#h.smcfngqbli6" id="h.smcfngqbli6

Visual Studio

Web

Scripting (See PowerShell and WMI)

Windows Deployment Kit & Assessment and Deployment Kit (Deploy/WAIK above)

Windows Software Dev Kit

Orca

#### Misc {#h.mg6xzr53wgn2" id="h.mg6xzr53wgn2

Microsoft Live Essentials

BING

SkyDrive

XML Notepad

DirectX

Visual C++ Redistributable

Microsoft Download Manager

WGA

Microsoft Silverlight

Microsoft Touch programs

Vista Ultimate add-ons

Other Windows add-ons

#### Other Programs {#h.wioxqkuchmx3" id="h.wioxqkuchmx3

**Apple**

iTunes, QuickTime, Safari

**Adobe**

Flash, Air, Reader, Shockwave

**Sun/Oracle Java**

**WinZip**

**Toolbars**

Google

AOL

Yahoo

Ask Jeeves (installed by Java updates)

Microsoft Bing

``Free Games installed by OEM (Conexant\<?>)``

**Anti-Virus**

Symantec

McAfee

Grisoft AVG

Microsoft Defender, Security Essentials

**Remote Control**

WebEx, GoToMyPc, LogMeIn

**Additional Enterprise Configuration or Deployment Tools**

Create MST, GPO, MSI

Adobe

Apple

Google Chrome

Mozilla Firefox

### Windows Domain and Active Directory paths {#h.i85qe6xf7cfv" id="h.i85qe6xf7cfv

![A screenshot of a computer

Description automatically generated](.gitbook/assets/0.png)

Database folder

``C:\Windows\NTDS``

Log files folder

``C:\Windows\NTDS``

SYSVOL folder

``C:\Windows SYSVOL``

``NTDS and \_?\_ folder location can be customized during installation of Active Directory role.``

| **DB/Log/Sys** | **File**           |                                                                                                                                                                                |
| -------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| NTDS           | edb.chk            | The file that is used to track the point up to which transactions in the log file have been committed.                                                                         |
| NTDS           | edb.log            | The log file into which directory transactions are written before being committed to the database file.                                                                        |
| NTDS           | edb00085.log       | Active Directory creates additional log files as necessary as existing log files fill up. Each log file has a fixed size of 10 MB.                                             |
| NTDS           | edbres00001.jrs    | ? Files that are used to reserve space for additional log files if EDB.LOG becomes full.                                                                                       |
| NTDS           | edbres00002.jrs    | ? Files that are used to reserve space for additional log files if EDB.LOG becomes full.                                                                                       |
| NTDS           | edbtmp.log         |                                                                                                                                                                                |
| NTDS           | ntds.dit           | The physical database file in which all directory data is stored. This file consists of three internal tables: the data table, link table, and security descriptor (SD) table. |
| NTDS           | temp.edb           |                                                                                                                                                                                |
| SYSVOL         | domain             |                                                                                                                                                                                |
| SYSVOL         | staging            |                                                                                                                                                                                |
| SYSVOL         | staging areas      |                                                                                                                                                                                |
| SYSVOL         | sysvol             |                                                                                                                                                                                |
|                | domain\Policies    |                                                                                                                                                                                |
|                | domain\scripts     |                                                                                                                                                                                |
|                | domain\StarterGPOs |                                                                                                                                                                                |

#### Logon Scripts {#h.afrre0bnquyx" id="h.afrre0bnquyx

``%Systemroot%\System32\Repl\Import\Scripts``

``%SystemRoot%\sysvol\sysvol\\_\<domain DNS name>_\scripts``

``\\\\_\<Server>_\NETLOGON``

``\\\\_\<Server>_\SYSVOL\\_\<domain DNS name>_\scripts``

**How to reference paths in logon scripts**

``An example of a batch file Logon script that launches a VBScript program is as follows\[35]:``

@echo off

``wscript %0\\..\NetLogon.vbs``

``The "%0" in the batch file is interpreted by the command processor to be the name and path of the current file, which is the batch file itself. The string "%0\\..\\" then becomes the folder where the batch file is stored. The batch file above will launch the VBScript program NetLogon.vbs as long as it is saved in the NetLogon share with the batch file. This syntax is preferable to a UNC path, because it does not hard code the name of a Domain Controller. The syntax will work no matter which Domain Controller authenticates the user. The logon script will work no matter which Domain Controllers are available or where in the network the user logs on.``

Also to force a path to the current directory

``PUSHD %\~dp0``

#### Replication {#h.bbdnu95mten3" id="h.bbdnu95mten3

``Regular replication of logon scripts, group policy files, performed by \_\_``

DFS Replication, see above

#### Group Policy Objects {#h.l55boztd7p4b" id="h.l55boztd7p4b

Physical Path

``%SystemRoot%\sysvol\sysvol\\_\<domain DNS name>_\Policies\\_\<GUID>_\user\scripts\logon``

Network Path

``\\\\_\<AD Server>_\sysvol\\_\<domain DNS name>_\Policies\\_\<GUID>_\user\scripts\logon``

``\\\\_\<AD Server>_\sysvol\\_\<domain DNS name>_\Policies\\_\<GUID>_\user\scripts\logoff``

``\\\\_\<AD Server>_\sysvol\\_\<domain DNS name>_\Policies\\_\<GUID>_\machine\scripts\startup``

``\\\\_\<AD Server>_\sysvol\\_\<domain DNS name>_\Policies\\_\<GUID>_\machine\scripts\shutdown``

``%SystemRoot%\system32\repl\import\scripts``

#### GPO Template (.ADMX) files {#h.x7zefdpddhjv" id="h.x7zefdpddhjv

Only need to be present on the machine where the policies are edited from

``.ADMX %systemroot%\PolicyDefinitions``

``.ADML %systemroot%\PolicyDefinitions\en-US``

ADM (Group Policy Editor, Add/Remove Template Wizard)

``C:\Windows\PolicyDefinitions``

**Group Policy Management Tools**

Group Policy Management Tools include Group Policy Management Console, Group Policy Management Editor, and Group Policy Starter GPO Editor.

#### Paths for User Accounts {#h.ti90pi3cr8i1" id="h.ti90pi3cr8i1

**User Home folder and Profile path differences**

also see Remote Desktop Services User Profile, Profile Path and Remote Desktop Services Home Folder

see also Personal Virtual Desktop and UNIX Attributes

**Roaming Profiles**

Managing Roaming User Data Deployment Guide

``[http://download.microsoft.com/download/3/b/a/3ba6d659-6e39-4cd7-b3a2-9c96482f5353/Managing%20Roaming%20User%20Data%20Deployment%20Guide.doc](http://technet.microsoft.com/en-us/library/cc731728.aspx)``

**Different types of profiles**

Local, Roaming, Terminal Server, etc.

#### DNS entries for Active Directory Domains {#h.pz095n1sq406" id="h.pz095n1sq406

Not a file/folder path, but part of UNC and name resolution for network access

|                                 |              |                          |
| ------------------------------- | ------------ | ------------------------ |
| mydomainname.com                | SRV          | \_gc.\_tcp               |
|                                 |              | \_kerberos.\_tcp         |
|                                 |              | \_kpasswd.\_tcp          |
|                                 |              | \_ldap.\_tcp             |
| KMS server                      | SRV          | \_vlmcs.\_tcp            |
| DomainDnsZones.mydomainname.com | \_sites      | \_ldap.\_tcp.\<sitename> |
| DomainDnsZones.mydomainname.com | \_ldap.\_tcp |                          |
| ForestDnsZones                  |              |                          |

Exchange uses sites to match users to servers

**Additional special DNS records**

Exchange autodiscover srv record, autodiscover host name

Cisco Wireless cisco-capwap-controller or cisco-lwapp-controller

``Internet Explorer proxy autoconfig\[36] wpad``

KMS

Active-Directory based activation

See DNS Server above

Even Active Directory stored DNS zones can be written to a local file by using the export command.

Example:

``\_\_\_\_\_\_\_\_\_\_?``

They will then be written to the following folder path:

``\_\_\_\_?``

``C:\Windows\System32\dns\backup``

``nslookup -type=srv \_vlmcs.\_tcp``

**Backup/Export AD integrated zone to text file**

``DnsCmd \<ServerName> /ZoneExport \<ZoneName> \<ZoneExportFile>``

#### Certificate Services {#h.k7tbyipc0zj3" id="h.k7tbyipc0zj3

Some Certificate tools will be included in the Office-VBA section above

**Active Directory Certificate Services Tools**

Active Directory Certificate Services Tools includes the Certification Authority, Certificate Templates, Enterprise PKI, and Online Responder Management snap-ins.

[http://technet.microsoft.com/en-us/library/cc772497.aspx](http://technet.microsoft.com/en-us/library/cc772497.aspx)

| Command                                                                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Certreq](http://www.swiftforensics.com/2012/08/tracking-usb-first-insertion-in-event.html) | <p>Certreq can be used to:</p><ol><li>Request certificates from a certification authority (CA).</li><li>Retrieve a response to a previous request from a CA.</li><li>Create a new request from an .inf file.</li><li>Accept and install a response to a request.</li><li>Construct a cross-certification or qualified subordination request from an existing CA certificate or request.</li><li>Sign a cross-certification or qualified subordination request.</li></ol> |
| [Certutil](http://technet.microsoft.com/en-us/library/cc731968.aspx)                        | Displays certification configuration information, and configures Certificate Services.                                                                                                                                                                                                                                                                                                                                                                                   |

### Active Directory (LDAP) Database {#h.gd194euzmf7w" id="h.gd194euzmf7w

AD LDAP database entries and paths will be in a separate document.

AD versions and supported OS will be in a separate document.

See Link to: ?

``[http://technet.microsoft.com/en-us/library/cc772829%28WS.10%29.aspx](http://technet.microsoft.com/en-us/library/cc732887.aspx)``

Active Directory Technical References

``http://technet.microsoft.com/en-us/library/cc759186%28v=ws.10%29.aspx``

**Connecting Networkable Hardware**

Some networked copiers can connect to a LDAP database for an address book for email destinations or usernames for security.

One example of connecting and using an address book for names/dept/phone/email is above in Outlook, Add Address Book

#### AD Utilities {#h.u1ptx3w39kqq" id="h.u1ptx3w39kqq

A few tools will be included here, see other AD document for better information.

[http://www.ucertify.com/blog/windows-server-2008-tools-used-for-configuring-and-maintaining-active-directory.html](http://www.ucertify.com/blog/windows-server-2008-tools-used-for-configuring-and-maintaining-active-directory.html)

``%windir%\system32\dsac.exe Active Directory Administrative Center``

``%SystemRoot%\system32\dsa.msc Active Directory Users and Computers``

``After Windows version \_?\_ the RAS tab was removed. Exchange 2003? installs extended version in ?``

What attributes are carried across (and which will not) when copying a user.

``ADSI.exe (or mmc or msc?) ADSI Edit MMC (adsiedit.msc)? %SystemRoot%\system32\adsiedit.msc``

``C:\Windows\System32\LDP.exe``

``C:\Windows\System32\ldifde.exe``

``C:\Windows\System32\Ntdsutil.exe (Windows Server 2003, Windows Server 2003 R2, Windows Server 2003 with SP1, Windows Server 2008, Windows Server 2008 R2) (Ntdsutil.exe is built into Windows Server 2008 and Windows Server 2008 R2. It is available if you have the AD DS or the AD LDS server role installed. It is also available if you install the Active Directory Domain Services Tools that are part of the Remote Server Administration Tools (RSAT). If you have the AD LDS server role installed but not the AD DS server role, you can use the dsdbutil.exe and dsmgmt.exe command-line tools to perform the same tasks http://technet.microsoft.com/en-us/library/cc753343%28v=ws.10%29.aspx)``

``C:\Windows\System32\Dsdbutil.exe``

repadmin

DCPROMO

tool to extend schema (Windows server upgrades or exchange install)

dsmgmt.exe

Schmmgmt.dll Active Directory Schema snap-in

Which AD GUI tools have Advanced views to enable?

``DNS, AD UC (Object tab), AD S\&S (Services)``

**Delegwiz.inf**

**CSVDE**

**LDAP Import/Export File (LDIFDE)**

LDIF Directory Exchange

You can export and import information. Export user accounts and then open in Excel for sorting or analysis.

**Directory Service Utility (NTDSUtil)**

ntdsutil.exe /?

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsdbutil performs database maintenance of the Active Directory Domain Services store

and facilitates configuration of AD LDS communication ports and view AD LDS

instances installed on a machine.

``\------------------------\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*--------------------``

#### Directory Service Database Util (DSDBUtil) {#h.fo0d5r65ymmq" id="h.fo0d5r65ymmq

``C:\\>dsdbutil.exe /?``

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsdbutil performs database maintenance of the Active Directory Domain Services store

and facilitates configuration of AD LDS communication ports and view AD LDS

instances installed on a machine.

``C:\Windows\System32>dsmgmt.exe /?``

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsmgmt facilitates managing AD DS/LDS application partitions, management

and control of the Flexible Single Master Operations (FSMO),

and cleaning up of metadata left behind by abandoned AD DCs/LDS instances,

those which are removed from the network without being uninstalled.

#### Edit Objects in Active Directory {#h.5ueexcyelrvy" id="h.5ueexcyelrvy

#### DSMove {#h.2fh0o7z9ccwe" id="h.2fh0o7z9ccwe

``C:\Windows\System32>dsmove.exe /?``

Description: This command moves or renames an object within the directory.

**DS Modify Object (DSMOD)**

``C:\Windows\System32\dsmod.exe /?``

Description: This dsmod command modifies existing objects in the directory.

**AD Command line tools**

dsac.exe

dsacls.exe

dsadd.exe

dsdbutil.exe

dsget.exe

dsmgmt.exe

dsmod.exe

dsmove.exe

dsquery.exe

dsrm.exe

#### Active Directory Domain Services Command Reference {#h.b38vxxqc2f1i" id="h.b38vxxqc2f1i

[http://technet.microsoft.com/en-us/library/cc771131.aspx](http://www.microsoft.com/en-us/download/details.aspx)

| **Command**                                                                                                                                        | **Description**                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Adprep](http://www.grimadmin.com/article.php/creating-modifying-windows-7-libraries)                                                              | Extends the Active Directory schema and updates permissions as necessary to prepare a forest and domain for a domain controller that runs the Windows Server 2008 operating system.                                 |
| [Csvde](http://technet.microsoft.com/en-us/library/cc742118.aspx)                                                                                  | Imports and exports data from Active Directory using files that store data in the comma-separated value (CSV) format. You can also support batch operations based on the CSV file format standard.                  |
| [Dcdiag](http://www.forensickb.com/2009/01/windows-event-logs.html)                                                                                | Analyzes the state of domain controllers in a forest or enterprise and reports any problems to help in troubleshooting.                                                                                             |
| [Dcpromo](http://technet.microsoft.com/en-us/library/cc742035.aspx)                                                                                | Installs and removes Active Directory Domain Services (AD DS).                                                                                                                                                      |
| [Dsacls](http://technet.microsoft.com/en-us/library/cc732473.aspx)                                                                                 | Displays and changes permissions (access control entries) in the access control list (ACL) of objects in AD DS.                                                                                                     |
| [Dsadd](http://technet.microsoft.com/en-us/library/cc788054.aspx)                                                                                  | Adds specific types of objects to the directory.                                                                                                                                                                    |
| [Dsamain](http://technet.microsoft.com/en-us/library/cc788125.aspx)                                                                                | Exposes Active Directory data that is stored in a snapshot or backup as a Lightweight Directory Access Protocol (LDAP) server.                                                                                      |
| [Dsdbutil](http://technet.microsoft.com/en-us/library/cc732952.aspx)                                                                               | Provides database utilities for Active Directory Lightweight Directory Services (AD LDS).                                                                                                                           |
| [Dsget](http://technet.microsoft.com/en-us/library/cc788046.aspx)                                                                                  | Displays the selected properties of a specific object in the directory.                                                                                                                                             |
| [Dsmgmt](http://technet.microsoft.com/en-us/library/cc785434.aspx)                                                                                 | Provides management facilities for Active Directory Lightweight Directory Services (AD LDS).                                                                                                                        |
| [Dsmod](http://windowsitpro.com/windows/jsi-tip-2385-how-do-i-change-windows-2000-telnet-service-greeting-prompt-etc)                              | Modifies an existing object of a specific type in the directory.                                                                                                                                                    |
| [Dsmove](http://go.microsoft.com/fwlink/)                                                                                                          | Moves a single object in a domain from its current location in the directory to a new location or renames a single object without moving it in the directory tree.                                                  |
| [Dsquery](http://support.microsoft.com/kb/141705)                                                                                                  | Queries AD DS according to specified criteria.                                                                                                                                                                      |
| [Dsrm](http://windowsitpro.com/windows-server/jsi-tip-7142-registry-entries-telnet-server-service)                                                 | Deletes an object of a specific type or any general object from the directory.                                                                                                                                      |
| [Ldifde](http://technet.microsoft.com/en-us/library/cc771865.aspx)                                                                                 | Creates, modifies, and deletes directory objects on computers running Windows Server 2003 or Windows XP Professional operating systems.                                                                             |
| [Ldp](http://technet.microsoft.com/en-us/library/cc753101.aspx)                                                                                    | Makes it possible for users to perform operations against an LDAP-compatible directory, such as AD DS. These operations include connect, bind, search, modify, add, and delete.                                     |
| [Netdom](http://technet.microsoft.com/en-us/library/cc770885.aspx)                                                                                 | Makes it possible for administrators to manage Windows Server 2003 and Windows 2000 domains and trust relationships from a command prompt.                                                                          |
| [Net computer](http://technet.microsoft.com/en-us/library/cc770619.aspx)                                                                           | Adds or deletes a computer from a domain database.                                                                                                                                                                  |
| [Net group](http://technet.microsoft.com/en-us/library/cc771655.aspx)                                                                              | Adds, displays, or modifies global groups in domains.                                                                                                                                                               |
| [Net user](http://technet.microsoft.com/en-us/library/cc770592.aspx)                                                                               | Adds or modifies user accounts, or displays user account information.                                                                                                                                               |
| [Nltest](http://go.microsoft.com/fwlink/)                                                                                                          | Performs network administrative tasks.                                                                                                                                                                              |
| [Ntdsutil](http://technet.microsoft.com/en-us/library/cc753343.aspx)                                                                               | Provides management facilities for AD DS.                                                                                                                                                                           |
| [Redircmp](http://technet.microsoft.com/en-us/library/dd297932\(v=exchg.141\).aspx)                                                                | Redirects the default container for newly created computers to a specified target organizational unit (OU) so that newly created computer objects are created in the specific target OU instead of in CN=Computers. |
| [Redirusr](http://support.microsoft.com/kb/2919355)                                                                                                | Redirects the default container for newly created users to a specified target OU so that newly created user objects are created in the specific target OU instead of in CN=Users.                                   |
| [Repadmin](http://technet.microsoft.com/en-us/library/ee624057.aspx)                                                                               | Makes it possible for administrators to diagnose Active Directory replication problems between domain controllers running Windows operating systems.                                                                |
| [Setspn](http://www.windowsnetworking.com/kbase/WindowsTips/WindowsXP/AdminTips/Network/SharedprinterseparatorpageforWindows2000andWindowsXP.html) | Makes it possible for administrators to read, modify, and delete the Service Principal Names (SPN) directory property for an Active Directory service account.                                                      |

**Remote Server Administration Tools technology**

``Active Directory Domain Services (AD DS) Tools and Active Directory Lightweight Directory Services (AD LDS) Tools\[37]``

Active Directory Domain Services (AD DS) and Active Directory Lightweight Directory Services (AD LDS) Tools includes Active Directory Administrative Center; Active Directory Domains and Trusts; Active Directory Sites and Services; Active Directory Users and Computers; ADSI Edit; DCPromo.exe; LDP.exe; NetDom.exe; NTDSUtil.exe; RepAdmin.exe; Active Directory module for Windows PowerShell; DCDiag.exe; DSACLs.exe; DSAdd.exe; DSDBUtil.exe; DSMgmt.exe; DSMod.exe; DSMove.exe; DSQuery.exe; DSRm.exe;

GPFixup.exe; KSetup.exe; KtPass.exe; NlTest.exe; NSLookup.exe; W32tm.exe.

``\- Server for NIS Tools includes an extension to the Active Directory Users and Computers snap-in, and the **Ypclear.exe** command-line tool.``

Move the above into table below

|                            |                                                |
| -------------------------- | ---------------------------------------------- |
| %windir%\system32\dsac.exe | Active Directory Administrative Center         |
| mmc                        | Active Directory Domains and Trusts            |
| mmc                        | Active Directory Sites and Services            |
|                            | Active Directory Users and Computers           |
|                            | ADSI Edit                                      |
| DCPromo.exe                |                                                |
| LDP.exe                    |                                                |
| NetDom.exe                 |                                                |
| NTDSUtil.exe               |                                                |
| RepAdmin.exe               |                                                |
|                            | Active Directory module for Windows PowerShell |
| DCDiag.exe                 |                                                |
| DSACLs.exe                 |                                                |
| DSAdd.exe                  |                                                |
| DSDBUtil.exe               |                                                |
| DSMgmt.exe                 |                                                |
| DSMod.exe                  |                                                |
| DSMove.exe                 |                                                |
| DSQuery.exe                |                                                |
| DSRm.exe                   |                                                |
|                            |                                                |
| GPFixup.exe                |                                                |
| KSetup.exe                 |                                                |
| KtPass.exe                 |                                                |
| NlTest.exe                 |                                                |
|                            |                                                |
| NSLookup.exe               |                                                |
|                            |                                                |
| W32Tm.exe                  |                                                |

#### Active Directory Lightweight Directory Services {#h.74vxzvgmrjym" id="h.74vxzvgmrjym

Available in the following operating systems:

Windows Server 2012

Windows 8

Windows Server 2008 and Windows Server 2008 R2

``Windows 7 (separate download\[38])``

AD LDS is not supported on Windows Vista and earlier clients.

**AD LDS Features**

AD LDS features can be installed in the following operating systems:

``Dynamic list of LDAP Data Interchange Format (LDIF) files during instance setup With this feature, you can make custom LDIF files available during AD LDS instance setup—in addition to the default LDIF files that are provided with AD LDS—by adding the files to the %systemroot%\ADAM directory.``

``[http://technet.microsoft.com/en-us/library/cc754361%28v=ws.10%29.aspx](http://go.microsoft.com/fwlink/)``

Manage AD LDS instances by using the ADSI Edit MMC snap-in.

#### Active Directory Application Mode (ADAM) {#h.j7fsosvjlxyg" id="h.j7fsosvjlxyg

For organizations that require flexible support for directory-enabled applications, Microsoft has developed ADAM, which is an LDAP directory service that runs as a user service, rather than as a system service.

KB902838

[http://www.microsoft.com/en-us/download/details.aspx?id=4201](http://www.askvg.com/revealing-interesting-secret-behind-windows-build-numbers/?id=4201)

#### Active Directory Web Services (ADWS) {#h.ell1a23jtwxe" id="h.ell1a23jtwxe

#### Active Directory Database Mounting Tool {#h.1w4f0q5upgkt" id="h.1w4f0q5upgkt

#### Active Directory Recycle Bin {#h.hfhyke16bavk" id="h.hfhyke16bavk

``1. Not used, group policy or partial solution use \Default\Favorites instead. ↑``
2. [http://support.microsoft.com/kb/971760](http://support.microsoft.com/kb/971760) ↑
3. [http://support.microsoft.com/kb/2667628](http://support.microsoft.com/kb/2667628) ↑
4. Source Windows 2003 ↑
5. [http://support.microsoft.com/?kbid=974674](http://support.microsoft.com/?kbid=974674) ↑
6. [http://support.microsoft.com/kb/836961](http://support.microsoft.com/kb/836961) ↑
7. RegEdit.exe can load registry hives and edit registry value security since Windows version ? ↑
``8.  [http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/ntbackup\_command.mspx?mfr=true](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/ntbackup\_command.mspx?mfr=true)``

    [http://en.wikipedia.org/wiki/NTBackup](http://en.wikipedia.org/wiki/NTBackup) ↑
9. [http://office.microsoft.com/en-us/outlook-help/copy-outlook-express-address-book-contacts-to-outlook-HA001091960.aspx](http://office.microsoft.com/en-us/outlook-help/copy-outlook-express-address-book-contacts-to-outlook-HA001091960.aspx) ↑
``10. [http://technet.microsoft.com/en-us/library/cc179199%28v=office.14%29.aspx](http://technet.microsoft.com/en-us/library/cc179199\(v=office.14\).aspx) ↑``
``11. [http://technet.microsoft.com/en-us/library/cc179110%28v=office.14%29.aspx](http://technet.microsoft.com/en-us/library/cc179110\(v=office.14\).aspx) ↑``
``12. [http://www.networksteve.com/exchange/topic.php/Different\_work\_day\_times/?TopicId=8284\&Posts=6](http://www.networksteve.com/exchange/topic.php/Different\_work\_day\_times/?TopicId=8284\&Posts=6) ↑``
13. [http://office.microsoft.com/en-us/outlook-help/blocked-attachments-in-outlook-HA001229952.aspx](http://office.microsoft.com/en-us/outlook-help/blocked-attachments-in-outlook-HA001229952.aspx) ↑
``14. [http://www.nirsoft.net/utils/outlook\_nk2\_edit.html](http://www.nirsoft.net/utils/outlook\_nk2\_edit.html) ↑``
``15. [Outlook 2010 Home > Outlook 2010 Help and How-To > Getting help - What is the Enable logging (troubleshooting) option?](http://www.google.com/url?q=http%3A%2F%2Foffice.microsoft.com%2Fclient%2Fhelppreview14.aspx%3FAssetId%3DHA010356489%26lcid%3D1033%26NS%3DOUTLOOK%26Version%3D14%26tl%3D2%26respos%3D0%26CTT%3D1%26queryid%3D8a421809%252D143f%252D477d%252D873e%252D1c1c82f79a17%23\_Toc261091100\&sa=D\&sntz=1\&usg=AFQjCNFrnL0SZMZcpmW3f1CaskdXGOpjGQ) ↑``
16. [http://support.mozilla.org/en-US/kb/profiles-where-firefox-stores-user-data](http://support.mozilla.org/en-US/kb/profiles-where-firefox-stores-user-data) ↑
``17. [http://www.adobe.com/devnet/flashplayer/articles/flash\_player\_admin\_guide.html](http://www.adobe.com/devnet/flashplayer/articles/flash\_player\_admin\_guide.html) ↑``
18. Choose iTunes Library by holding Shift while starting iTunes ↑
19. [http://www.makeuseof.com/tag/10-top-itunes-troubleshooting-tips-tricks/](http://www.makeuseof.com/tag/10-top-itunes-troubleshooting-tips-tricks/) ↑
20. [http://support.apple.com/kb/TS1717](http://support.apple.com/kb/TS1717) ↑
21. [http://support.apple.com/kb/TS1421](http://support.apple.com/kb/TS1421) ↑
22. [http://support.apple.com/kb/TS1776](http://support.apple.com/kb/TS1776) ↑
``23. [http://java.com/en/download/help/msi\_install.xml](http://java.com/en/download/help/msi\_install.xml) ↑``
``24. [http://www.java.com/en/download/help/plugin\_cache.xml](http://www.java.com/en/download/help/plugin\_cache.xml) ↑``
25. [http://docs.oracle.com/javase/7/docs/technotes/guides/jweb/client-security.html#install](http://docs.oracle.com/javase/7/docs/technotes/guides/jweb/client-security.html#install) ↑
26. [http://www.mombu.com/microsoft/iis-smtp-and-nntp/t-some-emails-stuck-in-drop-folder-1028192.html](http://www.mombu.com/microsoft/iis-smtp-and-nntp/t-some-emails-stuck-in-drop-folder-1028192.html) ↑
27. [http://support.microsoft.com/?id=297700](http://support.microsoft.com/?id=297700) ↑
28. ↑
``29. I suggest adding \*.divx, \*.mkv, \*.vob, \*.flv ↑``
``30. I suggest adding \*.tar, \*.7z, \*.ex\_, \*.dl\_ ↑``
``31. I suggest adding php, perl, ext (.ps1) for powershell2? List of OS recognized ext can be found in reg key \_\_\_? or win.ini? What does Outlook consider level 1? ↑``
``32. May want to include \*.wp?, \*.pdf, \*.cbx, \*.wk? ↑``
``33. I suggest adding \*.me, \*.1st, \*.diz ↑``
``34. I suggest adding \*.webpage for Mozilla shortcuts ? ↑``
35. [http://www.winvistatips.com/windows-98-logon-scripts-2003server-t675450.html](http://www.winvistatips.com/windows-98-logon-scripts-2003server-t675450.html) ↑
``36. [http://en.wikipedia.org/wiki/Web\_Proxy\_Autodiscovery\_Protocol](http://en.wikipedia.org/wiki/Web\_Proxy\_Autodiscovery\_Protocol) ↑``
37. [http://social.technet.microsoft.com/wiki/contents/articles/2202.remote-server-administration-tools-rsat-for-windows-vista-windows-7-windows-8-windows-server-2008-windows-server-2008-r2-and-windows-server-2012-dsforum2wiki.aspx](http://social.technet.microsoft.com/wiki/contents/articles/2202.remote-server-administration-tools-rsat-for-windows-vista-windows-7-windows-8-windows-server-2008-windows-server-2008-r2-and-windows-server-2012-dsforum2wiki.aspx) ↑
38. [http://www.microsoft.com/en-us/download/details.aspx?id=14683](http://www.microsoft.com/en-us/download/details.aspx?id=14683) ↑
