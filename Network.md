#### Network {#network}

``C:\Windows\System32\drivers\etc\hosts``

(Take ownership to edit file)

`C:\Windows\System32\ras`

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
| dhcp        | Changes to the `netsh dhcp` context.                 |
| dhcpclient  | Changes to the `netsh dhcpclient` context.           |
| dnsclient   | Changes to the `netsh dnsclient` context.            |
| dump        | Displays a configuration script.                      |
| exec        | Runs a script file.                                   |
| exit        | Exits the program.                                    |
| firewall    | Changes to the `netsh firewall` context.             |
| help        | Displays a list of commands.                          |
| http        | Changes to the `netsh http` context.                 |
| interface   | Changes to the `netsh interface` context.            |
| ipsec       | Changes to the `netsh ipsec` context.                |
| lan         | Changes to the `netsh lan` context.                  |
| mbn         | Changes to the `netsh mbn` context.                  |
| namespace   | Changes to the `netsh namespace` context.            |
| nap         | Changes to the `netsh nap` context.                  |
| netio       | Changes to the `netsh netio` context.                |
| offline     | Sets the current mode to offline.                     |
| online      | Sets the current mode to online.                      |
| p2p         | Changes to the `netsh p2p` context.                  |
| popd        | Pops a context from the stack.                        |
| pushd       | Pushes current context on stack.                      |
| quit        | Exits the program.                                    |
| ras         | Changes to the `netsh ras` context.                  |
| rpc         | Changes to the `netsh rpc` context.                  |
| set         | Updates configuration settings.                       |
| show        | Displays information.                                 |
| trace       | Changes to the `netsh trace` context.                |
| unalias     | Deletes an alias.                                     |
| wcn         | Changes to the `netsh wcn` context.                  |
| wfp         | Changes to the `netsh wfp` context.                  |
| winhttp     | Changes to the `netsh winhttp` context.              |
| winsock     | Changes to the `netsh winsock` context.              |
| wlan        | Changes to the `netsh wlan` context.                 |

**3 netsh commands that may fix a broken Windows network**

Reset TCP/IP Network Stack

`netsh int ip reset resetlog.txt`

Reset Winsock using netsh. If you have a LSP that is corrupted and causing network connectivity problems, this command should repair that. Note that if you run this command, you may have to re-install several programs that had LSPs installed previously, such as Google Desktop Search, etc.

`netsh winsock reset catalog`

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

## SNMP
*go to* (Network/Net-SNMP.md)


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

`net view`

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

```
8.8.8.8

8.8.4.4
```

``verified as of [Publication Date]``

_space provided for writing notes_

_Suggest writing some addresses on back, inside cover_
