# Appendices

### Appendices

Lists of

Forensic Areas

Run commands

Registry key list?

(Environmental) Variables lists?

List of all files in plain install?

List of all files on install CD?

List of all files in SFC list?

Index of files in document?

Index of Tables in document?

List of sources?

List of copyrights?

Copyright, Citation example(s)

Ordering/Purchasing Information (ebook limit 5-page copy, 10-page print?) ebook included with each paper-back copy

Codex? Revisions? Version/printing/history? Submit corrections/content requests contact info

About the cover art

Biography about the author, information how to contact or follow the author

Other books available: NT File System, AD/LDAP Database, Group Policies, Windows Administration methods, tools, scripts and examples (how-to use tools/commands discussed here and more 3rd-party tools with real-world examples and guides)

* Windows Versions

* Run... Commands

* Windows Start Menu structure and contents

* Windows Components (Add/Remove Features and Roles)

* Microsoft Office Components

* Windows Event Logs

* Windows Explorer and File dialog box

* File and Directory Contents lists

* Command Syntax Help



#### Forensically interesting spots in the Windows 7, Vista and XP file system and registry {#Forensically-interesting}

``[http://www.irongeek.com/i.php?page=security/windows-forensics-registry-and-file-system-spots\&mode=print](http://technet.microsoft.com/en-us/library/cc754051.aspx?page=security/windows-forensics-registry-and-file-system-spots\&mode=print)``

Windows Explorer:

Recently opened files from Windows Explorer

``C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Recent``

Network Shortcuts

``C:\Users\\\<user name>\AppData\Roaming\Microsoft\Windows\Network Shortcuts``

Items recently ran from the "Run" bar

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU``

common file save/open dialog, recently opened/saved files

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePidlMRU``

Recent Docs

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs``

EXE to main window title cache

``HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell\MuiCache``

User Assist

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist``

Didier Stevens has a tool for parsing the data here:

[http://blog.didierstevens.com/programs/userassist/](http://blog.didierstevens.com/programs/userassist/)

Windows:

Temp folder

``C:\Users\\\<user name>\AppData\Local\Temp``

Recycle Bin

``C:\\$Recycle.Bin``

Last logged on user

``HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon``

Event logs

`C:\Windows\System32\config`

`C:\Windows\System32\winevt\Logs`

`*.evt and *.evtx`

Last key edited by RegEdit

``HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\Regedit``

List of Installed USB devices, both connected and unconnected

``HKLM\SYSTEM\CurrentControlSet\Enum\USB``

List of installed USB storage devices

``HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR``

SetupAPI Device Log

``C:\windows\inf\setupapi.dev.log``

includes what USB devices have been installed

Windows Prefetch

``C:\Windows\Prefetch``

meant to speed up commonly executed application and boot load times by recording what on the system is accessed.

Mark McKinnon has a tool you might be interested in for parsing this data. Also, you may want to read the Wikipedia entry: http://en.wikipedia.org/wiki/Prefetcher

#### Microsoft Office {#ms-office}

Microsoft Office

```
\-- +Microsoft Excel
\-- .NET Programmability Support
\-- +Add-ins
\-- Euro Currency Tools
\-- Analysis ToolPak
\-- Solver
\-- Sample Files
\-- +Microsoft OneNote
\-- Handwriting Fonts
\-- .NET Programmability Support
\-- +Send to OneNote Add-ins
\-- Internet Explorer Integration
\-- Outlook Integration
\-- +Microsoft Outlook
\-- .NET Programmability Support
\-- +Importers and Exporters
\-- +Import from Other Formats
\-- Act 3.0
\-- Text (DOS)
\-- Text (Win)
\-- ODBC
\-- Lotus Organizer
\-- PAB
\-- Visual Basic Scripting Support
\-- +Outlook Messaging Components
\-- +Outlook Mapi Service Providers
\-- Outlook Address Book
\-- Microsoft Exchange Server
\-- Microsoft LDAP Directory
\-- Personal Folders
\-- +Outlook Add-Ins
\-- SharePoint Server Colleague Recommendations Add-In
\-- Outlook Social Connector
\-- +Outlook Stationery
\-- Outlook Stationery - Basic Files
\-- Outlook Stationery - Extended Files
\-- Outlook Templates
\-- +Microsoft PowerPoint
\-- Organization Chart Add-in for Microsoft Office programs
\-- .NET Programmability Support
\-- Animation Sound Effects
\-- +Microsoft Publisher
\-- .NET Programmability Support
\-- +Office Shared Features
\-- +Clip Organizer
\-- +Clip Organizer Collections
\-- +Popular Clip Art
\-- Clips
\-- +AutoShapes and Themes
\-- Clips
\-- +Converters and Filters
\-- +Graphics Filters
\-- Computer Graphics Metafile (CGM) File Import
\-- Encapsulated Postscript (EPS) File Import
\-- Graphics Interchange Format (GIF) File Import
\-- Joint Photographic Experts Group (JPEG) File Import
\-- Macintosh Graphics (PICT) File Import
\-- Portable Network Graphics (PNG) File Import
\-- WordPerfect Graphics (WPG) File Import
\-- +Text Converters
\-- Works 7.0-9.0 Converter for Windows
\-- Recover Text Converter
\-- WordPerfect 5.x Converter
\-- WordPerfect 6.x Converter
\-- Word 97-2003/Open XML Format Converter
\-- +International Support
\-- Universal Font
\-- Japanese Font
\-- Microsoft Office Themes
\-- Digital Certificate for VBA Projects
\-- +Proofing Tools
\-- Translation Core Files
\-- +English Proofing Tools
\-- Find All Word Forms
\-- Hyphenation
\-- Optical Character Recognition Modules
\-- Spelling and Grammar Checkers
\-- Thesaurus
\-- +French Proofing Tools
\-- Find All Word Forms
\-- Hyphenation
\-- Optical Character Recognition Modules
\-- Spelling and Grammar Checkers
\-- Thesaurus
\-- English - French Translation
\-- +Spanish Proofing Tools
\-- Find All Word Forms
\-- Hyphenation
\-- Optical Character Recognition Modules
\-- Spelling and Grammar Checkers
\-- Thesaurus
\-- English - Spanish Translation
\-- +Fonts
\-- Additional TrueType Fonts
\-- Microsoft Office Download Control
\-- +Web Themes
\-- Additional Web Themes
\-- Typical Web Themes
\-- Visual Basic for Applications
\-- +Office Tools
\-- Microsoft Forms 2.0 .NET Programmability Support
\-- +Microsoft Graph
\-- .NET Programmability Support
\-- Optical Character Recognition (OCR)
\-- +Actions Plugins
\-- Measurement Converter Actions Plugin
\-- Bibliographic Information Actions Plugin
\-- Date Actions Plugin
\-- Instant Messaging Contact Actions Plugin
\-- Name Actions Plugin
\-- Addresses and Places Actions Plugin
\-- Stocks && Funds Actions Plugin
\-- Microsoft Office Picture Manager
\-- +Microsoft SharePoint Foundation Support
\-- Microsoft Access Web Datasheet Component
\-- Microsoft SharePoint Foundation Support
\-- Microsoft Query
\-- Language Settings Tool
\-- Actions .NET Programmability Support
\-- Hosted Webs
\-- Equation Editor
\-- +Microsoft Word
\-- .NET Programmability Support
\-- Page Border Art
\-- Quick Formatting Files
```

### Windows (7) Event Log {#h.dgqjcakmo7w9" id="h.dgqjcakmo7w9

#### Custom Views {#h.8vpbm97preop" id="h.8vpbm97preop

**Server Roles**

Administrative Events

Microsoft Exchange with Database Availability Group Events

Custom Views can import as Xml files

#### Windows Logs {#h.k1mlra2iuj8w" id="h.k1mlra2iuj8w

``Application %SystemRoot%\System32\Winevt\Logs\Application.evtx``

``Security %SystemRoot%\System32\Winevt\Logs\Security.evtx``

``Setup %SystemRoot%\System32\Winevt\Logs\Setup.evtx``

``System %SystemRoot%\System32\Winevt\Logs\System.evtx``

``Forwarded Events %SystemRoot%\System32\Winevt\Logs\ForwardedEvents.evtx``

#### Applications and Services Logs {#h.dngf5u4tmugc" id="h.dngf5u4tmugc

```
ACEEventLog %SystemRoot%\System32\Winevt\Logs\ACEEventLog.evtx

Hardware Events %SystemRoot%\System32\Winevt\Logs\HardwareEvents.evtx

Internet Explorer %SystemRoot%\System32\Winevt\Logs\Internet Explorer.evtx

Key Management Service %SystemRoot%\System32\Winevt\Logs\Key Management Service.evtx

Media Center %SystemRoot%\System32\Winevt\Logs\Media Center.evtx
```

_Microsoft_

**Windows**

``API-Tracing/Operational \<Default>\Microsoft-Windows-API-Tracing%4Operational.evtx``

AppID/Operational

``Application Server-Applications/Admin \<Default>\Microsoft-Windows-Application Server-Applications%4Admin.evtx``

``Application Server-Applications/Operational \<Default>\Microsoft-Windows-Application Server-Applications%4Operational.evtx``

``Application-Experience/Problem-Steps-Recorder \<Default>\Microsoft-Windows-Application-Experience%4Problem-Steps-Recorder.evtx``

``Application-Experience/Program-Compatibility-Assistant \<Default>\Microsoft-Windows-Application-Experience%4Program-Compatibility-Assistant.evtx``

``Application-Experience/Program-Compatibility-Troubleshooter \<Default>\Microsoft-Windows-Application-Experience%4Program-Compatibility-Troubleshooter.evtx``

``Application-Experience/Program-Inventory \<Default>\Microsoft-Windows-Application-Experience%4Program-Inventory.evtx``

``Application-Experience/Program-Telemetry \<Default>\Microsoft-Windows-Application-Experience%4Program-Telemetry.evtx``

AppLocker/EXE and DLL

AppLocker/MSI and Script

Audio/Capture Monitor

Audio/Operational

Authentication User Interface/Operational

Backup/Operational

Biometrics/Operational

``Bits-Client/Analytic \<Default>\Microsoft-Windows-Bits-Client%4Analytic.evtx``

``Bits-Client/Operational \<Default>\Microsoft-Windows-Bits-Client%4Operational.evtx``

Bluetooth-MTPEnum/Operational

BranchCache/Operational

BranchCacheSMB/Operational

CAPI2/Operational

CertificateServiceClient-CredentialRoaming/Operational

CertPolEng/Operational

CodeIntegrity/Operational

CorruptedFileRecovery-Client/Operational

CorruptedFileRecovery-Server/Operational

DateTimeControlPanel/Operational

DeviceSync/Operational

Dhcp-Client

``Microsoft-Windows DHCP Client Events/Admin \<Default>\Microsoft-Windows-Dhcp-Client%4Admin.evtx``

``Microsoft-Windows DHCP Client Events/Operational \<Default>\Microsoft-Windows-Dhcp-Client%4Operational.evtx``

Dhcp-Nap-Enforcement-Client

``Microsoft-Windows-DHCPNap/Admin \<Default>\Microsoft-Windows-DhcpNap%4Admin.evtx``

``Microsoft-Windows-DHCPNap/Operational \<Default>\Microsoft-Windows-DhcpNap%4Operational.evtx``

DHCPv6-Client

``Microsoft-Windows-DHCP Client Events/Operational \<Default>\Microsoft-Windows-Dhcpv6-Client%4Operational.evtx``

``Microsoft-Windows-DHCPv6 Client Events/Admin \<Default>\Microsoft-Windows-Dhcpv6-Client%4Admin.evtx``

Diagnosis-DPS/Operational

Diagnosis-PCW/Operational

Diagnosis-PLA/Operational

Diagnosis-Schedule/Operational

``Diagnosis-Scripted/Admin \<Default>\Microsoft-Windows-Diagnosis-Scripted%4Admin.evtx``

``Diagnosis-Scripted/Operational \<Default>\Microsoft-Windows-Diagnosis-Scripted%4Operational.evtx``

Diagnosis-ScriptedDiagnosticsProvider/Operational

Diagnostics-Networking/Operational

Diagnostics-Performance/Operational

DiskDiagnostic/Operational

DiskDiagnosticDataCollector/Operational

DiskDiagnosticResolver/Operational

DisplayColorCalibration/Operational

DNS Client Events/Operational

DriverFrameworks-Usermode/Operational

EapHost/Operational

EventCollector/Operational

Eventlog-ForwardingPlugin/Operational

Fault-Tolerant-Heap/Operational

FMS/Operational

``Folder Redirection/Operational \<Default>\Microsoft-Windows-Folder Redirection%4Operational.evtx``

``GroupPolicy/Operational \<Default>\Microsoft-Windows-GroupPolicy%4Operational.evtx``

Help/Operational

HomeGroup Control Pan/Operational

HomeGroup Provider Service/Operational

HomeGroup-ListenerService

Microsoft-Windows-HomeGroup Listener Service/Operational

HttpService/HTTP Service Channel

International/Operational

International-RegionalOptionsControlPanel/Operational

Iphlpsvc/Operational

``Kernel-EventTracing/Admin \<Default>\Microsoft-Windows-Kernel-EventTracing%4Admin.evtx``

Kernel-Power/Thermal-Operational

Kernel-StoreMgr/Operational

Kernel-WDI/Operational

Kernel-WHEA/Operational

Errors

Operational

Known Folders/Operational

LanguagePackSetup/Operational

MCT/Operational

MemoryDiagnostics-Results/Debug

MSPaint/Admin

``MUI/Admin \<Default>\Microsoft-Windows-MUI%4Admin.evtx``

``MUI/Operational \<Default>\Microsoft-Windows-MUI%4Operational.evtx``

NCSI/Operational

NDIS/Operational

Network Access Protection/Operational

Network Access Protection/WHC

NetworkProfile/Operational

NlaSvc/Operational

NTLM/Operational

OfflineFiles/Operational

``ParentalControls/Operational \<Default>\Microsoft-Windows-ParentalControls%4Operational.evtx``

PeopleNearMe/Operational

PowerShell/Operational

PrimaryNetworkIcon

Microsoft-Windows-NetworkLocationWizard/Operational

``PrintService/Admin \<Default>\Microsoft-Windows-PrintService%4Admin.evtx``

``PrintService/Operational \<Default>\Microsoft-Windows-PrintService%4Operational.evtx``

ReadyBoost/Operational

ReadyBoostDriver/Operational

Recovery/Operational

Reliability-Analysis-Engine/Operational

``RemoteApp and Desktop Connections/Admin \<Default>\Microsoft-Windows-RemoteApp and Desktop Connections%4Admin.evtx``

``RemoteAssistance/Admin \<Default>\Microsoft-Windows-RemoteAssistance%4Admin.evtx``

``RemoteAssistance/Operational \<Default>\Microsoft-Windows-RemoteAssistance%4Operational.evtx``

``RemoteDesktopServices-RemoteDesktopSessionManager/Admin \<Default>\microsoft-windows-RemoteDesktopServices-RemoteDesktopSessionManager%4Admin.evtx``

Resource-Exhaustion-Detector/Operational

Resource-Exhaustion-Resolver/Operational

Resource-Leak-Diagnostic/Operational

RestartManager/Operational

Security-Audit-Configuration-Client/Operational

Security-IdentityListener/Operation log

Service Reporting API/Debug

StickyNotes/Admin

``TaskScheduler/Operational \<Default>\Microsoft-Windows-TaskScheduler%4Operational.evtx``

TerminalServices-ClientActiveXCore

Microsoft-Windows-TerminalServices-RDPClient/Operational

``TerminalServices-ClientUSBDevices/Admin \<Default>\Microsoft-Windows-TerminalServices-ClientUSBDevices%4Admin.evtx``

``TerminalServices-ClientUSBDevices/Operational \<Default>\Microsoft-Windows-TerminalServices-ClientUSBDevices%4Operational.evtx``

``TerminalServices-LocalSessionManager/Admin \<Default>\Microsoft-Windows-TerminalServices-LocalSessionManager%4Admin.evtx``

``TerminalServices-LocalSessionManager/Operational \<Default>\Microsoft-Windows-TerminalServices-LocalSessionManager%4Operational.evtx``

``TerminalServices-PnPDevices/Admin \<Default>\Microsoft-Windows-TerminalServices-PnPDevices%4Admin.evtx``

``TerminalServices-PnPDevices/Operational \<Default>\Microsoft-Windows-TerminalServices-PnPDevices%4Operational.evtx``

``TerminalServices-RemoteConnectionManager/Admin \<Default>\Microsoft-Windows-TerminalServices-RemoteConnectionManager%4Admin.evtx``

``TerminalServices-RemoteConnectionManager/Operational \<Default>\Microsoft-Windows-TerminalServices-RemoteConnectionManager%4Operational.evtx``

TZUtil/Operational

UAC/Operational

IAC-FileVirtualization/Operational

``User Profile Service/Operational \<Default>\Microsoft-Windows-User Profile Service%4Operational.evtx``

VDRVROOT/Operational

VHDMP/Operational

WebIO

NDF/Diagnostic

WER-Diagnostics/Operational

WFP

Microsoft-Windows-IKE/Operational

Operational

WindowsDefender

``Operational \<Default>\Microsoft-Windows-Windows Defender%4Operational.evtx``

``WHC \<Default>\Microsoft-Windows-Windows Defender%4WHC.evtx``

``Windows Firewall With Advanced Security/ConnectionSecurity \<Default>\Microsoft-Windows-Windows Firewall With Advanced Security%4ConnectionSecurity.evtx``

``Windows Firewall With Advanced Security/ConnectionSecurityVerbose \<Default>\Microsoft-Windows-Windows Firewall With Advanced Security%4ConnectionSecurityVerbose.evtx``

``Windows Firewall With Advanced Security/Firewall \<Default>\Microsoft-Windows-Windows Firewall With Advanced Security%4Firewall.evtx``

``Windows Firewall With Advanced Security/FirewallVerbose \<Default>\Microsoft-Windows-Windows Firewall With Advanced Security%4FirewallVerbose.evtx``

Windows Remote Management/Operational

``WindowsBackup/ActionCenter \<Default>\Microsoft-Windows-WindowsBackup%4ActionCenter.evtx``

WindowsColorSystem/Operational

WindowsSystemAssessmentTool/Operational

WindowsUpdateClient/Operational

WinHttp

``NDF/Diagnostic \<Default>\Microsoft-Windows-WinHTTP-NDF%4Diagnostic.evtx``

Winlogon/Operational

Winsock Catalog Change/Operational

Winsock Network Event/Operational

Wired-AutoConfig/Operational

WLAN-AutoConfig/Operational

``Wordpad/Admin \<Default>\Microsoft-Windows-Wordpad%4Admin.evtx``

WPD-ClassInstaller/Operational

WPD-CompositeClassDriver/Operational

WPD-MTPClassDriver/Operational

``Microsoft Exchange PSTCapture %SystemRoot%\System32\Winevt\Logs\Microsoft Exchange PSTCapture.evtx``

``Microsoft Office Alerts %SystemRoot%\System32\Winevt\Logs\OAlerts.evtx``

``Windows PowerShell %SystemRoot%\System32\Winevt\Logs\Windows PowerShell.evtx``

#### Audit Policy Categories and Subcategories {#h.vwasogroz128" id="h.vwasogroz128

``C:\Windows\System32>Auditpol /list /subcategory:\*``

**System**

Security State Change

Security System Extension

System Integrity

IPsec Driver

Other System Events

**Logon/Logoff**

Logon

Logoff

Account Lockout

IPsec Main Mode

IPsec Quick Mode

IPsec Extended Mode

Special Logon

Other Logon/Logoff Events

Network Policy Server

**Object Access**

File System

Registry

Kernel Object

SAM

Certification Services

Application Generated

Handle Manipulation

File Share

Filtering Platform Packet Drop

Filtering Platform Connection

Other Object Access Events

Detailed File Share

**Privilege Use**

Sensitive Privilege Use

Non Sensitive Privilege Use

Other Privilege Use Events

**Detailed Tracking**

Process Creation

Process Termination

DPAPI Activity

RPC Events

**Policy Change**

Audit Policy Change

Authentication Policy Change

Authorization Policy Change

MPSSVC Rule-Level Policy Change

Filtering Platform Policy Change

Other Policy Change Events

**Account Management**

User Account Management

Computer Account Management

Security Group Management

Distribution Group Management

Application Group Management

Other Account Management Events

**DS Access**

Directory Service Access

Directory Service Changes

Directory Service Replication

Detailed Directory Service Replication

**Account Logon**

Credential Validation

Kerberos Service Ticket Operations

Other Account Logon Events

Kerberos Authentication Service

### Windows File control and explorer (7) {#h.q6bwbcldm6im" id="h.q6bwbcldm6im

#### Favorites {#h.rtude3w470ph" id="h.rtude3w470ph

Desktop

Downloads

Recent Places

Recent Places, Desktop, Libraries, Computer, Network

#### Explorer Tree pane {#h.mya07fun9ecj" id="h.mya07fun9ecj

Favorites

Desktop

Downloads

Recent Places

Libraries

Documents

Music

Pictures

Videos

Computer

(C:)

Network

### Windows directory contents {#h.ftspvbyphj9k" id="h.ftspvbyphj9k

``\addins``

``\AppCompat``

``\AppPatch``

``\assembly``

``\Boot``

``\Branding``

``\CSC``

``\Cursors``

``\debug``

``\diagnostics``

``\DigitalLocker``

``\dot3svc``

``\Downloaded Program Files``

``\ehome``

``\en-US``

``\Fonts``

``\Globalization``

``\Help``

``\IME``

``\inf``

``\L2Schemas``

``\LiveKernelReports``

``\Logs``

``\Media``

``\Microsoft.NET``

``\ModemLogs``

``\Offline Web Pages``

``\Panther``

``\Performance\WinSAT\ (part of Windows Experience Index assessment score)?``

``\PLA``

``\PolicyDefinitions Group Policy templates? More found ...?``

``\PreFetch``

``\Registration``

``\rescache``

``\Resources``

``\SchCache``

``\schemas``

``\security``

``\ServiceProfiles``

``\servicing``

``\Setup``

``\ShellNew Templates for right-click New... More templates found in ...?``

``\SoftwareDistribution``

``\Speech``

``\system``

``\System32``

``\SysWOW64``

``\TAPI``

``\Tasks``

``\Temp``

``\tracing``

``\twain\_32``

``\Vss``

``\Web``

``\winsxs side-by-side component store enables activating features without providing installation media``

``\wlansvc``

#### C:\\Windows\\System32 {#System32}

0409

AdvancedInstallers

appmgmt

ar-SA

bg-BG

Boot

catroot

catroot2

CodeIntegrity

com

config

cs-CZ

da-DK

de-DE

Dism

drivers

DriverStore

el-GR

en

en-US

es-ES

et-EE

fi-FI

fr-FR

FxsTmp

GroupPolicy

GroupPolicyUsers

he-IL

hr-HR

hu-HU

ias

icsxml

IME

inetsrv

it-IT

ja-JP

ko-KR

LogFiles

lt-LT

lv-LV

manifeststore

Microsoft

migration

migwiz

Msdtc

MUI

nb-NO

NDF

NetworkList

nl-NL

OEM

oobe

pl-PL

``Printing\_Admin\_Scripts``

pt-BR

pt-PT

ras

Recovery

restore

ro-RO

ru-RU

Setup

sk-SK

slmgr

sl-SI

SMI

Speech

spool

spp

sppui

sr-Latin-CS

sv-SE

sysprep

Tasks

th-TH

tr-TR

uk-UA

wbem

WCN

wdi

wfp

WinBioDatabase

WinBioPlugIns

WindowsPowerShell

winevt

winrm Windows Remote Management Command Line Tool

zh-CN

zh-HK

zh-TW

appwiz.cpl

bthprops.cpl

collab.cpl

desk.cpl

Firewall.cpl

hdwwiz.cpl

inetcpl.cpl

infocardcpl.cpl

intl.cpl

irprops.cpl

joy.cpl

main.cpl

mmsys.cpl

ncpa.cpl

powercfg.cpl

sysdm.cpl

TabletPC.cpl

telephon.cpl

timedate.cpl

wscui.cpl

azman.msc

certmgr.msc

comexp.msc

compmgmt.msc

devmgmt.msc

diskmgmt.msc

eventvwr.msc

fsmgmt.msc

gpedit.msc

lusrmgr.msc

NAPCLCFG.MSC

perfmon.msc

printmanagement.msc

rsop.msc

secpol.msc

services.msc

taskschd.msc

tpm.msc

WF.msc

WmiMgmt.msc

chcp.com

diskcomp.com

diskcopy.com

format.com

mode.com

more.com

tree.com

Bubbles.scr

Mystify.scr

PhotoScreensaver.scr

Ribbons.scr

scrnsave.scr

ssText3d.scr

gatherNetworkInfo.vbs

slmgr.vbs

winrm.vbs

login.cmd Default global login script for the Telnet Server

onlinesetup.cmd

winrm.cmd

manage-bde.wsf NOTE: manage-bde.wsf has been replaced. Please use the replacement tool, manage-bde.exe, to perform BitLocker Drive Encryption management operations.

AdapterTroubleshooter.exe Troubleshoot Display Adapter

aitagent.exe

alg.exe

appidcertstorecheck.exe

appidpolicyconverter.exe

ARP.EXE

at.exe

AtBroker.exe

attrib.exe Attribute Utility

audiodg.exe Windows Audio Device Graph Isolation

auditpol.exe Audit Policy Program

``autochk.exe Auto Check Utility \*``

``autoconv.exe Auto File System Conversion Utility \*``

autofmt.exe Auto File System Format Utility

AxInstUI.exe

bcdboot.exe

bcdedit.exe

BdeUISrv.exe

BdeUnlockWizard.exe BitLocker Unlock Wizard

bitsadmin.exe

bootcfg.exe

bridgeunattend.exe

bthudtask.exe

cacls.exe

calc.exe

CertEnrollCtrl.exe

certreq.exe

certutil.exe

change.exe

charmap.exe Character Map

chglogon.exe

chgport.exe

chgusr.exe

chkdsk.exe Check Disk Utility

chkntfs.exe NTFS Volume Maintenance Utility

choice.exe Offers the user a choice

cipher.exe File Encryption Utility

cleanmgr.exe Disk Space Cleanup Manager for Windows

cliconfg.exe SQL Client Configuration Utility EXE

clip.exe Clip - copies the data into clipboard

cluster.exe Cluster Command Line Utility

cmd.exe Windows Command Processor

cmdkey.exe Credential Manager Command Line Utility

cmdl32.exe Microsoft Connection Manager Auto-Download

cmmon32.exe Microsoft Connection Manager Monitor

cmstp.exe Microsoft Connection Manager Profile Installer

``cofire.exe Corrupted File Recovery Client \*``

colorcpl.exe Microsoft Color Control Panel

comp.exe File Compare Utility

compact.exe File Compress Utility

CompMgmtLauncher.exe Computer Management Snapin Launcher

ComputerDefaults.exe Set Program Access and Computer Defaults Control Panel

``conhost.exe Console Window Host \*``

consent.exe Consent UI for administrative applications

control.exe Windows Control Panel

convert.exe File System Conversion Utility

credwiz.exe

cscript.exe

csrss.exe

ctfmon.exe CTF Loader

cttune.exe ClearType Tuner

cttunesvr.exe

dccw.exe Display Color Calibration

dcomcnfg.exe

ddodiag.exe

Defrag.exe

DeviceDisplayObjectProvider.exe

DeviceEject.exe

DevicePairingWizard.exe

DeviceProperties.exe

DFDWiz.exe

dfrgui.exe Microsoft Disk Defragmenter

dialer.exe

diantz.exe Microsoft Cabinet Maker

dinotify.exe Windows Device Installation

dirquota.exe

diskpart.exe

diskperf.exe Disk Performance Configuration Utility

diskraid.exe DiskRAID

Dism.exe

dispdiag.exe

DisplaySwitch.exe

djoin.exe

dllhost.exe

dllhst3g.exe

dnscacheugc.exe

doskey.exe

dpapimig.exe

DpiScaling.exe

dpnsvr.exe

driverquery.exe

drvinst.exe

dvdplay.exe

dvdupgrd.exe

dwm.exe

DWWIN.EXE

dxdiag.exe

Dxpserver.exe

Eap3Host.exe

efsui.exe

EhStorAuthn.exe

esentutl.exe

eudcedit.exe

eventcreate.exe Enables an administrator to create a custom event in a specified event log.

eventvwr.exe

expand.exe LZ Expansion Utility

``extrac32.exe Microsoft CAB File Extract Utility \*``

fc.exe

find.exe

findstr.exe

finger.exe

fixmapi.exe

fltMC.exe

fontview.exe

forfiles.exe

fsutil.exe

ftp.exe

fvenotify.exe

fveprompt.exe

FXSCOVER.exe

FXSSVC.exe

FXSUNATD.exe

getmac.exe

GettingStarted.exe

gpresult.exe

gpscript.exe

gpupdate.exe

grpconv.exe

hdwwiz.exe

help.exe

HOSTNAME.EXE

hwrcomp.exe

hwrreg.exe

icacls.exe

icardagt.exe

icsunattend.exe

ie4uinit.exe

ieUnatt.exe

iexpress.exe

InfDefaultInstall.exe

ipconfig.exe

irftp.exe

iscsicli.exe

iscsicpl.exe

isoburn.exe

klist.exe

ksetup.exe

ktmutil.exe

label.exe

LocationNotifications.exe

Locator.exe

lodctr.exe

logagent.exe

logman.exe

logoff.exe

LogonUI.exe

lpksetup.exe

lpremove.exe

lsass.exe

lsm.exe

Magnify.exe

makecab.exe

manage-bde.exe

mblctr.exe

mcbuilder.exe

mctadmin.exe

MdRes.exe

MdSched.exe

mfpmp.exe

MigAutoPlay.exe

mmc.exe

mobsync.exe

mountvol.exe

mpnotify.exe

MpSigStub.exe

MRINFO.EXE

MRT.exe

msconfig.exe

msdt.exe

msdtc.exe

msfeedssync.exe

msg.exe

mshta.exe

msiexec.exe

msinfo32.exe

mspaint.exe

msra.exe

mstsc.exe Use your computer to connect to a computer that is located elsewhere and run programs or access files.

mtstocom.exe

MuiUnattend.exe

MultiDigiMon.exe

NAPSTAT.EXE

Narrator.exe

nbtstat.exe

ndadmin.exe

net.exe

net1.exe

netbtugc.exe

netcfg.exe

netiougc.exe

Netplwiz.exe

NetProj.exe

netsh.exe

NETSTAT.EXE

newdev.exe

nltest.exe

notepad.exe

nslookup.exe

ntoskrnl.exe

ntprint.exe

ocsetup.exe

odbcad32.exe

odbcconf.exe

openfiles.exe

OptionalFeatures.exe

osk.exe

OxpsConverter.exe

p2phost.exe

PATHPING.EXE

pcalua.exe

pcaui.exe

pcawrk.exe

pcwrun.exe

perfmon.exe

PING.EXE

PkgMgr.exe

plasrv.exe

PnPUnattend.exe

PnPutil.exe

poqexec.exe

powercfg.exe

PresentationHost.exe

PresentationSettings.exe

prevhost.exe

print.exe

PrintBrmUi.exe

printfilterpipelinesvc.exe

PrintIsolationHost.exe

printui.exe

proquota.exe

psr.exe

PushPrinterConnections.exe

qappsrv.exe

qprocess.exe

query.exe

quser.exe

qwinsta.exe

rasautou.exe

rasdial.exe

raserver.exe

rasphone.exe

rdpclip.exe

rdrleakdiag.exe

rdrmemptylst.exe

ReAgentc.exe

recdisc.exe

recover.exe

reg.exe

regedt32.exe

regini.exe

RegisterIEPKEYs.exe

regsvr32.exe

rekeywiz.exe

relog.exe

RelPost.exe

repair-bde.exe

replace.exe

reset.exe

resmon.exe

RMActivate.exe

``RMActivate\_isv.exe``

``RMActivate\_ssp.exe``

``RMActivate\_ssp\_isv.exe``

RmClient.exe

Robocopy.exe

ROUTE.EXE

RpcPing.exe

rrinstaller.exe

rstrui.exe

runas.exe

rundll32.exe

RunLegacyCPLElevated.exe

runonce.exe

rwinsta.exe

sbunattend.exe

sc.exe

schtasks.exe

sdbinst.exe

sdchange.exe

sdclt.exe

sdiagnhost.exe

SearchFilterHost.exe

SearchIndexer.exe

SearchProtocolHost.exe

SecEdit.exe

secinit.exe

services.exe

sethc.exe Accessibility - Sticky Keys

SetIEInstalledDate.exe

setspn.exe

setupcl.exe

setupugc.exe

setx.exe

sfc.exe

shadow.exe

shrpubw.exe

shutdown.exe

sigverif.exe

slui.exe Windows Activation Client

smss.exe

SndVol.exe

SnippingTool.exe

snmptrap.exe

sort.exe

SoundRecorder.exe

spinstall.exe

spoolsv.exe

sppsvc.exe Software Protection service

spreview.exe

srdelayed.exe

StikyNot.exe

subst.exe

svchost.exe

sxstrace.exe

SyncHost.exe

syskey.exe

systeminfo.exe

SystemPropertiesAdvanced.exe

SystemPropertiesComputerName.exe

SystemPropertiesDataExecutionPrevention.exe

SystemPropertiesHardware.exe

SystemPropertiesPerformance.exe

SystemPropertiesProtection.exe

SystemPropertiesRemote.exe

systray.exe

tabcal.exe

takeown.exe

TapiUnattend.exe

taskeng.exe

taskhost.exe

taskkill.exe

tasklist.exe

taskmgr.exe

tcmsetup.exe

TCPSVCS.EXE

telnet.exe

TFTP.EXE

timeout.exe

tlntadmn.exe

tlntsess.exe

tlntsvr.exe

TpmInit.exe

tracerpt.exe

TRACERT.EXE

tscon.exe

tsdiscon.exe

tskill.exe

TSTheme.exe

TsUsbRedirectionGroupPolicyControl.exe

TSWbPrxy.exe

TsWpfWrp.exe

typeperf.exe

tzutil.exe

ucsvc.exe

UI0Detect.exe

unlodctr.exe

unregmp2.exe

upnpcont.exe

UserAccountControlSettings.exe

userinit.exe

Utilman.exe

VaultCmd.exe

VaultSysUi.exe

vds.exe

vdsldr.exe

verclsid.exe

verifier.exe

vmicsvc.exe

vssadmin.exe Volume Shadow Copy Service administrative command-line tool

VSSVC.exe

w32tm.exe

waitfor.exe

wbadmin.exe

wbengine.exe

wecutil.exe

WerFault.exe

WerFaultSecure.exe

wermgr.exe

wevtutil.exe

wextract.exe

WFS.exe

where.exe

whoami.exe

wiaacmgr.exe

wiawow64.exe

wimserv.exe

WindowsAnytimeUpgrade.exe

WindowsAnytimeUpgradeResults.exe

WindowsAnytimeUpgradeui.exe

wininit.exe

winload.exe

winlogon.exe

winresume.exe

winrs.exe

winrshost.exe

WinSAT.exe

winver.exe

wisptis.exe

wksprt.exe

wlanext.exe

wlrmdr.exe

wowreg32.exe

WPDShextAutoplay.exe

wpnpinst.exe

write.exe

wscript.exe

WSManHTTPConfig.exe

wsmprovhost.exe

wsqmcons.exe

wuapp.exe

wuauclt.exe

WUDFHost.exe

wusa.exe

xcopy.exe

xpsrchvw.exe

xwizard.exe

``#### C:\Windows\SysWOW64\ <a href="#h.68y30a4v3j7" id="h.68y30a4v3j7"></a>``

``C:\Windows>cd SysWOW64``

``C:\Windows\SysWOW64>dir \*.cpl /b``

appwiz.cpl

bthprops.cpl

desk.cpl

Firewall.cpl

FlashPlayerCPLApp.cpl

hdwwiz.cpl

inetcpl.cpl

infocardcpl.cpl

intl.cpl

irprops.cpl

joy.cpl

main.cpl

mmsys.cpl

ncpa.cpl

powercfg.cpl

sysdm.cpl

telephon.cpl

timedate.cpl

wscui.cpl

``C:\Windows\SysWOW64>dir \*.msc /b``

adsiedit.msc

azman.msc

certmgr.msc

comexp.msc

compmgmt.msc

devmgmt.msc

dfsmgmt.msc

diskmgmt.msc

domain.msc

dsa.msc

dssite.msc

eventvwr.msc

fsmgmt.msc

gpedit.msc

gpmc.msc

gpme.msc

gptedit.msc

lusrmgr.msc

NAPCLCFG.MSC

perfmon.msc

printmanagement.msc

rsop.msc

SanMmc.msc

services.msc

taskschd.msc

tpm.msc

WF.msc

``C:\Windows\SysWOW64>dir \*.com /b``

chcp.com

diskcomp.com

diskcopy.com

format.com

mode.com

more.com

tree.com

``C:\Windows\SysWOW64>dir \*.cmd /b``

winrm.cmd

``C:\Windows\SysWOW64>dir \*.bat /b``

File Not Found

``C:\Windows\SysWOW64>dir \*.wsh /b``

File Not Found

``C:\Windows\SysWOW64>dir \*.vbs /b``

slmgr.vbs

winrm.vbs

``C:\Windows\SysWOW64>dir \*.exe /b``

AdapterTroubleshooter.exe

ARP.EXE

at.exe

AtBroker.exe

attrib.exe

auditpol.exe

autochk.exe

autoconv.exe

autofmt.exe

bitsadmin.exe

bootcfg.exe

bthudtask.exe

cacls.exe

calc.exe

CertEnrollCtrl.exe

certreq.exe

certutil.exe

charmap.exe

chkdsk.exe

chkntfs.exe

choice.exe

cipher.exe

cleanmgr.exe

cliconfg.exe

clip.exe

cmd.exe

cmdkey.exe

cmdl32.exe

cmmon32.exe

cmstp.exe

colorcpl.exe

comp.exe

compact.exe

ComputerDefaults.exe

control.exe

convert.exe

credwiz.exe

cscript.exe

csvde.exe

ctfmon.exe

cttune.exe

cttunesvr.exe

dccw.exe

dcdiag.exe

dcomcnfg.exe

dcpromo.exe

ddodiag.exe

DevicePairingWizard.exe

DeviceProperties.exe

dfrgui.exe

dfsfrsHost.exe

dialer.exe

diantz.exe

diskpart.exe

diskperf.exe

diskraid.exe

Dism.exe

DisplaySwitch.exe

dllhost.exe

dllhst3g.exe

dns-sd.exe

dnscacheugc.exe

doskey.exe

dpapimig.exe

DpiScaling.exe

dplaysvr.exe

dpnsvr.exe

driverquery.exe

drvinst.exe

dsac.exe (was missing from list, 2008R2 or Win7 w/ RSAT) Manages users, computers, security groups and other Active Directory objects through data-driven and task-oriented navigation.

dsacls.exe

dsadd.exe

dsdbutil.exe

dsget.exe

dsmgmt.exe

dsmod.exe

dsmove.exe

dsquery.exe

dsrm.exe

dvdplay.exe

dvdupgrd.exe

DWWIN.EXE

dxdiag.exe

efsui.exe

EhStorAuthn.exe

esentutl.exe

eudcedit.exe

eventcreate.exe

eventvwr.exe

evntcmd.exe

evntwin.exe

expand.exe

explorer.exe

extrac32.exe

fc.exe

find.exe

findstr.exe

finger.exe

fixmapi.exe

FlashPlayerApp.exe

FlexLMCOMServer.exe

fltMC.exe

fontview.exe

forfiles.exe

fsutil.exe

ftp.exe

GetCDriveSerialNumber.exe

getmac.exe

gpfixup.exe

gpresult.exe

gpscript.exe

gpupdate.exe

grpconv.exe

hdwwiz.exe

help.exe

hh.exe

HOSTNAME.EXE

icacls.exe

icardagt.exe

icsunattend.exe

ie4uinit.exe

ieUnatt.exe

iexpress.exe

iisreset.exe

InfDefaultInstall.exe

instnm.exe

ipconfig.exe

iscsicli.exe

iscsicpl.exe

isoburn.exe

java.exe

javaw.exe

javaws.exe

ktmutil.exe

label.exe

ldifde.exe

ldp.exe

LocationNotifications.exe

lodctr.exe

logagent.exe

logman.exe

Magnify.exe

makecab.exe

mcbuilder.exe

MergeRawLicense.exe

mfpmp.exe

MigAutoPlay.exe

mmc.exe

mobsync.exe

mountvol.exe

MRINFO.EXE

msdt.exe

msfeedssync.exe

mshta.exe

msiexec.exe

msinfo32.exe

mspaint.exe

msra.exe

mstsc.exe

mtstocom.exe

MuiUnattend.exe

NAPSTAT.EXE

ndadmin.exe

net.exe

net1.exe

netbtugc.exe

netdom.exe

netiougc.exe

Netplwiz.exe

netsh.exe

NETSTAT.EXE

newdev.exe

notepad.exe

nslookup.exe

ntdsutil.exe

ntkrnlpa.exe

ntoskrnl.exe

ntprint.exe

ocsetup.exe

odbcad32.exe

odbcconf.exe

openfiles.exe

OptionalFeatures.exe

osk.exe

PATHPING.EXE

pcaui.exe

perfhost.exe

perfmon.exe

PING.EXE

PkgMgr.exe

poqexec.exe

powercfg.exe

PresentationHost.exe

prevhost.exe

print.exe

printui.exe

proquota.exe

psr.exe

PushPrinterConnections.exe

rasautou.exe

rasdial.exe

raserver.exe

rasphone.exe

rdrleakdiag.exe

ReAgentc.exe

recover.exe

redircmp.exe

redirusr.exe

reg.exe

regedit.exe

regedt32.exe

regini.exe

RegisterIEPKEYs.exe

regsvr32.exe

rekeywiz.exe

relog.exe

rendom.exe

repadmin.exe

replace.exe

resmon.exe

RMActivate.exe

``RMActivate\_isv.exe``

``RMActivate\_ssp.exe``

``RMActivate\_ssp\_isv.exe``

RmClient.exe

Robocopy.exe

ROUTE.EXE

RpcPing.exe

rrinstaller.exe

runas.exe

rundll32.exe

RunLegacyCPLElevated.exe

runonce.exe

sbunattend.exe

sc.exe

schtasks.exe

sdbinst.exe

sdchange.exe

sdiagnhost.exe

SearchFilterHost.exe

SearchIndexer.exe

SearchProtocolHost.exe

SecEdit.exe

secinit.exe

sethc.exe

SetIEInstalledDate.exe

setup16.exe

setupSNK.exe

setupugc.exe

setx.exe

sfc.exe

shrpubw.exe

shutdown.exe

SndVol.exe

snmp.exe

sort.exe

srdelayed.exe

subst.exe

svchost.exe

sxstrace.exe

SyncHost.exe

syskey.exe

systeminfo.exe

SystemPropertiesAdvanced.exe

SystemPropertiesComputerName.exe

SystemPropertiesDataExecutionPrevention.exe

SystemPropertiesHardware.exe

SystemPropertiesPerformance.exe

SystemPropertiesProtection.exe

SystemPropertiesRemote.exe

systray.exe

takeown.exe

TapiUnattend.exe

taskeng.exe

taskkill.exe

tasklist.exe

taskmgr.exe

tcmsetup.exe

TCPSVCS.EXE

timeout.exe

TpmInit.exe

tracerpt.exe

TRACERT.EXE

TSTheme.exe

TsWpfWrp.exe

typeperf.exe

tzutil.exe

unlodctr.exe

unregmp2.exe

upnpcont.exe

user.exe

UserAccountControlSettings.exe

userinit.exe

Utilman.exe

verclsid.exe

verifier.exe

vssadmin.exe

w32tm.exe

waitfor.exe

wecutil.exe

WerFault.exe

WerFaultSecure.exe

wermgr.exe

wevtutil.exe

wextract.exe

where.exe

whoami.exe

wiaacmgr.exe

wimserv.exe

wininit.exe

winrs.exe

winrshost.exe

winver.exe

wlanext.exe

wowreg32.exe

WPDShextAutoplay.exe

write.exe

wscript.exe

WSManHTTPConfig.exe

wsmprovhost.exe

wuapp.exe

wusa.exe

xcopy.exe

xpsrchvw.exe

xwizard.exe

``C:\Windows\SysWOW64>``

**Sysinternals GUI Tools**

AccessEnum.exe

ADExplorer.exe

ADInsight.exe

autoruns.exe

Bginfo.exe great for terminal server (RDP) for admins, easy access to info by users for helpdesk, and can inventory as well!

Cacheset.exe

Dbgview.exe

Desktops.exe

disk2vhd.exe

Diskmon.exe (depreciated?)

DiskView.exe

LoadOrd.exe

pagedfrg.exe

portmon.exe

procexp.exe

PROCEXP64.exe (not runnable, use procexp.exe instead)

Procmon.exe

RAMMap.exe

RootkitRevealer.exe (depreciated?)

ShareEnum.exe

ShellRunas.exe (must run from CLI or install from CLI)

Tcpvcon.exe (not GUI)

Tcpview.exe

vmmap.exe

Winobj.exe

ZoomIt.exe

**Sysinternals PS Tools**

PsExec.exe

psfile.exe

PsGetsid.exe

PsInfo.exe

pskill.exe

pslist.exe

PsLoggedon.exe

psloglist.exe

pspasswd.exe

PsService.exe

psshutdown.exe

pssuspend.exe

**Other Sysinternals Tools**

### List of Microsoft Commands {#h.kobq43mphrp8" id="h.kobq43mphrp8

Adprep

Append

Arp

Assoc

At

Atmadm

Attrib

Auditpol

Auditpol get

Auditpol set

Auditpol list

Auditpol backup

Audtipol restore

Auditpol clear

Auditpol remove

Auditpol resourceSACL

Autochk

Autoconv

Autofmt

Bcdboot

Bcdedit

Bdehdcfg

Bdehdcfg: driveinfo

Bdehdcfg: target

Bdehdcfg: newdriveletter

Bdehdcfg: size

Bdehdcfg: quiet

Bdehdcfg: restart

Bitsadmin

Bitsadmin /addfile

Bitsadmin /addfileset

Bitsadmin /addfilewithranges

Bitsadmin /cache

Bitsadmin /cache /clear

Bitsadmin /cache /delete

Bitsadmin /cache /deleteurl

Bitsadmin /cache /list

Bitsadmin /cache /info

Bitsadmin /cache /getlimit

Bitsadmin /cache /setlimit

Bitsadmin /cache /getexpirationtime

Bitsadmin /cache /setexpirationtime

Bitsadmin /cache /help

Bitsadmin /cancel

Bitsadmin /complete

Bitsadmin /create

Bitsadmin /getaclflags

Bitsadmin /getbytestotal

Bitsadmin /getbytestransferred

Bitsadmin /getclientcertificate

Bitsadmin /getcompletiontime

Bitsadmin /getcustomheaders

Bitsadmin /getcreationtime

Bitsadmin /getdescription

Bitsadmin /getdisplayname

Bitsadmin /geterror

Bitsadmin /geterrorcount

Bitsadmin /getfilestotal

Bitsadmin /getfilestransferred

Bitsadmin /getmaxdownloadtime

Bitsadmin /getminretrydelay

Bitsadmin /getmodificationtime

Bitsadmin /getnoprogresstimeout

Bitsadmin /getnotifycmdline

Bitsadmin /getnotifyflags

Bitsadmin /getnotifyinterface

Bitsadmin /getowner

Bitsadmin /getpeercachingflags

Bitsadmin /getpriority

Bitsadmin /getproxybypasslist

Bitsadmin /getproxylist

Bitsadmin /getproxyusage

Bitsadmin /getreplydata

Bitsadmin /getreplyfilename

Bitsadmin /getreplyprogress

Bitsadmin /getsecurityflags

Bitsadmin /getstate

Bitsadmin /gettemporaryname

Bitsadmin /gettype

Bitsadmin /getvalidationstate

Bitsadmin /help

Bitsadmin /info

Bitsadmin /list

Bitsadmin /listfiles

Bitsadmin /monitor

Bitsadmin /nowrap

Bitsadmin /peers

Bitsadmin /peers /list

Bitsadmin /peers /clear

Bitsadmin /peers /discover

Bitsadmin /peers /help

Bitsadmin /peercaching

Bitsadmin /peercaching /getconfigurationflags

Bitsadmin /peercaching /setconfigurationflags

Bitsadmin /peercaching /help

Bitsadmin /rawreturn

Bitsadmin /removeclientcertificate

Bitsadmin /removecredentials

Bitsadmin /replaceremoteprefix

Bitsadmin /reset

Bitsadmin /resume

Bitsadmin /setaclflag

Bitsadmin /setclientcertificatebyid

Bitsadmin /setclientcertificatebyname

Bitsadmin /setcredentials

Bitsadmin /setcustomheaders

Bitsadmin /setdescription

Bitsadmin /setdisplayname

Bitsadmin /setmaxdownloadtime

Bitsadmin /setminretrydelay

Bitsadmin /setnoprogresstimeout

Bitsadmin /setnotifycmdline

Bitsadmin /setnotifyflags

Bitsadmin /setpeercachingflags

Bitsadmin /setpriority

Bitsadmin /setproxysettings

Bitsadmin /setreplyfilename

Bitsadmin /setsecurityflags

Bitsadmin /setvalidationstate

Bitsadmin /suspend

Bitsadmin /takeownership

Bitsadmin /transfer

Bitsadmin /util

Bitsadmin /util /help

Bitsadmin /util /getieproxy

Bitsadmin /util /repairservice

Bitsadmin /util /setieproxy

Bitsadmin /util /version

Bitsadmin /util /enableanalyticchannel

Bitsadmin /wrap

Bootcfg

Bootcfg /addsw

Bootcfg /copy

Bootcfg /dbg1394

Bootcfg /debug

Bootcfg /default

Bootcfg /delete

Bootcfg /ems

Bootcfg /query

Bootcfg /raw

Bootcfg /rmsw

Bootcfg /timeout

Break

Cacls

Call

Cd

Certreq

Certutil certutil -v -?

Change

Change logon

Change port

Change user

Chcp

Chdir

Chglogon

Chgport

Chgusr

Chkdsk

Chkntfs

Choice

Cipher

Clip

Cls

Cluadmin

Cluster

Cmd

Cmdkey

Cmstp

Color

Comp

Compact

Convert

Copy

Cprofile

Cscript

Csvde

Date

Dcdiag

Dcgpofix

Dcpromo

Defrag

Del

Dfscmd

Dfsrmig

Diantz

Dir

Dirquota

Dirquota quota

Dirquota quota list

Dirquota quota add

Dirquota quota modify

Dirquota quota delete

Dirquota quota scan

Dirquota quota freespace

Dirquota autoquota

Dirquota autoquota list

Dirquota autoquota add

Dirquota autoquota modify

Dirquota autoquota delete

Dirquota template

Dirquota template list

Dirquota template add

Dirquota template modify

Dirquota template delete

Dirquota template import

Dirquota template export

Dirquota admin

Dirquota admin options

Dirquota admin defaults

Dirquota notification

Configuration files for notifications in File Server Resource Manager

Diskcomp

Diskcopy

Diskedit

DiskPart

Active

Add

Assign

Attach vdisk

Attributes

Attributes disk

Attributes volume

Automount

Break

Clean

Compact vdisk

Convert

Convert basic

Convert dynamic

Convert gpt

Convert mbr

Create

Create partition

Create partition efi

Create partition extended

Create partition logical

Create partition msr

Create partition primary

Create volume

Create volume raid

Create volume simple

Create volume stripe

Create volume mirror

Create vdisk

Delete

Delete disk

Delete partition

Delete volume

Detach vdisk

Detail

Detail disk

Detail partition

Detail volume

Detail vdisk

Exit

Expand vdisk

Extend

Filesystems

Format

GPT

Help

Import

Inactive

List

Merge vdisk

Offline

Offline disk

Offline volume

Online

Online disk

Online volume

Recover

Rem

Remove

Repair

Rescan

Retain

San

Select

Select disk

Select partition

Select volume

Select vdisk

Setid

Shrink

Uniqueid

Diskperf

DiskRAID

Diskshadow

Add

Begin backup

Begin restore

Break

Create

Delete shadows

End backup

End restore

Exec

Exit

Expose

Import

List

List writers

List shadows

List providers

Load metadata

Mask

Reset

Revert

Set

Set context

Set option

Set verbose

Set metadata

Simulate restore

Unexpose

Writer

Dispdiag

Djoin

Dnscmd

Doskey

Driverquery

Dsacls

Dsadd

Dsadd computer

Dsadd contact

Dsadd group

Dsadd ou

Dsadd user

Dsadd quota

Dsamain

Dsdbutil

authoritative restore

files

ifm

semantic database analysis

snapshot

Dsget

Dsget computer

Dsget contact

Dsget group

Dsget ou

Dsget server

Dsget user

Dsget subnet

Dsget site

Dsget quota

Dsget partition

Dsmgmt

configurable settings

DS behavior

group membership evaluation

LDAP policies

local roles

metadata cleanup

partition management

roles

security account management

set DSRM password

Dsmod

Dsmod computer

Dsmod contact

Dsmod group

Dsmod ou

Dsmod server

Dsmod user

Dsmod quota

Dsmod partition

Dsmove

Dsquery

Dsquery computer

Dsquery contact

Dsquery group

Dsquery ou

Dsquery site

Dsquery server

Dsquery user

Dsquery quota

Dsquery partition

``Dsquery \*``

Dsrm

Echo

Edit

Endlocal

Erase

Esentutl

Esentutl /defragmentation

Esentutl /recovery

Esentutl /integrity

Esentutl /checksum

Esentutl /repair

Esentutl /file dump

Esentutl /copy file

Eventcreate

Eventquery.vbs

Eventtriggers

Evntcmd

Exit

Expand

Extract

Fc

Filescrn

Filescrn filegroup

Filescrn filegroup list

Filescrn filegroup add

Filescrn filegroup modify

Filescrn filegroup delete

Filescrn filegroup import

Filescrn filegroup export

Filescrn screen

Filescrn screen list

Filescrn screen add

Filescrn screen modify

Filescrn screen delete

Filescrn exception

Filescrn exception list

Filescrn exception add

Filescrn exception modify

Filescrn exception delete

Filescrn template

Filescrn template list

Filescrn template add

Filescrn template modify

Filescrn template delete

Filescrn template import

Filescrn template export

Filescrn admin

Filescrn admin options

Filescrn admin defaults

Filescrn notification

Configuration files for notifications in File Server Resource Manager

Find

Findstr

Finger

Flattemp

Fondue

For

Forfiles

Format

Freedisk

Fsutil

Fsutil 8dot3name

Fsutil behavior

Fsutil dirty

Fsutil file

Fsutil fsinfo

Fsutil hardlink

Fsutil objectid

Fsutil quota

Fsutil repair

Fsutil reparsepoint

Fsutil resource

Fsutil sparse

Fsutil transaction

Fsutil usn

Fsutil volume

Ftp

Ftp: ?

Ftp: !

Ftp: append

Ftp: ascii

Ftp: bell

Ftp: bye

Ftp: binary

Ftp: cd

Ftp: close

Ftp: debug

Ftp: delete

Ftp: dir

Ftp: disconnect

Ftp: get

Ftp: glob

Ftp: hash

Ftp: lcd

Ftp: literal

Ftp: ls

Ftp: mdelete

Ftp: mdir

Ftp: mget

Ftp: mkdir

Ftp: mls

Ftp: mput

Ftp: open

Ftp: prompt

Ftp: put

Ftp: pwd

Ftp: quit

Ftp: quote

Ftp: recv

Ftp: remotehelp

Ftp: rename

Ftp: rmdir

Ftp: send

Ftp: status

Ftp: trace

Ftp: type

Ftp: user

Ftp: verbose

Ftype

Fveupdate

Getmac

Gettype

Goto

Gpfixup

Gpresult

Gpupdate

Graftabl

Hashgen

Help

Helpctr

Hostname

Icacls

If

Inuse

Ipconfig

Ipxroute

Irftp

Ismserv

Jetpack

Klist

Ksetup

Ksetup:setrealm

Ksetup:mapuser

Ksetup:addkdc

Ksetup:delkdc

Ksetup:addkpasswd

Ksetup:delkpasswd

Ksetup:server

Ksetup:setcomputerpassword

Ksetup:removerealm

Ksetup:domain

Ksetup:changepassword

Ksetup:listrealmflags

Ksetup:setrealmflags

Ksetup:addrealmflags

Ksetup:delrealmflags

Ksetup:dumpstate

Ksetup:addhosttorealmmap

Ksetup:delhosttorealmmap

Ksetup:setenctypeattr

Ksetup:getenctypeattr

Ksetup:addenctypeattr

Ksetup:delenctypeattr

Ktmutil

Ktpass

Label

Ldifde

Ldp

Lodctr

Logman

logman create

logman create counter

logman create trace

logman create alert

logman create cfg

logman create api

logman query

logman start | stop

logman delete

logman update

logman update counter

logman update trace

logman update alert

logman update cfg

logman update api

logman import | export

Logoff

Lpq

Lpr

Macfile

Makecab

Manage-bde

Manage-bde: status

Manage-bde: on

Manage-bde: off

Manage-bde: pause

Manage-bde: resume

Manage-bde: lock

Manage-bde: unlock

Manage-bde: autounlock

Manage-bde: protectors

Manage-bde: tpm

Manage-bde: setidentifier

Manage-bde: ForceRecovery

Manage-bde: changepassword

Manage-bde: changepin

Manage-bde: changekey

Manage-bde: upgrade

Manage-bde: KeyPackage

Manage-bde: WipeFreeSpace

Mapadmin

Md

Mkdir

Mklink

Mmc

Mode

More

Mount

Mountvol

Move

Mqbkup

Mqsvc

Mqtgsvc

Msdt

Msg

Msiexec

Msinfo32

Mstsc

Nbtstat

Net computer

Net group

Net localgroup

Net print

Net session

Net share

Net use

Net user

Net view

Netcfg

Netdiag

Netdom

Netdom add

Netdom computername

Netdom join

Netdom move

Netdom query

Netdom remove

Netdom movent4bdc

Netdom renamecomputer

Netdom reset

Netdom resetpwd

Netdom trust

Netdom verify

Netsh

Netstat

Nfsadmin

Nfsshare

Nfsstat

Nlb

Nlbmgr

Nltest

Nslookup

Nslookup /exit

Nslookup /finger

Nslookup /help

Nslookup /ls

Nslookup /lserver

Nslookup /root

Nslookup /server

Nslookup /set

Nslookup /set all

Nslookup /set class

Nslookup /set d2

Nslookup /set debug

Nslookup /set defname

Nslookup /set domain

Nslookup /set ignore

Nslookup /set port

Nslookup /set querytype

Nslookup /set recurse

Nslookup /set retry

Nslookup /set root

Nslookup /set search

Nslookup /set srchlist

Nslookup /set timeout

Nslookup /set type

Nslookup /set vc

Nslookup /view

Ntbackup

Ntcmdprompt

Ntdsutil

authoritative restore

configurable settings

DS behavior

files

group membership evaluation

ifm

LDAP policies

local roles

metadata cleanup

partition management

roles

security account management

semantic database analysis

set DSRM password

snapshot

Ntfrsutl

Openfiles

Pagefileconfig.vbs

Path

Pathping

Pause

Pbadmin

Pentnt

Perfmon

Ping

Pnpunattend

Pnputil

Popd

Powercfg

PowerShell

``PowerShell\_Ise``

Print

Prncnfg.vbs

Prndrvr.vbs

Prnjobs.vbs

Prnmngr.vbs

Prnport.vbs

Prnqctl.vbs

Prompt

Pubprn.vbs

Pushd

Pushprinterconnections

Qappsrv

Pwlauncher

Qprocess

Query

Query process

Query session

Query termserver

Query user

Quser

Qwinsta

Rasdial

Rcp

Rd

Rdpsign

Reagentc

Recover

Redircmp

Redirusr

Reg

Reg add

Reg compare

Reg copy

Reg delete

Reg export

Reg flags

Reg import

Reg load

Reg query

Reg restore

Reg save

Reg unload

Regini

Regsvr32

Relog

Rem

Ren

Rename

Rendom

Repadmin

Repadmin /kcc

Repadmin /prp

Repadmin /queue

Repadmin /replicate

Repadmin /replsingleobj

Repadmin /replsummary

Repadmin /rodcpwdrepl

Repadmin /showattr

Repadmin /showobjmeta

Repadmin /showrepl

Repadmin /showutdvec

Repadmin /syncall

Repair-bde

Replace

Reset session

Rexec

Risetup

Rmdir

Robocopy

Route

Rpcinfo

Rpcping

Rsh

Rsm

Rss

Runas

Rundll32

Rundll32 printui.dll,PrintUIEntry

Rwinsta

Sc

Sc boot

Sc config

Sc continue

Sc control

Sc create

Sc delete

Sc description

Sc enumdepend

Sc failure

Sc failureflag

Sc getdisplayname

Sc getkeyname

Sc interrogate

Sc lock

Sc pause

Sc qc

Sc qdescription

Sc qfailure

Sc query

Sc queryex

Sc querylock

Sc sdset

Sc sdshow

Sc start

Sc stop

Schtasks

Scwcmd

Scwcmd: analyze

Scwcmd: configure

Scwcmd: register

Scwcmd: rollback

Scwcmd: transform

Scwcmd: view

Secedit

Secedit:analyze

Secedit:configure

Secedit:export

Secedit:generaterollback

Secedit:import

Secedit:validate

Serverceipoptin

Servermanagercmd

Serverweroptin

Set

Setlocal

Setspn

Setx

Sfc

Shadow

Shift

Showmount

Shutdown

Sort

Start

Storrept

Storrept reports

Storrept reports list

Storrept reports add

Storrept reports modify

Storrept reports delete

Storrept reports generate

Storrept reports cancel

Creating a task for File Server Resource Manager reports by using the schtasks command

Storrept admin

Storrept admin options

Storrept admin defaults

Subst

Sxstrace

Sysocmgr

Systeminfo

Takeown

Tapicfg

Taskkill

Tasklist

Tcmsetup

Telnet

Telnet: close

Telnet: display

Telnet: open

Telnet: quit

Telnet: set

Telnet: send

Telnet: status

Telnet: unset

Telnet: ?

Tftp

Time

Timeout

Title

Tlntadmn

Tracerpt

Tracert

Tree

Tscon

Tsdiscon

Tsecimp

Tskill

Tsprof

Type

Typeperf

Tzutil

Uddiconfig

Umount

Unlodctr

Ver

Verifier

Verify

Vol

Vssadmin

Vssadmin add shadowstorage

Vssadmin create shadow

Vssadmin delete shadows

Vssadmin delete shadowstorage

Vssadmin list providers

Vssadmin list shadows

Vssadmin list shadowstorage

Vssadmin list volumes

Vssadmin list writers

Vssadmin resize shadowstorage

W32tm

Waitfor

Wbadmin

Wbadmin enable backup

Wbadmin disable backup

Wbadmin start backup

Wbadmin stop job

Wbadmin get versions

Wbadmin get items

Wbadmin start recovery

Wbadmin get status

Wbadmin get disks

Wbadmin start systemstaterecovery

Wbadmin start systemstatebackup

Wbadmin delete systemstatebackup

Wbadmin start sysrecovery

Wbadmin restore catalog

Wbadmin delete catalog

Wdsutil

/add

/add-AllDriverPackages

/add-Device

/add-DriverGroup

/add-DriverGroupFilter

/add-DriverGroupPackage

/add-DriverGroupPackages

/add-DriverPackage

/add-Image

/add-ImageDriverPackage

/add-ImageDriverPackages

/add-ImageGroup

/approve-AutoAddDevices

/convert-RiprepImage

/copy

/copy-DriverGroup

/copy-Image

/delete-AutoAddDevices

/disable

/disable-Server

/disable-TransportServer

/disconnect-Client

/enable

/enable-Server

/enable-TransportServer

/export-Image

/get

/get-AllDevices

/get-AllDriverGroups

/get-AllDriverPackages

/get-AllImageGroups

/get-AllImages

/get-AllMulticastTransmissions

/get-AllNamespaces

/get-AllServers

/get-AutoAddDevices

/get-Device

/get-DriverGroup

/get-DriverPackage

/get-DriverPackageFile

/get-Image

/get-ImageFile

/get-ImageGroup

/get-MulticastTransmission

/get-Namespace

/get-Server

/get-TransportServer

/initialize-Server

/new

/new-CaptureImage

/new-DiscoverImage

/new-MulticastTransmission

/new-Namespace

/reject-AutoAddDevices

/remove

/remove-DriverGroup

/remove-DriverGroupFilter

/remove-DriverGroupPackage

/remove-DriverGroupPackages

/remove-DriverPackage

/remove-DriverPackages

/remove-Image

/remove-ImageGroup

/remove-MulticastTransmission

/remove-Namespace

/replace-Image

/set

/set-Device

/set-DriverGroup

/set-DriverGroupFilter

/set-DriverPackage

/set-Image

/set-ImageGroup

/set-Server

/set-TransportServer

/start

/start-MulticastTransmission

/start-Namespace

/start-Server

/start-TransportServer

/stop

/stop-Server

/stop-TransportServer

/uninitialize-Server

/update-ServerFiles

/verbose

/progress

Wecutil

Wevtutil

Where

Whoami

Winnt

Winnt32

Winpop

Winrs

Winsat

winsat dwm

winsat d3d

winsat mem

winsat disk

winsat cpu

winsat media

winsat mfmedia

winsat features

winsat formal

Wlbs

Wmic

Wscript

Xcopy

**DNS Server Command Reference**

0 out of 1 rated this helpful

Updated: August 15, 2012

Applies To: Windows 8, Windows Server 2008, Windows Server 2012

Insert introduction here.

Section Heading

Insert section body here.

Subsection Heading

Insert subsection body here.

Top of Form

Thank you for your feedback

Bottom of Form

### Command Syntax {#h.h9kyurjnqqeg" id="h.h9kyurjnqqeg

#### msiexec.exe {#h.2ycpi6o977gd" id="h.2ycpi6o977gd

``C:\\>msiexec /?``

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

#### at.exe {#h.gcuqkw03gqk" id="h.gcuqkw03gqk

``C:\Windows\System32>at.exe /?``

```
The AT command schedules commands and programs to run on a computer at
a specified time and date. The Schedule service must be running to use
the AT command.

AT \[\\\\computername] \[ \[id] \[/DELETE] | /DELETE \[/YES]]
AT \[\\\\computername] time \[/INTERACTIVE]
   \[ /EVERY:date\[,...] | /NEXT:date\[,...]] "command"

\\\\computername Specifies a remote computer. Commands are scheduled on the
    local computer if this parameter is omitted.
    id Is an identification number assigned to a scheduled
    command.
/delete Cancels a scheduled command. If id is omitted, all the
    scheduled commands on the computer are canceled.
/yes Used with cancel all jobs command when no further
    confirmation is desired.
time Specifies the time when command is to run.
/interactive Allows the job to interact with the desktop of the user
    who is logged on at the time the job runs.
/every:date\[,...] Runs the command on each specified day(s) of the week or
    month. If date is omitted, the current day of the month
    is assumed.
/next:date\[,...] Runs the specified command on the next occurrence of the
    day (for example, next Thursday). If date is omitted, the
current day of the month is assumed.
"command" Is the Windows NT command, or batch program to be run.
```

#### slmgr.vbs {#license-mgr-script}

Software Licensing Management Tool (slmgr.vbs)

Syntax

``slmgr \[MachineName \[Username Password]] \[Option]``

Key

machinename The machine to administer, by default the current local machine.

username An administrator equivalent user account for the remote computer.

password The password for the user account on the remote computer.

Options

/ato Activate Windows license and product key against Microsoft’s server.

``/atp Confirmation\_ID Activate Windows with user-provided Confirmation ID``

/ckms Clear the name of KMS server used to default and port to default.

/cpky Clear product key from the registry (prevents disclosure attacks)

/dli Display the current license information with activation status and partial product key.

/dlv Verbose, similar to -dli but with more information.

/dti Display Installation ID for offline activation

/ipk Key Enter a new product key supplied as xxxxx-xxxxx-xxxxx-xxxxx-xxxxx

``/ilc License\_file Install license``

/rilc Re-install system license files

/rearm Reset the evaluation period/licensing status and activation state of the machine

/skms activationservername:port Set the Volume Licensing KMS server and/or the port used for KMS activation (where supported by your Windows edition)

/skhc Enable KMS host caching (default), this blocks the use of DNS priority and weight after the initial discovery of a working KMS host.

If the system can no longer contact the working KMS host, discovery will be attempted again.

/ckhc Disable KMS host caching. This setting instructs the client to use DNS auto-discovery each time it attempts KMS activation (recommended when using priority and weight)

/sai interval Sets the interval in minutes for unactivated clients to attempt KMS connection.

The activation interval must be between 15 minutes and 30 days, although the default (2 hours) is recommended.

The KMS client initially picks up this interval from the registry but switches to the KMS setting after the first KMS response has been received.

/sri interval Sets the renewal interval in minutes for activated clients to attempt KMS connection.

The renewal interval must be between 15 minutes and 30 days.

This option is set initially on both the KMS server and client sides.

The default is 10080 minutes (7 days).

/spri Set the KMS priority to normal (default).

/cpri Set the KMS priority to low.

Use this option to minimize contention from KMS in a co-hosted environment.

Note that this could lead to KMS starvation, depending on what other applications or server roles are active. Use with care.

/sprt port Sets the port on which the KMS host listens for client activation requests. The default TCP port is 1688.

/sdns Enable DNS publishing by the KMS host (default).

/cdns Disable DNS publishing by the KMS host.

/upk Uninstall current installed product key and return license status back to trial state.

/xpr Show the expiry date of current license (if not permanently activated)

#### slui.exe {#h.eh19dc1dc5mi" id="h.eh19dc1dc5mi

no command line or GUI help?

#### sysprep.exe {#h.29uv2zcpcsx6" id="h.29uv2zcpcsx6

``C:\Windows\System32\sysprep\sysprep.exe``

USAGE: sysprep.exe \[/quiet] \[/generalize] \[/audit | /oobe] \[/reboot | /shutdown | /quit] \[/unattend:\<filename>]

If no command-line arguments are provided, a graphical user interface is used to select the desired mode of sysprep operation.

#### ehshell.exe {#h.9qk6rclzcgm8" id="h.9qk6rclzcgm8

**Windows Media Center Shell (ehshell.exe) Command Line Switches and Options**

[http://www.mydigitallife.info/windows-media-center-shell-ehshellexe-command-line-switches-and-options/](http://www.mydigitallife.info/windows-media-center-shell-ehshellexe-command-line-switches-and-options/)

Windows Media Center is a digital home entertainment hub application included in Windows XP Media Center Edition and higher-end editions of Windows Vista, and has built-in support for remote control for keyboard-less operation. Usually when using WMC (Windows Media Center), your computer will boot directly to Media Center interface. However, in some situation such as for debugging and troubleshooting, the following command line switches and options available to Windows Media Center shell (ehshell.exe) may be useful.

ehshell.exe supports the following command line switches:

``**ehshell.exe /entrypoint:{APP\_GUID}\\{ENTRYPOINT\_GUID}**``

``This parameter starts Windows Media Center and navigates directly to a registered entry point. APP\_GUID and ENTRYPOINT\_GUID are strings that match the GUIDs of the desired application and entry point identifiers for the entry point to be launched. You must have previously registered the application using the RegisterApplication API or RegisterMceApp.exe for this command line switch to work correctly.``

``**ehshell.exe /url:\<url>**``

``This parameter starts Windows Media Center and navigates directly to a Hosted HTML application or XBAP application specified by \<url>.``

``**ehshell.exe /homepage:\<url>**``

``This parameter starts Windows Media Center and navigates directly to a Windows Media Center Presentation Layer Web Application specified by \<url>.``

``**ehshell.exe /addinfallbackpath:\<path>**``

``This parameter starts Windows Media Center and causes it to use to locate and load add-in assemblies. This location is only used after Windows Media Center attempts to load add-in assemblies from the global assembly cache (GAC) and %windir%\ehome. This switch can be combined with the /entrypoint switch described above to allow prototyping of Windows Media Center applications without needing to install an updated assembly to the GAC each time you rebuild your project in Visual Studio.``

**ehshell.exe /gdi**

This parameter starts Windows Media Center in GDI graphics mode. The GDI graphics mode simulates a low-fidelity graphics environment that does not support DirectX graphics mode.

**ehshell.exe /widescreen**

This parameter starts Windows Media Center with a 16 x 9 aspect ratio to enable testing widescreen display resolutions on systems that only have a 4 x 3 monitor installed. This switch works when Windows Media Center is started in windowed mode but not in full-screen mode. If you launch Windows Media Center with the /widescreen switch and it starts in full-screen mode, you will need to click the taskbar button in the top right corner of the Windows Media Center UI to change it to windowed mode, then close Windows Media Center and re-launch it using the /widescreen switch to see the correct 16 x 9 aspect ratio.

**ehshell.exe /rtl**

This parameter starts Windows Media Center in right-to-left display mode. This is useful for simulating how your application will look and behave on a right-to-left OS language such as Arabic or Hindi.

**ehshell.exe /directmedia:general**

Launches Windows Media Center in full screen mode, a new switch as part of Windows HotStart feature that can be used to launch Windows Media Center and cause it to navigate directly to one of the built-in experiences.

**ehshell.exe /directmedia:music**

Launches Windows Media Center in full screen mode and navigates to the music library, a new switch as part of Windows HotStart feature that can be used to launch Windows Media Center and cause it to navigate directly to one of the built-in experiences.

**ehshell.exe /directmedia:video**

Launches Windows Media Center in full screen mode and navigates to the video library, a new switch as part of Windows HotStart feature that can be used to launch Windows Media Center and cause it to navigate directly to one of the built-in experiences.

**ehshell.exe /directmedia:tv**

Launches Windows Media Center in full screen mode and navigates to the recorded TV library.

**ehshell.exe /directmedia:pictures**

Launches Windows Media Center in full screen mode and navigates to the picture library, a new switch as part of Windows HotStart feature that can be used to launch Windows Media Center and cause it to navigate directly to one of the built-in experiences.

**ehshell.exe /directmedia:discplayback**

Launches Windows Media Center in full screen mode and begins playback of the disc in the drive by reusing AutoRun code, a new switch as part of Windows HotStart feature that can be used to launch Windows Media Center and cause it to navigate directly to one of the built-in experiences.

#### wmplayer.exe {#h.any6oacfguwq" id="h.any6oacfguwq

[http://www.mydigitallife.info/control-windows-media-player-behaviour-with-command-line-parameters/](http://technet.microsoft.com/en-us/library/cc754352.aspx)

[http://msdn2.microsoft.com/en-us/library/ms984439.aspx](http://technet.microsoft.com/en-us/library/cc725833.aspx)

#### Control Windows Media Player Behaviour with Command Line Parameters {#h.4pjm6sqvyf4b" id="h.4pjm6sqvyf4b

Windows Media Player (wmplayer) including WMPlayer 9, WMP 10 and Windows Media Player 11 supports set of command line parameters and operators that specify how the Windows Media Player behaves when it starts or launches. The parameters are good for WMPlayer users who wants to use command prompt to control and modify the behavior or condition of Windows Media Player. These command line operators or parameters can also be added to Windows shortcut to Windows Media Player as option for the target of shortcut, i.e. wmplayer.exe.

According to[ ](http://technet.microsoft.com/en-us/library/cc753980.aspx)[MSDN](http://technet.microsoft.com/en-us/library/cc725868.aspx), the command line parameters that available for Windows Media Player include (with syntax and the changed behavior):

``“path\filename” (e.g. wmplayer “c:\filename.wma”) – Start the Player and play the file.``

``“path\filename” /fullscreen (e.g.: wmplayer “c:\filename.wmv” /fullscreen) – Play the specified file in full-screen mode. The path and file name of the content to play must be specified.``

/Device:{DVD|AudioCD} (e.g.: wmplayer /device:audio CD) – Play a DVD or audio CD.

``“path\filename”?WMPSkin=skin name (e.g.: wmplayer “c:\filename.wma”?wmpskin=headspace) – Open the Player, applying the specified skin.``

/Service:keyname – Open the Player showing the online store specified by keyname. (WMP10 and above only).

/Task NowPlaying – Open the Player in the Now Playing feature.

/Task MediaGuide – Open the Player in the Media Guide feature (current active online store in Windows Media Player).

/Task CDAudio – Open the Player in the Copy from CD feature (Rip feature in Windows Media Player).

/Task CDWrite – Open the Player in the Burn feature. (Requires Windows Media Player 10 or 11)

/Task MediaLibrary – Open the Player in the Media Library feature in Windows Media Player.

/Task RadioTuner – Open the Player in the Radio Tuner feature (current active online store in Windows Media Player).

/Task PortableDevice – Open the Player in the Copy to CD or Device feature (Sync feature in Windows Media Player).

/Task Services /Service servicename – Open the Player in the Premium Services feature, showing the service specified by the servicename parameter. This value is the unique name for the service. If the specified service has not been previously viewed, the servicename parameter is ignored. (Opens the specified online store in Windows Media Player)

/Task ServiceTaskX – Open the Player in the online store service task pane specified by X. For example, /Task ServiceTask1 opens the Player in the first online store service task pane.

/Task SkinViewer – Open the Player in the Skin Chooser feature.

/Playlist PlaylistName – Open the Player and play the specified playlist.

#### winrm.cmd {#h.pr5dvw6cgx0z" id="h.pr5dvw6cgx0z

Windows Remote Management

``C:\\>winrm.cmd``

Windows Remote Management Command Line Tool

Windows Remote Management (WinRM) is the Microsoft implementation of

the WS-Management protocol which provides a secure way to communicate

with local and remote computers using web services.

Usage:

``winrm OPERATION RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``\[@{KEY=VALUE\[;KEY=VALUE]...}]``

For help on a specific operation:

``winrm g\[et] -? Retrieving management information.``

``winrm s\[et] -? Modifying management information.``

``winrm c\[reate] -? Creating new instances of management resources.``

``winrm d\[elete] -? Remove an instance of a management resource.``

``winrm e\[numerate] -? List all instances of a management resource.``

``winrm i\[nvoke] -? Executes a method on a management resource.``

``winrm id\[entify] -? Determines if a WS-Management implementation is``

running on the remote machine.

winrm quickconfig -? Configures this machine to accept WS-Management

requests from other machines.

winrm configSDDL -? Modify an existing security descriptor for a URI.

winrm helpmsg -? Displays error message for the error code.

For help on related topics:

winrm help uris How to construct resource URIs.

winrm help aliases Abbreviations for URIs.

winrm help config Configuring WinRM client and service settings.

winrm help certmapping Configuring client certificate access.

winrm help remoting How to access remote machines.

winrm help auth Providing credentials for remote access.

winrm help input Providing input to create, set, and invoke.

winrm help switches Other switches such as formatting, options, etc.

winrm help proxy Providing proxy information.

``C:\\>winrm g -?``

Windows Remote Management Command Line Tool

``winrm get RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``Retrieves instances of RESOURCE\_URI using specified``

options and key-value pairs.

Example: Retrieve current configuration in XML format:

winrm get winrm/config -format:pretty

``Example: Retrieve spooler instance of Win32\_Service class:``

``winrm get wmicimv2/Win32\_Service?Name=spooler``

Example: Retrieve a certmapping entry on this machine:

winrm get winrm/config/service/certmapping?Issuer=1212131238d84023982e381f2039

``1a2935301923+Subject=\*.example.com+URI=wmicimv2/\*``

See also:

winrm help uris

winrm help aliases

winrm help switches

``C:\\>winrm s -?``

Windows Remote Management Command Line Tool

``winrm set RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``\[@{KEY="VALUE"\[;KEY="VALUE"]}]``

``\[-file:VALUE]``

``Modifies settings in RESOURCE\_URI using specified switches``

and input of changed values via key-value pairs or updated

object via an input file.

Example: Modify a configuration property of WinRM:

winrm set winrm/config @{MaxEnvelopeSizekb="100"}

Example: Disable a listener on this machine:

``winrm set winrm/config/Listener?Address=\*+Transport=HTTPS @{Enabled="false"}``

Example: Disable a certmapping entry on this machine:

Winrm set winrm/config/service/certmapping?Issuer=1212131238d84023982e381f2039

``1a2935301923+Subject=\*.example.com+URI=wmicimv2/\* @{Enabled="false"}``

See also:

winrm help uris

winrm help aliases

winrm help input

winrm help switches

``C:\\>winrm c -?``

Windows Remote Management Command Line Tool

``winrm create RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``\[@{KEY="VALUE"\[;KEY="VALUE"]}]``

``\[-file:VALUE]``

``Spawns an instance of RESOURCE\_URI using specified``

key-value pairs or input file.

Example: Create instance of HTTP Listener on IPv6 address:

winrm create winrm/config/Listener?Address=IP:3ffe:8311:ffff:f2c1::5e61+Transp

ort=HTTP

Example: Create instance of HTTPS Listener on all IPs:

``winrm create winrm/config/Listener?Address=\*+Transport=HTTPS @{Hostname="HOST"``

;CertificateThumbprint="XXXXXXXXXX"}

Note: XXXXXXXXXX represents a 40-digit hex string; see help config.

Example: Create a windows shell command instance from xml:

winrm create shell/cmd -file:shell.xml -remote:srv.corp.com

Example: Create a CertMapping entry:

winrm create winrm/config/service/certmapping?Issuer=1212131238d84023982e381f2

``0391a2935301923+Subject=\*.example.com+URI=wmicimv2/\* @{UserName="USERNAME";Passw``

ord="PASSWORD"} -remote:localhost

See also:

winrm help uris

winrm help aliases

winrm help input

winrm help switches

``C:\\>winrm d -?``

Windows Remote Management Command Line Tool

``winrm delete RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``Removes an instance of RESOURCE\_URI.``

Example: delete the HTTP listener on this machine for given IP address:

winrm delete winrm/config/Listener?Address=IP:192.168.2.1+Transport=HTTP

Example: delete a certmapping entry:

winrm delete winrm/config/service/certmapping?Issuer=1212131238d84023982e381f2

``0391a2935301923+Subject=\*.example.com+URI=wmicimv2/\*``

See also:

winrm help uris

winrm help aliases

winrm help switches

``C:\\>winrm e -?``

Windows Remote Management Command Line Tool

``winrm enumerate RESOURCE\_URI \[-ReturnType:Value] \[-Shallow]``

``\[-BasePropertiesOnly] \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``Lists instances of RESOURCE\_URI.``

Can limit the instances returned by using a filter and dialect if the

resource supports these.

ReturnType

``\----------``

returnType is an optional switch that determines the type of data returned.

Possible options are 'Object', 'EPR' and 'ObjectAndEPR'. Default is Object

If Object is specified or if switch is omitted, then only the objects are

returned.

If EPR is specified, then only the EPRs (End point reference) of the

objects are returned. EPRs contain information about the resource URI and

selectors for the instance.

If ObjectAndEPR is specified, then both the object and the associated EPRs

are returned.

Shallow

``\-------``

Enumerate only instances of the base class specified in the resource URI.

If this flag is not specified, instances of the base class specified in

the resource URI and all its derived classes are returned.

BasePropertiesOnly

``\------------------``

Includes only those properties that are part of the base class specified

in the resource URI. When -Shallow is specified, this flag has no effect.

Example: List all WinRM listeners on this machine:

winrm enumerate winrm/config/Listener

``Example: List all instances of Win32\_Service class:``

``winrm enumerate wmicimv2/Win32\_Service``

Example: List all shell instances on a machine:

winrm enum shell/cmd -remote:srv.corp.com

Example: List resources accessible to the current user:

winrm enum winrm/config/resource

Example: List all certmapping settings:

winrm enum winrm/config/service/certmapping

See also:

winrm help uris

winrm help aliases

winrm help filters

winrm help switches

``C:\\>winrm i -?``

Windows Remote Management Command Line Tool

``winrm invoke ACTION RESOURCE\_URI \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

``\[@{KEY="VALUE"\[;KEY="VALUE"]}]``

``\[-file:VALUE]``

``Executes method specified by ACTION on target object specified by RESOURCE\_URI``

with parameters specified by key-value pairs.

Example: Call StartService method on Spooler service:

``winrm invoke StartService wmicimv2/Win32\_Service?Name=spooler``

Example: Call StopService method on Spooler service using XML file:

``winrm invoke StopService wmicimv2/Win32\_Service?Name=spooler -file:input.xml``

Where input.xml:

``\<p:StopService\_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root``

``/cimv2/Win32\_Service"/>``

``Example: Call Create method of Win32\_Process class with specified parameters:``

``winrm invoke Create wmicimv2/Win32\_Process @{CommandLine="notepad.exe";Current``

``Directory="C:\\"}``

Example: Restore the default winrm configuration:

Note that this will not restore the default winrm plugin configuration:

winrm invoke restore winrm/config @{}

Example: Restore the default winrm plugin configuration:

Note that all external plugins will be unregistered during this operation:

winrm invoke restore winrm/config/plugin @{}

See also:

winrm help uris

winrm help aliases

winrm help input

winrm help switches

``C:\\>winrm id -?``

Windows Remote Management Command Line Tool

``winrm identify \[-SWITCH:VALUE \[-SWITCH:VALUE] ...]``

Issues an operation against a remote machine to see if the WS-Management

service is running. This operation must be run with the '-remote' switch.

To run this operation unauthenticated against the remote machine use the

``\-auth:none``

Example: identify if WS-Management is running on www.example.com:

winrm identify -remote:www.example.com

See also:

winrm help switches

winrm help remoting

``C:\\>winrm quickconfig -?``

Windows Remote Management Command Line Tool

``winrm quickconfig \[-quiet] \[-transport:VALUE] \[-force]``

Performs configuration actions to enable this machine for remote management.

Includes:

``1\. Start the WinRM service``

``2\. Set the WinRM service type to auto start``

``3\. Create a listener to accept request on any IP address``

``4\. Enable firewall exception for WS-Management traffic (for http only)``

``\-q\[uiet]``

``\--------``

If present, quickconfig will not prompt for confirmation.

``\-transport:VALUE``

``\----------------``

Perform quickconfig for specific transport.

Possible options are http and https. Defaults to http.

``\-force``

``\--------``

If present, quickconfig will not prompt for confirmation, and will enable

the firewall exception regardless of current network profile settings.

See also:

winrm help config

``C:\\>winrm help config``

Windows Remote Management Command Line Tool

Configuration for WinRM is managed using the winrm command line or through GPO.

Configuration includes global configuration for both the client and service.

The WinRM service requires at least one listener to indicate the IP address(es)

on which to accept WS-Management requests. For example, if the machine has

multiple network cards, WinRM can be configured to only accept requests from

one of the network cards.

Global configuration

winrm get winrm/config

winrm get winrm/config/client

winrm get winrm/config/service

winrm enumerate winrm/config/resource

winrm enumerate winrm/config/listener

winrm enumerate winrm/config/plugin

winrm enumerate winrm/config/service/certmapping

Network listening requires one or more listeners.

Listeners are identified by two selectors: Address and Transport.

Address must be one of:

``\* - Listen on all IPs on the machine``

IP:1.2.3.4 - Listen only on the specified IP address

MAC:... - Listen only on IP address for the specified MAC

Note: All listening is subject to the IPv4Filter and IPv6Filter under

config/service.

Note: IP may be an IPv4 or IPv6 address.

Transport must be one of:

HTTP - Listen for requests on HTTP (default port is 5985)

HTTPS - Listen for requests on HTTPS (default port is 5986)

Note: HTTP traffic by default only allows messages encrypted with

the Negotiate or Kerberos SSP.

When configuring HTTPS, the following properties are used:

Hostname - Name of this machine; must match CN in certificate.

CertificateThumbprint - hexadecimal thumbprint of certificate appropriate for

Server Authentication.

Note: If only Hostname is supplied, WinRM will try to find an appropriate

certificate.

Example: To listen for requests on HTTP on all IPs on the machine:

``winrm create winrm/config/listener?Address=\*+Transport=HTTP``

Example: To disable a given listener

winrm set winrm/config/listener?Address=IP:1.2.3.4+Transport=HTTP @{Enabled="f

alse"}

Example: To enable basic authentication on the client but not the service:

winrm set winrm/config/client/auth @{Basic="true"}

Example: To enable Negotiate for all workgroup machines.

``winrm set winrm/config/client @{TrustedHosts="\<local>"}``

See also:

winrm help uris

winrm help aliases

winrm help certmapping

winrm help input

winrm help switches

``C:\\>``

#### winrs.exe {#h.4py3p5s070q1" id="h.4py3p5s070q1

Windows Remote Shell

``C:\\>winrs /?``

USAGE

``\=====``

(ALL UPPER-CASE = value that must be supplied by user.)

``winrs \[-/SWITCH\[:VALUE]] COMMAND``

COMMAND - Any string that can be executed as a command in the cmd.exe shell.

SWITCHES

``\========``

(All switches accept both short form or long form. For example both -r and

``\-remote are valid.)``

``\-r\[emote]:ENDPOINT - The target endpoint using a NetBIOS name or the standard connection URL: \[TRANSPORT://]TARGET\[:PORT]. If not specified``

``\-r:localhost is used.``

``\-un\[encrypted] - Specify that the messages to the remote shell will not be encrypted. This is useful for troubleshooting, or when the network traffic is already encrypted using ipsec, or when physical security is enforced. By default the messages are encrypted using Kerberos or NTLM keys. This switch is ignored when HTTPS transport is selected.``

``\-u\[sername]:USERNAME - Specify username on command line. If not specified the tool will use Negotiate authentication or prompt for the name.``

If -username is specified, -password must be as well.

``\-p\[assword]:PASSWORD - Specify password on command line. If -password is not specified but -username is the tool will prompt for the password. If -password is specified, -user must be specified as well.``

``\-t\[imeout]:SECONDS - This option is deprecated.``

``\-d\[irectory]:PATH - Specifies starting directory for remote shell. If not specified the remote shell will start in the user's home directory defined by the environment variable %USERPROFILE%.``

``\-env\[ironment]:STRING=VALUE - Specifies a single environment variable to be set when shell starts, which allows changing default environment for shell. Multiple occurrences of this switch must be used to specify multiple environment variables.``

``\-noe\[cho] - Specifies that echo should be disabled. This may be necessary to ensure that user's answers to remote prompts are not displayed locally. By default echo is "on".``

``\-nop\[rofile] - Specifies that the user's profile should not be loaded. By default the server will attempt to load the user profile. If the remote user is not a local administrator on the target system then this option will be required (the default will result in error).``

``\-a\[llow]d\[elegate] - Specifies that the user's credentials can be used to access a remote share, for example, found on a different machine than the target endpoint.``

``\-comp\[ression] - Turn on compression. Older installations on remote machines may not support compression so it is off by default.``

``\-\[use]ssl - Use an SSL connection when using a remote endpoint. Specifying this instead of the transport "https:" will use the default WinRM default port.``

``\-? - Help``

To terminate the remote command the user can type Ctrl-C or Ctrl-Break, which will be sent to the remote shell. The second Ctrl-C will force termination of winrs.exe.

To manage active remote shells or WinRS configuration, use the WinRM tool. The URI alias to manage active shells is shell/cmd. The URI alias for WinRS configuration is winrm/config/winrs. Example usage can be found in the WinRM tool by typing "WinRM -?".

Examples:

winrs -r:https://myserver.com command

winrs -r:myserver.com -usessl command

winrs -r:myserver command

winrs -r:http://127.0.0.1 command

winrs -r:http://169.51.2.101:80 -unencrypted command

``winrs -r:https://\[::FFFF:129.144.52.38] command``

``winrs -r:http://\[1080:0:0:0:8:800:200C:417A]:80 command``

``winrs -r:https://myserver.com -t:600 -u:administrator -p:$%fgh7 ipconfig``

``winrs -r:myserver -env:PATH=^%PATH^%;c:\tools -env:TEMP=d:\temp config.cmd``

``winrs -r:myserver netdom join myserver /domain:testdomain /userd:johns /passwordd:$%fgh789``

``winrs -r:myserver -ad -u:administrator -p:$%fgh7 dir \\\anotherserver\share``

``C:\\>``

#### SFC {#h.otdn2ca088zj" id="h.otdn2ca088zj

Microsoft (R) Windows (R) Resource Checker Version 6.0

Copyright (c) 2006 Microsoft Corporation. All rights reserved.

Scans the integrity of all protected system files and replaces incorrect versions with correct Microsoft versions.

``SFC \[/SCANNOW] \[/VERIFYONLY] \[/SCANFILE=\<file>] \[/VERIFYFILE=\<file>]``

``\[/OFFWINDIR=\<offline windows directory> /OFFBOOTDIR=\<offline boot directory>]``

/SCANNOW Scans integrity of all protected system files and repairs files with

problems when possible.

/VERIFYONLY Scans integrity of all protected system files. No repair operation is

performed.

/SCANFILE Scans integrity of the referenced file, repairs file if problems are

``identified. Specify full path \<file>``

``/VERIFYFILE Verifies the integrity of the file with full path \<file>. No repair``

operation is performed.

/OFFBOOTDIR For offline repair specify the location of the offline boot directory

/OFFWINDIR For offline repair specify the location of the offline windows directory

e.g.

sfc /SCANNOW

``sfc /VERIFYFILE=c:\windows\system32\kernel32.dll``

``sfc /SCANFILE=d:\windows\system32\kernel32.dll /OFFBOOTDIR=d:\ /OFFWINDIR=d:\windows``

sfc /VERIFYONLY

#### NET {#net.exe}

``C:\\>NET HELP``

command

``\-or-``

NET command /HELP

Commands available are:

NET ACCOUNTS NET HELPMSG NET STATISTICS

NET COMPUTER NET LOCALGROUP NET STOP

NET CONFIG NET PAUSE NET TIME

NET CONTINUE NET SESSION NET USE

NET FILE NET SHARE NET USER

NET GROUP NET START NET VIEW

NET HELP

NET HELP NAMES explains different types of names in NET HELP syntax lines.

NET HELP SERVICES lists some of the services you can start.

NET HELP SYNTAX explains how to read NET HELP syntax lines.

NET HELP command | MORE displays Help one screen at a time.

``C:\\>net help names``

The syntax of this command is:

NAMES

The following types of names are used with Windows:

Computername A unique name that identifies a computer on

the local-area network.

Devicename The name by which Windows identifies a disk resource

or printer. A disk resource is identified by a drive

letter followed by a colon (for example, D:). A

printer is identified by a port name followed by a colon

(for example, LPT1:).

Workgroup A group of computers on the network. Each workgroup

has a unique name.

Localgroup A group of names in a Workgroup that are granted the

same rights.

Domain A group of Windows Servers, Windows Workstations

and other computers on the network. A

domain has a unique name. Usually, you must log on in

a domain to gain access to the network. Domains are

created and managed with Windows Server.

Global group A group of names in a domain that are granted the

same rights.

Filename The name of a file. Under the file allocation table

(FAT) file system, a filename can have as many as eight

characters, followed by a period (.) and an extension of

as many as three characters. Under NTFS and HPFS, a

filename can have as many as 254 characters.

Network path A description of the location of a shared resource,

consisting of a computer's computername followed by

the sharename of the resource. The computername

is preceded by two backslashes, and the sharename is

preceded by one backslash (for example,

``\\\SERVER1\RESOURCE).``

Path The location of a directory. A path can consist of a

devicename and one or more directory names. A

``backslash (\\) precedes each directory name (for example,``

``C:\CUSTOMER\CORP\ACCT).``

Pathname A path and a filename. The filename is preceded by a

``backslash (\\) (for example, C:\CUSTOMER\CORP\REPORT.DOC).``

Sharename A name that identifies a shared resource on a computer. A

sharename is used with the computer's computername to form

``a network path (as in \\\SERVER\RESOURCE).``

Username The name a person supplies when logging on at

a computer.

``C:\\>net help services``

The syntax of this command is:

To view these definitions one screen at a time, type NET HELP NAMES | MORE.

SERVICES

NET START can be used to start services, including:

NET START BROWSER

NET START CLIENT SERVICE FOR NETWARE

NET START CLIPBOOK

NET START DHCP CLIENT

NET START EVENTLOG

NET START FILE REPLICATION

NET START NET LOGON

NET START NT LM SECURITY SUPPORT PROVIDER

NET START PLUG AND PLAY

NET START REMOTE ACCESS CONNECTION MANAGER

NET START ROUTING AND REMOTE ACCESS

NET START RPCLOCATOR

NET START RPCSS

NET START SCHEDULE

NET START SERVER

NET START SPOOLER

NET START TCP/IP NETBIOS HELPER SERVICE

NET START UPS

NET START WORKSTATION

When typed at the command prompt, service names of two words or more must

be enclosed in quotation marks. For example, NET START "NET LOGON"

starts the net logon service.

#### netsh {#h.8hlv2eqiapm" id="h.8hlv2eqiapm

``C:\\>netsh ?``

netsh>?

The following commands are available:

Commands in this context:

.. - Goes up one context level.

? - Displays a list of commands.

abort - Discards changes made while in offline mode.

add - Adds a configuration entry to a list of entries.

``advfirewall - Changes to the \`netsh advfirewall' context.``

alias - Adds an alias.

``branchcache - Changes to the \`netsh branchcache' context.``

``bridge - Changes to the \`netsh bridge' context.``

bye - Exits the program.

commit - Commits changes made while in offline mode.

delete - Deletes a configuration entry from a list of entries.

``dhcp - Changes to the \`netsh dhcp' context.``

``dhcpclient - Changes to the \`netsh dhcpclient' context.``

``dnsclient - Changes to the \`netsh dnsclient' context.``

dump - Displays a configuration script.

exec - Runs a script file.

exit - Exits the program.

``firewall - Changes to the \`netsh firewall' context.``

help - Displays a list of commands.

``http - Changes to the \`netsh http' context.``

``interface - Changes to the \`netsh interface' context.``

``ipsec - Changes to the \`netsh ipsec' context.``

``lan - Changes to the \`netsh lan' context.``

``mbn - Changes to the \`netsh mbn' context.``

``namespace - Changes to the \`netsh namespace' context.``

``nap - Changes to the \`netsh nap' context.``

``netio - Changes to the \`netsh netio' context.``

offline - Sets the current mode to offline.

online - Sets the current mode to online.

``p2p - Changes to the \`netsh p2p' context.``

popd - Pops a context from the stack.

pushd - Pushes current context on stack.

quit - Exits the program.

``ras - Changes to the \`netsh ras' context.``

``rpc - Changes to the \`netsh rpc' context.``

set - Updates configuration settings.

show - Displays information.

``trace - Changes to the \`netsh trace' context.``

unalias - Deletes an alias.

``wcn - Changes to the \`netsh wcn' context.``

``wfp - Changes to the \`netsh wfp' context.``

``winhttp - Changes to the \`netsh winhttp' context.``

``winsock - Changes to the \`netsh winsock' context.``

``wlan - Changes to the \`netsh wlan' context.``

The following sub-contexts are available:

advfirewall branchcache bridge dhcp dhcpclient dnsclient firewall http interface ipsec lan mbn namespace nap netio p2p ras rpc trace wcn wfp winhttp winsock wlan

To view help for a command, type the command, followed by a space, and then

type ?.

#### sysprep {#h.ay13tnsqgyz2" id="h.ay13tnsqgyz2

USAGE: sysprep.exe \[/quiet] \[/generalize] \[/audit | /oobe] \[/reboot | /shutdown | /quit] \[/unattend:\<filename>]

If no command-line arguments are provided, a graphical user interface is used to select the desired mode of sysprep operation.

#### ipconfig.exe {#h.ottiavvmm3mz" id="h.ottiavvmm3mz

``C:\Windows\System32\ipconfig.exe /?``

USAGE:

ipconfig \[/allcompartments] \[/? | /all |

/renew \[adapter] | /release \[adapter] |

/renew6 \[adapter] | /release6 \[adapter] |

/flushdns | /displaydns | /registerdns |

/showclassid adapter |

/setclassid adapter \[classid] |

/showclassid6 adapter |

``/setclassid6 adapter \[classid] ]``

where

adapter Connection name

``(wildcard characters \* and ? allowed, see examples)``

Options:

/? Display this help message

/all Display full configuration information.

/release Release the IPv4 address for the specified adapter.

/release6 Release the IPv6 address for the specified adapter.

/renew Renew the IPv4 address for the specified adapter.

/renew6 Renew the IPv6 address for the specified adapter.

/flushdns Purges the DNS Resolver cache.

/registerdns Refreshes all DHCP leases and re-registers DNS names

/displaydns Display the contents of the DNS Resolver Cache.

/showclassid Displays all the dhcp class IDs allowed for adapter.

/setclassid Modifies the dhcp class id.

/showclassid6 Displays all the IPv6 DHCP class IDs allowed for adapter.

/setclassid6 Modifies the IPv6 DHCP class id.

The default is to display only the IP address, subnet mask and default gateway for each adapter bound to TCP/IP.

For Release and Renew, if no adapter name is specified, then the IP address leases for all adapters bound to TCP/IP will be released or renewed.

For Setclassid and Setclassid6, if no ClassId is specified, then the ClassId is removed.

Examples:

``\> ipconfig ... Show information``

``\> ipconfig /all ... Show detailed information``

``\> ipconfig /renew ... renew all adapters``

``\> ipconfig /renew EL\* ... renew any connection that has its``

name starting with EL

``\> ipconfig /release \*Con\* ... release all matching connections,``

eg. "Local Area Connection 1" or

"Local Area Connection 2"

``\> ipconfig /allcompartments ... Show information about all``

compartments

``\> ipconfig /allcompartments /all ... Show detailed information about all``

compartments

``C:\Windows\System32>``

#### sc.exe {#h.xj97epqun85h" id="h.xj97epqun85h

``C:\Windows\System32\sc.exe``

DESCRIPTION:

SC is a command line program used for communicating with the

Service Control Manager and services.

USAGE:

``sc \<server> \[command] \[service name] \<option1> \<option2>...``

``The option \<server> has the form "\\\ServerName"``

``Further help on commands can be obtained by typing: "sc \[command]"``

Commands:

query-----------Queries the status for a service, or

enumerates the status for types of services.

queryex---------Queries the extended status for a service, or

enumerates the status for types of services.

start-----------Starts a service.

pause-----------Sends a PAUSE control request to a service.

interrogate-----Sends an INTERROGATE control request to a service.

continue--------Sends a CONTINUE control request to a service.

stop------------Sends a STOP request to a service.

config----------Changes the configuration of a service (persistent).

description-----Changes the description of a service.

failure---------Changes the actions taken by a service upon failure.

failureflag-----Changes the failure actions flag of a service.

sidtype---------Changes the service SID type of a service.

privs-----------Changes the required privileges of a service.

qc--------------Queries the configuration information for a service.

qdescription----Queries the description for a service.

qfailure--------Queries the actions taken by a service upon failure.

qfailureflag----Queries the failure actions flag of a service.

qsidtype--------Queries the service SID type of a service.

qprivs----------Queries the required privileges of a service.

qtriggerinfo----Queries the trigger parameters of a service.

qpreferrednode--Queries the preferred NUMA node of a service.

delete----------Deletes a service (from the registry).

create----------Creates a service. (adds it to the registry).

control---------Sends a control to a service.

sdshow----------Displays a service's security descriptor.

sdset-----------Sets a service's security descriptor.

showsid---------Displays the service SID string corresponding to an arbitrary name.

triggerinfo-----Configures the trigger parameters of a service.

preferrednode---Sets the preferred NUMA node of a service.

GetDisplayName--Gets the DisplayName for a service.

GetKeyName------Gets the ServiceKeyName for a service.

EnumDepend------Enumerates Service Dependencies.

The following commands don't require a service name:

``sc \<server> \<command> \<option>``

boot------------(ok | bad) Indicates whether the last boot should

be saved as the last-known-good boot configuration

Lock------------Locks the Service Database

QueryLock-------Queries the LockStatus for the SCManager Database

EXAMPLE:

sc start MyService

Would you like to see help for the QUERY and QUERYEX commands? \[ y | n ]:

y

QUERY and QUERYEX OPTIONS:

If the query command is followed by a service name, the status

for that service is returned. Further options do not apply in

this case. If the query command is followed by nothing or one of

the options listed below, the services are enumerated.

type= Type of services to enumerate (driver, service, all)

(default = service)

state= State of services to enumerate (inactive, all)

(default = active)

bufsize= The size (in bytes) of the enumeration buffer

(default = 4096)

ri= The resume index number at which to begin the enumeration

(default = 0)

group= Service group to enumerate

(default = all groups)

SYNTAX EXAMPLES

sc query - Enumerates status for active services & drivers

sc query eventlog - Displays status for the eventlog service

sc queryex eventlog - Displays extended status for the eventlog service

sc query type= driver - Enumerates only active drivers

sc query type= service - Enumerates only Win32 services

sc query state= all - Enumerates all services & drivers

sc query bufsize= 50 - Enumerates with a 50 byte buffer

sc query ri= 14 - Enumerates with resume index = 14

sc queryex group= "" - Enumerates active services not in a group

sc query type= interact - Enumerates all interactive services

sc query type= driver group= NDIS - Enumerates all NDIS drivers

``C:\\>``

#### dsmod.exe {#h.6h8t9i93kt0u" id="h.6h8t9i93kt0u

``C:\Windows\System32\dsmod.exe /?``

Description: This dsmod command modifies existing objects in the directory.

The dsmod commands include:

dsmod computer - modifies an existing computer in the directory.

dsmod contact - modifies an existing contact in the directory.

dsmod group - modifies an existing group in the directory.

dsmod ou - modifies an existing organizational unit in the directory.

dsmod server - modifies an existing AD DC/LDS instance in the directory.

dsmod user - modifies an existing user in the directory.

dsmod quota - modifies an existing quota specification in the directory.

dsmod partition - modifies an existing partition specification in the directory.

``For help on a specific command, type "dsmod \<ObjectType> /?" where``

``\<ObjectType> is one of the supported object types shown above.``

For example, dsmod ou /?.

Remarks:

The dsmod commands support piping of input to allow you to pipe results from the dsquery commands as input to the dsmod commands and modify the objects found by the dsquery commands.

``Commas that are not used as separators in distinguished names must be escaped with the backslash ("\\") character``

``(for example, "CN=Company\\, Inc.,CN=Users,DC=microsoft,DC=com").``

Backslashes used in distinguished names must be escaped with a backslash

``(for example, "CN=Sales\\\ Latin America,OU=Distribution Lists,DC=microsoft,DC=com").``

Examples:

To find all users in the organizational unit (OU)

"ou=Marketing,dc=microsoft,dc=com" and add them to the Marketing Staff group:

dsquery user -startnode "ou=Marketing,dc=microsoft,dc=com" |

dsmod group "cn=Marketing Staff,ou=Marketing,dc=microsoft,dc=com" -addmbr

Directory Service command-line tools help:

dsadd /? - help for adding objects.

dsget /? - help for displaying objects.

dsmod /? - help for modifying objects.

dsmove /? - help for moving objects.

dsquery /? - help for finding objects matching search criteria.

dsrm /? - help for deleting objects.

#### dsmove.exe {#h.yezh1iab40z" id="h.yezh1iab40z

``C:\Windows\System32>dsmove.exe /?``

Description: This command moves or renames an object within the directory.

``Syntax: dsmove \<ObjectDN>``

``\[-newparent \<ParentDN>]``

``\[-newname \<NewName>]``

\[{-s \<Server> | -d \<Domain>}]

``\[-u \<UserName>]``

\[-p {\<Password> | \*}]

``\[-q]``

\[{-uc | -uco | -uci}]

Parameters:

Value Description

``\<ObjectDN> Required/stdin. Distinguished name (DN)``

of object to move or rename.

If this parameter is omitted it

will be taken from standard input (stdin).

``\-newparent \<ParentDN> DN of the new parent location to which object``

should be moved.

``\-newname \<NewName> New relative distinguished name (RDN) value``

to which object should be renamed.

{-s \<Server> | -d \<Domain>}

``\-s \<Server> connects to the AD DC/LDS instance``

``with name \<Server>.``

``\-d \<Domain> connects to an AD DC in domain \<Domain>.``

Default: an AD DC in the logon domain.

``\-u \<UserName> Connect as \<UserName>. Default: the logged in user.``

``User name can be: user name, domain\user name,``

or user principal name (UPN).

``\-p \<Password> Password for the user \<UserName>.``

``If \* is used, then the command prompts for a``

password.

``\-q Quiet mode: suppress all output to standard output.``

{-uc | -uco | -uci} -uc Specifies that input from or output to pipe is

formatted in Unicode.

``\-uco Specifies that output to pipe or file is``

formatted in Unicode.

``\-uci Specifies that input from pipe or file is``

formatted in Unicode.

Remarks:

If a value that you supply contains spaces, use quotation marks

around the text (for example, "CN=John Smith,CN=Users,DC=microsoft,DC=com").

If you enter multiple values, the values must be separated by spaces

(for example, a list of distinguished names).

Commas that are not used as separators in distinguished names must be

``escaped with the backslash ("\\") character``

``(for example, "CN=Company\\, Inc.,CN=Users,DC=microsoft,DC=com").``

Backslashes used in distinguished names must be escaped with a backslash

(for example,

``"CN=Sales\\\ Latin America,OU=Distribution Lists,DC=microsoft,DC=com").``

Examples:

The user object for the user Jane Doe can be renamed to Jane Jones

with the following command:

dsmove "cn=Jane Doe,ou=sales,dc=microsoft,dc=com" -newname "Jane Jones"

The same user can be moved from the Sales organization to the Marketing

organization with the following command:

dsmove "cn=Jane Doe,ou=sales,dc=microsoft,dc=com"

``\-newparent ou=Marketing,dc=microsoft,dc=com``

The rename and move operations for the user can be combined with the

following command:

dsmove "cn=Jane Doe,ou=sales,dc=microsoft,dc=com"

``\-newparent ou=Marketing,dc=microsoft,dc=com -newname "Jane Jones"``

Directory Service command-line tools help:

dsadd /? - help for adding objects.

dsget /? - help for displaying objects.

dsmod /? - help for modifying objects.

dsmove /? - help for moving objects.

dsquery /? - help for finding objects matching search criteria.

dsrm /? - help for deleting objects.

dsmove succeeded

#### dsmgmt.exe {#h.8tqrhhpv4mdt" id="h.8tqrhhpv4mdt

``C:\Windows\System32>dsmgmt.exe /?``

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsmgmt facilitates managing AD DS/LDS application partitions, management

and control of the Flexible Single Master Operations (FSMO),

and cleaning up of metadata left behind by abandoned AD DCs/LDS instances,

those which are removed from the network without being uninstalled.

This is an interactive tool. Type "help" at the prompt for more information.

? - Show this help information

Configurable Settings - Manage configurable settings

DS Behavior - View and modify AD DS/LDS Behavior

Group Membership Evaluation - Evaluate SIDs in token for a given user or

group

Help - Show this help information

LDAP policies - Manage LDAP protocol policies

Local Roles - Local RODC roles management

Metadata cleanup - Clean up objects of decommissioned servers

Partition management - Manage directory partitions

Popups off - Disable popups

Popups on - Enable popups

Quit - Quit the utility

Roles - Manage NTDS role owner tokens

Security account management - Manage Security Account Database - Duplicate

SID Cleanup

Set DSRM Password - Reset directory service restore mode

administrator account password

#### dsdbutil.exe {#h.es1tu2tbmz39" id="h.es1tu2tbmz39

Directory Service Database Util (DSDBUtil)

``C:\\>dsdbutil.exe /?``

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsdbutil performs database maintenance of the Active Directory Domain Services store

and facilitates configuration of AD LDS communication ports and view AD LDS

instances installed on a machine.

This is an interactive tool. Type "help" at the prompt for more information.

? - Show this help information

``Activate Instance %s - Set "NTDS" or a specific AD LDS instance``

as the active instance.

Authoritative restore - Authoritatively restore the DIT database

``Change Service Account %s1 %s2 - Change AD DS/LDS Service Account to``

``username %s1 and password %s2.``

``Use "NULL" for blank password, \* to``

enter password from the console.

Files - Manage AD DS/LDS database files

Help - Show this help information

IFM - IFM media creation

``LDAP Port %d - Configure LDAP Port for an AD LDS Instance.``

List Instances - List all AD LDS instances installed

on this machine.

Popups off - Disable popups

Popups on - Enable popups

Quit - Quit the utility

Semantic database analysis - Semantic Checker

Snapshot - Snapshot management

``SSL Port %d - Configure SSL Port for an AD LDS Instance.``

#### ldifde.exe {#h.w1kihb42zl2m" id="h.w1kihb42zl2m

LDAP Import/Export File (LDIFDE)

C:>ldifde -?

LDIF Directory Exchange

General Parameters

``\==================``

``\-i Turn on Import Mode (The default is Export)``

``\-f filename Input or Output filename``

``\-s servername The server to bind to (Default to DC of computer's domain)``

``\-c FromDN ToDN Replace occurences of FromDN to ToDN``

If either FromDN or ToDN ends with #attributeName, the

attribute value will be looked up in rootDSE and used to

replace #attributeName. See example for "Macro expansion

in DNs".

``\-v Turn on Verbose Mode``

``\-j path Log File Location``

``\-t port Port Number (default = 389)``

``\-u Use Unicode format``

``\-w timeout Terminate execution if the server takes longer than the``

specified number of seconds to respond to an operation

(default = no timeout specified)

``\-h Enable SASL layer encryption``

``\-? Help``

Export Specific

``\===============``

``\-d RootDN The root of the LDAP search (Default to Naming Context)``

``\-r Filter LDAP search filter (Default to "(objectClass=\*)")``

``\-p SearchScope Search Scope (Base/OneLevel/Subtree)``

``\-l list List of attributes (comma separated) to look for``

in an LDAP search

``\-o list List of attributes (comma separated) to omit from``

input.

``\-g Disable Paged Search.``

``\-m Enable the SAM logic on export.``

``\-n Do not export binary values``

``\-x Include deleted objects (tombstones)``

``\-1 Retain only the important replPropertyMetadata``

Import

``\======``

``\-k The import will go on ignoring 'Constraint Violation'``

and 'Object Already Exists' errors

``\-y The import will use lazy commit for better performance``

(enabled by default)

``\-e The import will not use lazy commit``

``\-q threads The import will use the specified number of threads``

(default is 1)

``\-z Continue importing irrespective of errors.``

``\-x Enable tombstone reanimation support (passes deleted``

objects control with ldap modify requests)

Credentials Establishment

``\=========================``

Note that if no credentials is specified, LDIFDE will bind as the currently

logged on user, using SSPI.

\-a UserDN \[Password | \*] Simple authentication

\-b UserName Domain \[Password | \*] SSPI bind method

Example: Simple import of current domain

ldifde -i -f INPUT.LDF

Example: Simple export of current domain

ldifde -f OUTPUT.LDF

Example: Export of specific domain with credentials

ldifde -m -f OUTPUT.LDF

``\-b USERNAME DOMAINNAME \*``

``\-s SERVERNAME``

``\-d "cn=users,DC=DOMAINNAME,DC=Microsoft,DC=Com"``

``\-r "(objectClass=user)"``

Example: Macro expansion in DNs

ldifde -f export.ldf -c "#configurationNamingContext" "cn=configuration,dc=x"

ldifde -i -f import.ldf -c "cn=configuration,dc=x" "#configurationNamingContext"

No log files were written. In order to generate a log file, please

specify the log file path via the -j option.

#### ntdsutil.exe {#h.96rj0f2vfdwa" id="h.96rj0f2vfdwa

Directory Service Utility (NTDSUtil)

ntdsutil.exe /?

Microsoft(R) Windows(TM) Directory Service Utilities Version 2.0

Copyright (C) Microsoft Corporation 1991-2002. All Rights Reserved.

dsdbutil performs database maintenance of the Active Directory Domain Services store

and facilitates configuration of AD LDS communication ports and view AD LDS

instances installed on a machine.

This is an interactive tool. Type "help" at the prompt for more information.

? - Show this help information

``Activate Instance %s - Set "NTDS" or a specific AD LDS instance``

as the active instance.

Authoritative restore - Authoritatively restore the DIT database

``Change Service Account %s1 %s2 - Change AD DS/LDS Service Account to``

``username %s1 and password %s2.``

``Use "NULL" for blank password, \* to``

enter password from the console.

Configurable Settings - Manage configurable settings

DS Behavior - View and modify AD DS/LDS Behavior

Files - Manage AD DS/LDS database files

Group Membership Evaluation - Evaluate SIDs in token for a given user or

group

Help - Show this help information

IFM - IFM media creation

LDAP policies - Manage LDAP protocol policies

``LDAP Port %d - Configure LDAP Port for an AD LDS Instance.``

List Instances - List all AD LDS instances installed

on this machine.

Local Roles - Local RODC roles management

Metadata cleanup - Clean up objects of decommissioned servers

Partition management - Manage directory partitions

Popups off - Disable popups

Popups on - Enable popups

Quit - Quit the utility

Roles - Manage NTDS role owner tokens

Security account management - Manage Security Account Database - Duplicate

SID Cleanup

Semantic database analysis - Semantic Checker

Set DSRM Password - Reset directory service restore mode

administrator account password

Snapshot - Snapshot management

``SSL Port %d - Configure SSL Port for an AD LDS Instance.``

``\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*-------------------------\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*``

ntdsutil

ntdsutil: ?

? - Show this help information

``Activate Instance %s - Set "NTDS" or a specific AD LDS instance``

as the active instance.

Authoritative restore - Authoritatively restore the DIT database

``Change Service Account %s1 %s2 - Change AD DS/LDS Service Account to``

``username %s1 and password %s2.``

``Use "NULL" for blank password, \* to``

enter password from the console.

Configurable Settings - Manage configurable settings

DS Behavior - View and modify AD DS/LDS Behavior

Files - Manage AD DS/LDS database files

Group Membership Evaluation - Evaluate SIDs in token for a given user or

group

Help - Show this help information

IFM - IFM media creation

LDAP policies - Manage LDAP protocol policies

``LDAP Port %d - Configure LDAP Port for an AD LDS Instance.``

List Instances - List all AD LDS instances installed

on this machine.

Local Roles - Local RODC roles management

Metadata cleanup - Clean up objects of decommissioned servers

Partition management - Manage directory partitions

Popups off - Disable popups

Popups on - Enable popups

Quit - Quit the utility

Roles - Manage NTDS role owner tokens

Security account management - Manage Security Account Database - Duplicate

SID Cleanup

Semantic database analysis - Semantic Checker

Set DSRM Password - Reset directory service restore mode

administrator account password

Snapshot - Snapshot management

``SSL Port %d - Configure SSL Port for an AD LDS Instance.``

ntdsutil:

#### dnscmd.exe {#h.lpv0kdomhmpd" id="h.lpv0kdomhmpd

``C:\Windows\System32>dnscmd /?``

``Usage: DnsCmd \<ServerName> \<Command> \[\<Command Parameters>]``

``\<ServerName>:``

IP address or host name -- remote or local DNS server

. -- DNS server on local machine

``\<Command>:``

/Info -- Get server information

/Config -- Reset server or zone configuration

/EnumZones -- Enumerate zones

/Statistics -- Query/clear server statistics data

/ClearCache -- Clear DNS server cache

/WriteBackFiles -- Write back all zone or root-hint datafile(s)

/StartScavenging -- Initiates server scavenging

/IpValidate -- Validate remote DNS servers

/ResetListenAddresses -- Set server IP address(es) to serve DNS requests

/ResetForwarders -- Set DNS servers to forward recursive queries to

/ZoneInfo -- View zone information

/ZoneAdd -- Create a new zone on the DNS server

/ZoneDelete -- Delete a zone from DNS server or DS

/ZonePause -- Pause a zone

/ZoneResume -- Resume a zone

/ZoneReload -- Reload zone from its database (file or DS)

/ZoneWriteBack -- Write back zone to file

/ZoneRefresh -- Force refresh of secondary zone from master

/ZoneUpdateFromDs -- Update a DS integrated zone by data from DS

/ZonePrint -- Display all records in the zone

/ZoneResetType -- Change zone type

``/ZoneResetSecondaries -- Reset secondary\notify information for a zone``

/ZoneResetScavengeServers -- Reset scavenging servers for a zone

/ZoneResetMasters -- Reset secondary zone's master servers

/ZoneExport -- Export a zone to file

/ZoneChangeDirectoryPartition -- Move a zone to another directory partition

/TrustAnchorsResetType -- Change zone type for a trust anchor zone

/EnumRecords -- Enumerate records at a name

/RecordAdd -- Create a record in zone or RootHints

/RecordDelete -- Delete a record from zone, RootHints or cache

/NodeDelete -- Delete all records at a name

/AgeAllRecords -- Force aging on node(s) in zone

/TrustAnchorAdd -- Create a new trust anchor zone on the DNS server

/TrustAnchorDelete -- Delete a trust anchor zone from DNS server or DS

/EnumTrustAnchors -- Enumerate records at a name

/EnumDirectoryPartitions -- Enumerate directory partitions

/DirectoryPartitionInfo -- Get info on a directory partition

/CreateDirectoryPartition -- Create a directory partition

/DeleteDirectoryPartition -- Delete a directory partition

/EnlistDirectoryPartition -- Add DNS server to partition replication scope

/UnenlistDirectoryPartition -- Remove DNS server from replication scope

/CreateBuiltinDirectoryPartitions -- Create built-in partitions

/ExportSettings -- Output settings to DnsSettings.txt in the DNS server database directory

/OfflineSign -- Offline signing zone files, including key generation/deletion

``\<Command Parameters>:``

``DnsCmd \<CommandName> /? -- For help info on specific Command``

``C:\Windows\System32>``

``C:\Windows\System32>dnscmd /offlinesign /?``

To see usage for generating a self-signed certificate with private key:

DnsCmd /OfflineSign /GenKey

To see usage for deleting a self-signed certificate together with the key

that was generated by this tool:

DnsCmd /OfflineSign /DeleteKey

To see usage for signing a zone file:

DnsCmd /OfflineSign /SignZone

To see usage for importing a key from BIND private key file:

DnsCmd /OfflineSign /ImportKey

``C:\Windows\System32>dnscmd /exportsettings /?``

. completed successfully.

``C:\Windows\System32>dnscmd /zoneexport /?``

``Usage: DnsCmd \<ServerName> /ZoneExport \<ZoneName> \<ZoneExportFile>``

``\<ZoneName> -- FQDN of zone to export``

/Cache to export cache

``C:\Windows\System32>``

``C:\Windows\System32>dnscmd /info /?``

``Usage: DnsCmd \<Server> /Info \[\<Property>]``

``\<Property> -- server property to view``

Examples:

BootMethod

RpcProtocol

LogLevel

EventlogLevel

NoRecursion

ForwardDelegations

ForwardingTimeout

IsSlave

SecureResponses

RecursionRetry

RecursionTimeout

AdditionalRecursionTimeout

MaxCacheTtl

MaxNegativeCacheTtl

RoundRobin

LocalNetPriority

AddressAnswerLimit

BindSecondaries

WriteAuthorityNs

NameCheckFlag

StrictFileParsing

UpdateOptions

DisableAutoReverseZones

SendPort

XfrConnectTimeout

DsPollingInterval

ScavengingInterval

DefaultAgingState

DefaultNoRefreshInterval

DefaultRefreshInterval

``C:\Windows\System32>``

#### mstsc.exe {#h.nvr31pgwbc45" id="h.nvr31pgwbc45

Remote Desktop Connection

``%windir%\system32\mstsc.exe``

Remote Desktop Connection Usage

MSTSC \[\<connection file>] \[/v:\<server\[:port]> \[/admin] \[/f\[ullscreen]] \[/w:\<width> /h:\<height>] /public | \[/span] \[/multimon] \[/migrate] \[/edit “connection file”]

“connection file” -- Specifies the name of an .RDP file for the connection.

``/v:\<server\[:port]> -- Specifies the remote computer to which you want to connect.``

/admin -- Connects you to the session for administering a server.

/f -- Starts Remote Desktop in full-screen mode.

``/w:\<width> -- Specifies the width of the Remote Desktop window.``

``/h:\<height> -- Specifies the height of the Remote Desktop window.``

/public -- Runs Remote Desktop in public mode.

/span -- Matches the remote desktop width and height with the local virtual desktop, spanning across multiple monitors, if necessary. To span across monitors, the monitors must be arranged to form a rectangle.

/multimon -- Configures the Remote Desktop Services session monitor layout to be identical to the current client-side configuration.

/edit -- Opens the specified .RDP connection file for editing.

/migrate -- Migrates legacy connection files that were created with Client Connection Manager to new .RDP connection files.

#### wevtutil.exe {#h.3pl14weu2l32" id="h.3pl14weu2l32

``C:\\>wevtutil /?``

Windows Events Command Line Utility.

Enables you to retrieve information about event logs and publishers, install

and uninstall event manifests, run queries, and export, archive, and clear logs.

Usage:

You can use either the short (for example, ep /uni) or long (for example,

enum-publishers /unicode) version of the command and option names. Commands,

options and option values are not case-sensitive.

Variables are noted in all upper-case.

``wevtutil COMMAND \[ARGUMENT \[ARGUMENT] ...] \[/OPTION:VALUE \[/OPTION:VALUE] ...]``

Commands:

el | enum-logs List log names.

gl | get-log Get log configuration information.

sl | set-log Modify configuration of a log.

ep | enum-publishers List event publishers.

gp | get-publisher Get publisher configuration information.

im | install-manifest Install event publishers and logs from manifest.

um | uninstall-manifest Uninstall event publishers and logs from manifest.

qe | query-events Query events from a log or log file.

gli | get-log-info Get log status information.

epl | export-log Export a log.

al | archive-log Archive an exported log.

cl | clear-log Clear a log.

Common options:

/{r | remote}:VALUE

If specified, run the command on a remote computer. VALUE is the remote computer

name. Options /im and /um do not support remote operations.

/{u | username}:VALUE

Specify a different user to log on to the remote computer. VALUE is a user name

``in the form domain\user or user. Only applicable when option /r is specified.``

/{p | password}:VALUE

``Password for the specified user. If not specified, or if VALUE is "\*", the user``

will be prompted to enter a password. Only applicable when the /u option is

specified.

/{a | authentication}:\[Default|Negotiate|Kerberos|NTLM]

Authentication type for connecting to remote computer. The default is Negotiate.

/{uni | unicode}:\[true|false]

Display output in Unicode. If true, then output is in Unicode.

To learn more about a specific command, type the following:

wevtutil COMMAND /?

``C:\\>``

#### eventcreate.exe {#h.9kwnw88tei32" id="h.9kwnw88tei32

``C:\\>eventcreate /?``

``EVENTCREATE \[/S system \[/U username \[/P \[password]]]] /ID eventid``

``\[/L logname] \[/SO srcname] /T type /D description``

Description:

This command line tool enables an administrator to create

a custom event ID and message in a specified event log.

Parameter List:

/S system Specifies the remote system to connect to.

``/U \[domain\\]user Specifies the user context under which``

the command should execute.

``/P \[password] Specifies the password for the given``

user context. Prompts for input if omitted.

/L logname Specifies the event log to create

an event in.

/T type Specifies the type of event to create.

Valid types: SUCCESS, ERROR, WARNING, INFORMATION.

/SO source Specifies the source to use for the

event (if not specified, source will default

to 'eventcreate'). A valid source can be any

string and should represent the application

or component that is generating the event.

/ID id Specifies the event ID for the event. A

valid custom message ID is in the range

of 1 - 1000.

/D description Specifies the description text for the new event.

/? Displays this help message.

Examples:

EVENTCREATE /T ERROR /ID 1000

/L APPLICATION /D "My custom error event for the application log"

EVENTCREATE /T ERROR /ID 999 /L APPLICATION

/SO WinWord /D "Winword event 999 happened due to low diskspace"

EVENTCREATE /S system /T ERROR /ID 100

/L APPLICATION /D "Custom job failed to install"

EVENTCREATE /S system /U user /P password /ID 1 /T ERROR

/L APPLICATION /D "User access failed due to invalid user credentials"

``C:\\>``

#### WMIC {#h.di0atv7puoor" id="h.di0atv7puoor

``C:\\>wmic.exe /?``

``\[global switches] \<command>``

The following global switches are available:

/NAMESPACE Path for the namespace the alias operate against.

/ROLE Path for the role containing the alias definitions.

/NODE Servers the alias will operate against.

/IMPLEVEL Client impersonation level.

/AUTHLEVEL Client authentication level.

/LOCALE Language id the client should use.

/PRIVILEGES Enable or disable all privileges.

/TRACE Outputs debugging information to stderr.

/RECORD Logs all input commands and output.

/INTERACTIVE Sets or resets the interactive mode.

/FAILFAST Sets or resets the FailFast mode.

/USER User to be used during the session.

/PASSWORD Password to be used for session login.

/OUTPUT Specifies the mode for output redirection.

/APPEND Specifies the mode for output redirection.

/AGGREGATE Sets or resets aggregate mode.

``/AUTHORITY Specifies the \<authority type> for the connection.``

/?\[:\<BRIEF|FULL>] Usage information.

For more information on a specific global switch, type: switch-name /?

The following alias/es are available in the current role:

ALIAS - Access to the aliases available on the local system

BASEBOARD - Base board (also known as a motherboard or system board) management.

BIOS - Basic input/output services (BIOS) management.

BOOTCONFIG - Boot configuration management.

CDROM - CD-ROM management.

COMPUTERSYSTEM - Computer system management.

CPU - CPU management.

CSPRODUCT - Computer system product information from SMBIOS.

DATAFILE - DataFile Management.

DCOMAPP - DCOM Application management.

DESKTOP - User's Desktop management.

DESKTOPMONITOR - Desktop Monitor management.

DEVICEMEMORYADDRESS - Device memory addresses management.

DISKDRIVE - Physical disk drive management.

DISKQUOTA - Disk space usage for NTFS volumes.

DMACHANNEL - Direct memory access (DMA) channel management.

ENVIRONMENT - System environment settings management.

FSDIR - Filesystem directory entry management.

GROUP - Group account management.

IDECONTROLLER - IDE Controller management.

IRQ - Interrupt request line (IRQ) management.

JOB - Provides access to the jobs scheduled using the schedule service.

LOADORDER - Management of system services that define execution dependencies.

LOGICALDISK - Local storage device management.

LOGON - LOGON Sessions.

MEMCACHE - Cache memory management.

MEMORYCHIP - Memory chip information.

MEMPHYSICAL - Computer system's physical memory management.

NETCLIENT - Network Client management.

NETLOGIN - Network login information (of a particular user) management.

NETPROTOCOL - Protocols (and their network characteristics) management.

NETUSE - Active network connection management.

NIC - Network Interface Controller (NIC) management.

NICCONFIG - Network adapter management.

NTDOMAIN - NT Domain management.

NTEVENT - Entries in the NT Event Log.

NTEVENTLOG - NT eventlog file management.

ONBOARDDEVICE - Management of common adapter devices built into the motherboard (system board).

OS - Installed Operating System/s management.

PAGEFILE - Virtual memory file swapping management.

PAGEFILESET - Page file settings management.

PARTITION - Management of partitioned areas of a physical disk.

PORT - I/O port management.

PORTCONNECTOR - Physical connection ports management.

PRINTER - Printer device management.

PRINTERCONFIG - Printer device configuration management.

PRINTJOB - Print job management.

PROCESS - Process management.

PRODUCT - Installation package task management.

QFE - Quick Fix Engineering.

QUOTASETTING - Setting information for disk quotas on a volume.

RDACCOUNT - Remote Desktop connection permission management.

RDNIC - Remote Desktop connection management on a specific network adapter.

RDPERMISSIONS - Permissions to a specific Remote Desktop connection.

RDTOGGLE - Turning Remote Desktop listener on or off remotely.

RECOVEROS - Information that will be gathered from memory when the operating system fails.

REGISTRY - Computer system registry management.

SCSICONTROLLER - SCSI Controller management.

SERVER - Server information management.

SERVICE - Service application management.

SHADOWCOPY - Shadow copy management.

SHADOWSTORAGE - Shadow copy storage area management.

SHARE - Shared resource management.

SOFTWAREELEMENT - Management of the elements of a software product installed on a system.

SOFTWAREFEATURE - Management of software product subsets of SoftwareElement.

SOUNDDEV - Sound Device management.

STARTUP - Management of commands that run automatically when users log onto the computer system.

SYSACCOUNT - System account management.

SYSDRIVER - Management of the system driver for a base service.

SYSTEMENCLOSURE - Physical system enclosure management.

SYSTEMSLOT - Management of physical connection points including ports, slots and peripherals, and proprie

tary connections points.

TAPEDRIVE - Tape drive management.

TEMPERATURE - Data management of a temperature sensor (electronic thermometer).

TIMEZONE - Time zone data management.

UPS - Uninterruptible power supply (UPS) management.

USERACCOUNT - User account management.

VOLTAGE - Voltage sensor (electronic voltmeter) data management.

VOLUME - Local storage volume management.

VOLUMEQUOTASETTING - Associates the disk quota setting with a specific disk volume.

VOLUMEUSERQUOTA - Per user storage volume quota management.

WMISET - WMI service operational parameters management.

For more information on a specific alias, type: alias /?

CLASS - Escapes to full WMI schema.

PATH - Escapes to full WMI object paths.

CONTEXT - Displays the state of all the global switches.

QUIT/EXIT - Exits the program.

For more information on CLASS/PATH/CONTEXT, type: (CLASS | PATH | CONTEXT) /?

``C:\\>``

#### arp.exe {#h.48bo45mhu8d0" id="h.48bo45mhu8d0

``C:\\>arp -?``

Displays and modifies the IP-to-Physical address translation tables used by

address resolution protocol (ARP).

``ARP -s inet\_addr eth\_addr \[if\_addr]``

``ARP -d inet\_addr \[if\_addr]``

``ARP -a \[inet\_addr] \[-N if\_addr] \[-v]``

``\-a Displays current ARP entries by interrogating the current``

``protocol data. If inet\_addr is specified, the IP and Physical``

addresses for only the specified computer are displayed. If

more than one network interface uses ARP, entries for each ARP

table are displayed.

``\-g Same as -a.``

``\-v Displays current ARP entries in verbose mode. All invalid``

entries and entries on the loop-back interface will be shown.

``inet\_addr Specifies an internet address.``

``\-N if\_addr Displays the ARP entries for the network interface specified``

``by if\_addr.``

``\-d Deletes the host specified by inet\_addr. inet\_addr may be``

``wildcarded with \* to delete all hosts.``

``\-s Adds the host and associates the Internet address inet\_addr``

``with the Physical address eth\_addr. The Physical address is``

given as 6 hexadecimal bytes separated by hyphens. The entry

is permanent.

``eth\_addr Specifies a physical address.``

``if\_addr If present, this specifies the Internet address of the``

interface whose address translation table should be modified.

If not present, the first applicable interface will be used.

Example:

``\> arp -s 157.55.85.212 00-aa-00-62-c6-09 .... Adds a static entry.``

``\> arp -a .... Displays the arp table.``

#### nbtstat.exe {#h.7cusilarkcdi" id="h.7cusilarkcdi

``C:\\>nbtstat /?``

Displays protocol statistics and current TCP/IP connections using NBT

(NetBIOS over TCP/IP).

``NBTSTAT \[ \[-a RemoteName] \[-A IP address] \[-c] \[-n]``

``\[-r] \[-R] \[-RR] \[-s] \[-S] \[interval] ]``

``\-a (adapter status) Lists the remote machine's name table given its name``

``\-A (Adapter status) Lists the remote machine's name table given its``

IP address.

``\-c (cache) Lists NBT's cache of remote \[machine] names and their IP addresses``

``\-n (names) Lists local NetBIOS names.``

``\-r (resolved) Lists names resolved by broadcast and via WINS``

``\-R (Reload) Purges and reloads the remote cache name table``

``\-S (Sessions) Lists sessions table with the destination IP addresses``

``\-s (sessions) Lists sessions table converting destination IP``

addresses to computer NETBIOS names.

``\-RR (ReleaseRefresh) Sends Name Release packets to WINS and then, starts Refresh``

RemoteName Remote host machine name.

IP address Dotted decimal representation of the IP address.

interval Redisplays selected statistics, pausing interval seconds

between each display. Press Ctrl+C to stop redisplaying

statistics.

#### netstat.exe {#h.bdmftey7iug2" id="h.bdmftey7iug2

``C:\\>netstat -?``

Displays protocol statistics and current TCP/IP network connections.

``NETSTAT \[-a] \[-b] \[-e] \[-f] \[-n] \[-o] \[-p proto] \[-r] \[-s] \[-t] \[interval]``

``\-a Displays all connections and listening ports.``

``\-b Displays the executable involved in creating each connection or``

listening port. In some cases well-known executables host

multiple independent components, and in these cases the

sequence of components involved in creating the connection

or listening port is displayed. In this case the executable

``name is in \[] at the bottom, on top is the component it called,``

and so forth until TCP/IP was reached. Note that this option

can be time-consuming and will fail unless you have sufficient

permissions.

``\-e Displays Ethernet statistics. This may be combined with the -s``

option.

``\-f Displays Fully Qualified Domain Names (FQDN) for foreign``

addresses.

``\-n Displays addresses and port numbers in numerical form.``

``\-o Displays the owning process ID associated with each connection.``

``\-p proto Shows connections for the protocol specified by proto; proto``

may be any of: TCP, UDP, TCPv6, or UDPv6. If used with the -s

option to display per-protocol statistics, proto may be any of:

IP, IPv6, ICMP, ICMPv6, TCP, TCPv6, UDP, or UDPv6.

``\-r Displays the routing table.``

``\-s Displays per-protocol statistics. By default, statistics are``

shown for IP, IPv6, ICMP, ICMPv6, TCP, TCPv6, UDP, and UDPv6;

the -p option may be used to specify a subset of the default.

``\-t Displays the current connection offload state.``

interval Redisplays selected statistics, pausing interval seconds

between each display. Press CTRL+C to stop redisplaying

statistics. If omitted, netstat will print the current

configuration information once.

#### nslookup.exe {#h.4h3lycmpdf0p" id="h.4h3lycmpdf0p

``C:\\>nslookup /?``

Usage:

``nslookup \[-opt ...] # interactive mode using default server``

``nslookup \[-opt ...] - server # interactive mode using 'server'``

``nslookup \[-opt ...] host # just look up 'host' using default server``

``nslookup \[-opt ...] host server # just look up 'host' using 'server'``

#### ping.exe {#h.u0s7oy6qolo2" id="h.u0s7oy6qolo2

``C:\\>ping -?``

``Usage: ping \[-t] \[-a] \[-n count] \[-l size] \[-f] \[-i TTL] \[-v TOS]``

\[-r count] \[-s count] \[\[-j host-list] | \[-k host-list]]

``\[-w timeout] \[-R] \[-S srcaddr] \[-4] \[-6] target\_name``

Options:

``\-t Ping the specified host until stopped.``

To see statistics and continue - type Control-Break;

To stop - type Control-C.

``\-a Resolve addresses to hostnames.``

``\-n count Number of echo requests to send.``

``\-l size Send buffer size.``

``\-f Set Don't Fragment flag in packet (IPv4-only).``

``\-i TTL Time To Live.``

``\-v TOS Type Of Service (IPv4-only. This setting has been deprecated``

and has no effect on the type of service field in the IP Header).

``\-r count Record route for count hops (IPv4-only).``

``\-s count Timestamp for count hops (IPv4-only).``

``\-j host-list Loose source route along host-list (IPv4-only).``

``\-k host-list Strict source route along host-list (IPv4-only).``

``\-w timeout Timeout in milliseconds to wait for each reply.``

``\-R Use routing header to test reverse route also (IPv6-only).``

``\-S srcaddr Source address to use.``

``\-4 Force using IPv4.``

``\-6 Force using IPv6.``

#### pathping.exe {#h.973uehfsh5gg" id="h.973uehfsh5gg

``C:\\>pathping -?``

``Usage: pathping \[-g host-list] \[-h maximum\_hops] \[-i address] \[-n]``

``\[-p period] \[-q num\_queries] \[-w timeout]``

``\[-4] \[-6] target\_name``

Options:

``\-g host-list Loose source route along host-list.``

``\-h maximum\_hops Maximum number of hops to search for target.``

``\-i address Use the specified source address.``

``\-n Do not resolve addresses to hostnames.``

``\-p period Wait period milliseconds between pings.``

``\-q num\_queries Number of queries per hop.``

``\-w timeout Wait timeout milliseconds for each reply.``

``\-4 Force using IPv4.``

``\-6 Force using IPv6.``

#### route.exe {#h.93xd9wgptoyw" id="h.93xd9wgptoyw

``C:\\>route.exe -?``

Manipulates network routing tables.

ROUTE \[-f] \[-p] \[-4|-6] command \[destination]

``\[MASK netmask] \[gateway] \[METRIC metric] \[IF interface]``

``\-f Clears the routing tables of all gateway entries. If this is``

used in conjunction with one of the commands, the tables are

cleared prior to running the command.

``\-p When used with the ADD command, makes a route persistent across``

boots of the system. By default, routes are not preserved

when the system is restarted. Ignored for all other commands,

which always affect the appropriate persistent routes. This

option is not supported in Windows 95.

``\-4 Force using IPv4.``

``\-6 Force using IPv6.``

command One of these:

PRINT Prints a route

ADD Adds a route

DELETE Deletes a route

CHANGE Modifies an existing route

destination Specifies the host.

MASK Specifies that the next parameter is the 'netmask' value.

netmask Specifies a subnet mask value for this route entry.

If not specified, it defaults to 255.255.255.255.

gateway Specifies gateway.

interface the interface number for the specified route.

METRIC specifies the metric, ie. cost for the destination.

All symbolic names used for destination are looked up in the network database

file NETWORKS. The symbolic names for gateway are looked up in the host name

database file HOSTS.

If the command is PRINT or DELETE. Destination or gateway can be a wildcard,

``(wildcard is specified as a star '\*'), or the gateway argument may be omitted.``

``If Dest contains a \* or ?, it is treated as a shell pattern, and only``

``matching destination routes are printed. The '\*' matches any string,``

``and '?' matches any one char. Examples: 157.\*.1, 157.\*, 127.\*, \*224\*.``

Pattern match is only allowed in PRINT command.

Diagnostic Notes:

Invalid MASK generates an error, that is when (DEST & MASK) != DEST.

Example> route ADD 157.0.0.0 MASK 155.0.0.0 157.55.80.1 IF 1

The route addition failed: The specified mask parameter is invalid. (Destination & Mask) != Destination.

Examples:

``\> route PRINT``

``\> route PRINT -4``

``\> route PRINT -6``

``\> route PRINT 157\* .... Only prints those matching 157\*``

``\> route ADD 157.0.0.0 MASK 255.0.0.0 157.55.80.1 METRIC 3 IF 2``

destination^ ^mask ^gateway metric^ ^

Interface^

If IF is not given, it tries to find the best interface for a given

gateway.

``\> route ADD 3ffe::/32 3ffe::1``

``\> route CHANGE 157.0.0.0 MASK 255.0.0.0 157.55.80.5 METRIC 2 IF 2``

CHANGE is used to modify gateway and/or metric only.

``\> route DELETE 157.0.0.0``

``\> route DELETE 3ffe::/32``

#### tracert.exe {#h.qxnx8bxafrv9" id="h.qxnx8bxafrv9

``C:\\>tracert.exe -?``

``Usage: tracert \[-d] \[-h maximum\_hops] \[-j host-list] \[-w timeout]``

``\[-R] \[-S srcaddr] \[-4] \[-6] target\_name``

Options:

``\-d Do not resolve addresses to hostnames.``

``\-h maximum\_hops Maximum number of hops to search for target.``

``\-j host-list Loose source route along host-list (IPv4-only).``

``\-w timeout Wait timeout milliseconds for each reply.``

``\-R Trace round-trip path (IPv6-only).``

``\-S srcaddr Source address to use (IPv6-only).``

``\-4 Force using IPv4.``

``\-6 Force using IPv6.``

#### hostname {#h.98fm7mpngwo3" id="h.98fm7mpngwo3

``C:\\>hostname -?``

Prints the name of the current host.

hostname

#### whoami {#h.tiha9jcuzq6m" id="h.tiha9jcuzq6m

``C:\\>whoami -?``

WhoAmI has three ways of working:

Syntax 1:

WHOAMI \[/UPN | /FQDN | /LOGONID]

Syntax 2:

``WHOAMI { \[/USER] \[/GROUPS] \[/PRIV] } \[/FO format] \[/NH]``

Syntax 3:

``WHOAMI /ALL \[/FO format] \[/NH]``

Description:

This utility can be used to get user name and group information

along with the respective security identifiers (SID), privileges,

logon identifier (logon ID) for the current user (access token)

on the local system. i.e. who is the current logged on user?

If no switch is specified, tool displays the user name in NTLM

``format (domain\username).``

Parameter List:

/UPN Displays the user name in User Principal

Name (UPN) format.

/FQDN Displays the user name in Fully Qualified

Distinguished Name (FQDN) format.

/USER Displays information on the current user

along with the security identifier (SID).

/GROUPS Displays group membership for current user,

type of account, security identifiers (SID)

and attributes.

/PRIV Displays security privileges of the current

user.

/LOGONID Displays the logon ID of the current user.

/ALL Displays the current user name, groups

belonged to along with the security

identifiers (SID) and privileges for the

current user access token.

/FO format Specifies the output format to be displayed.

Valid values are TABLE, LIST, CSV.

Column headings are not displayed with CSV

format. Default format is TABLE.

/NH Specifies that the column header should not

be displayed in the output. This is

valid only for TABLE and CSV formats.

/? Displays this help message.

Examples:

WHOAMI

WHOAMI /UPN

WHOAMI /FQDN

WHOAMI /LOGONID

WHOAMI /USER

WHOAMI /USER /FO LIST

WHOAMI /USER /FO CSV

WHOAMI /GROUPS

WHOAMI /GROUPS /FO CSV /NH

WHOAMI /PRIV

WHOAMI /PRIV /FO TABLE

WHOAMI /USER /GROUPS

WHOAMI /USER /GROUPS /PRIV

WHOAMI /ALL

WHOAMI /ALL /FO LIST

WHOAMI /ALL /FO CSV /NH

WHOAMI /?

``C:\\>``

#### nslookup.exe {#h.15mj2e40omqx" id="h.15mj2e40omqx

``C:\\>nslookup``

Default Server: appserver.medlinkmanagement.com

Address: 192.168.1.99

``\> ?``

``Commands: (identifiers are shown in uppercase, \[] means optional)``

NAME - print info about the host/domain NAME using default server

NAME1 NAME2 - as above, but use NAME2 as server

help or ? - print info on common commands

set OPTION - set an option

all - print options, current server and host

``\[no]debug - print debugging information``

``\[no]d2 - print exhaustive debugging information``

``\[no]defname - append domain name to each query``

``\[no]recurse - ask for recursive answer to query``

``\[no]search - use domain search list``

``\[no]vc - always use a virtual circuit``

domain=NAME - set default domain name to NAME

``srchlist=N1\[/N2/.../N6] - set domain to N1 and search list to N1,N2, etc.``

root=NAME - set root server to NAME

retry=X - set number of retries to X

timeout=X - set initial time-out interval to X seconds

type=X - set query type (ex. A,AAAA,A+AAAA,ANY,CNAME,MX,NS,PTR,SOA,SRV)

querytype=X - same as type

class=X - set query class (ex. IN (Internet), ANY)

``\[no]msxfr - use MS fast zone transfer``

ixfrver=X - current version to use in IXFR transfer request

server NAME - set default server to NAME, using current default server

lserver NAME - set default server to NAME, using initial server

root - set current default server to the root

``ls \[opt] DOMAIN \[> FILE] - list addresses in DOMAIN (optional: output to FILE)``

``\-a - list canonical names and aliases``

``\-d - list all records``

``\-t TYPE - list records of the given RFC record type (ex. A,CNAME,MX,NS,PTR etc.)``

view FILE - sort an 'ls' output file and view it with pg

exit - exit the program

``\>``

#### telnet.exe {#h.ijpbch98x73b" id="h.ijpbch98x73b

Welcome to Microsoft Telnet Client

Escape Character is 'CTRL+]'

Microsoft Telnet> ?

Commands may be abbreviated. Supported commands are:

c - close close current connection

d - display display operating parameters

``o - open hostname \[port] connect to hostname (default port 23).``

q - quit exit telnet

set - set set options (type 'set ?' for a list)

sen - send send strings to server

st - status print status information

u - unset unset options (type 'unset ?' for a list)

?/h - help print help information

?/h - help print help information

Microsoft Telnet> set ?

bsasdel Backspace will be sent as delete

crlf New line mode - Causes return key to send CR & LF

delasbs Delete will be sent as backspace

escape x x is an escape charater to enter telnet client prompt

localecho Turn on localecho.

logfile x x is current client log file

logging Turn on logging

mode x x is console or stream

ntlm Turn on NTLM authentication.

term x x is ansi, vt100, vt52, or vtnt

Microsoft Telnet>

Microsoft Telnet> d

Escape Character is 'CTRL+]'

Will auth(NTLM Authentication)

Local echo off

New line mode - Causes return key to send CR & LF

Current mode: Console

Will term type

Preferred term type is ANSI

Microsoft Telnet>

#### diskperf.exe {#h.r8a90dycvukd" id="h.r8a90dycvukd

``C:\\>diskperf -?``

DISKPERF=====================

Starts and stops system disk performance counters.

Used without the command switches, DISKPERF reports what disk

performance counters are enabled on the specified Windows 2000 computer.

Disk performance counters can be specified to report the

performance of the individual physical drives, or the individual

logical drives or storage volumes. Note that these two sets of

performance counters are measured independently. The user

has the option of enabling and disabling them independently

using the command line switches.

NOTE: This command can only be used to control remote

Windows 2000 systems. In newer systems, these performance counters

are automatically enabled.

DISKPERF \[-Y\[D|V] | -N\[D|V]] \[\\\computername]

``\-Y Sets the system to start all disk performance counters``

when the system is restarted.

``\-YD Enables the disk performance counters for physical drives.``

when the system is restarted.

``\-YV Enables the disk performance counters for logical drives``

or storage volumes when the system is restarted.

``\-N Sets the system to disable all disk performance counters``

when the system is restarted.

``\-ND Disables the disk performance counters for physical drives.``

``\-NV Disables the disk performance counters for logical drives.``

``\\\computername Is the name of the computer you want to``

see or set disk performance counter use.

The computer must be a Windows 2000 system.

NOTE: Disk performance counters are permanently enabled on

systems beyond Windows 2000.

``C:\\>``

#### schtasks.exe {#h.d48jkgkmc5mk" id="h.d48jkgkmc5mk

``C:\Windows\System32>schtasks /?``

``SCHTASKS /parameter \[arguments]``

Description:

Enables an administrator to create, delete, query, change, run and

end scheduled tasks on a local or remote system.

Parameter List:

/Create Creates a new scheduled task.

/Delete Deletes the scheduled task(s).

/Query Displays all scheduled tasks.

/Change Changes the properties of scheduled task.

/Run Runs the scheduled task on demand.

/End Stops the currently running scheduled task.

/ShowSid Shows the security identifier corresponding to a scheduled task name.

/? Displays this help message.

Examples:

SCHTASKS

SCHTASKS /?

SCHTASKS /Run /?

SCHTASKS /End /?

SCHTASKS /Create /?

SCHTASKS /Delete /?

SCHTASKS /Query /?

SCHTASKS /Change /?

SCHTASKS /ShowSid /?

``C:\Windows\System32>schtasks /Query /?``

``SCHTASKS /Query \[/S system \[/U username \[/P \[password]]]]``

\[/FO format | /XML \[xml\_type]] \[/NH] \[/V] \[/TN taskname] \[/?]

Description:

Enables an administrator to display the scheduled tasks on the

local or remote system.

Parameter List:

/S system Specifies the remote system to connect to.

/U username Specifies the user context under

which schtasks.exe should execute.

``/P \[password] Specifies the password for the given``

user context. Prompts for input if omitted.

/FO format Specifies the format for the output.

Valid values: TABLE, LIST, CSV.

/NH Specifies that the column header should not

be displayed in the output. This is

valid only for TABLE format.

/V Displays verbose task output.

/TN taskname Specifies the task name for which to

retrieve the information, else all of them.

``/XML \[xml\_type] Displays task definitions in XML format.``

``If xml\_type is ONE then the output will be one valid XML file.``

``If xml\_type is not present then the output will be``

the concatenation of all XML task definitions.

/? Displays this help message.

Examples:

SCHTASKS /Query

SCHTASKS /Query /?

SCHTASKS /Query /S system /U user /P password

SCHTASKS /Query /FO LIST /V /S system /U user /P password

SCHTASKS /Query /FO TABLE /NH /V

``C:\Windows\System32>schtasks /Create /?``

``SCHTASKS /Create \[/S system \[/U username \[/P \[password]]]]``

``\[/RU username \[/RP password]] /SC schedule \[/MO modifier] \[/D day]``

``\[/M months] \[/I idletime] /TN taskname /TR taskrun \[/ST starttime]``

\[/RI interval] \[ {/ET endtime | /DU duration} \[/K] \[/XML xmlfile] \[/V1]]

\[/SD startdate] \[/ED enddate] \[/IT | /NP] \[/Z] \[/F]

Description:

Enables an administrator to create scheduled tasks on a local or

remote system.

Parameter List:

/S system Specifies the remote system to connect to. If omitted

the system parameter defaults to the local system.

/U username Specifies the user context under which SchTasks.exe

should execute.

``/P \[password] Specifies the password for the given user context.``

Prompts for input if omitted.

/RU username Specifies the "run as" user account (user context)

under which the task runs. For the system account,

``valid values are "", "NT AUTHORITY\SYSTEM"``

or "SYSTEM".

``For v2 tasks, "NT AUTHORITY\LOCALSERVICE" and``

``"NT AUTHORITY\NETWORKSERVICE" are also available as well``

as the well known SIDs for all three.

``/RP \[password] Specifies the password for the "run as" user.``

To prompt for the password, the value must be either

``"\*" or none. This password is ignored for the``

system account. Must be combined with either /RU or

/XML switch.

/SC schedule Specifies the schedule frequency.

Valid schedule types: MINUTE, HOURLY, DAILY, WEEKLY,

MONTHLY, ONCE, ONSTART, ONLOGON, ONIDLE, ONEVENT.

/MO modifier Refines the schedule type to allow finer control over

schedule recurrence. Valid values are listed in the

"Modifiers" section below.

/D days Specifies the day of the week to run the task. Valid

values: MON, TUE, WED, THU, FRI, SAT, SUN and for

MONTHLY schedules 1 - 31 (days of the month).

``Wildcard "\*" specifies all days.``

/M months Specifies month(s) of the year. Defaults to the first

day of the month. Valid values: JAN, FEB, MAR, APR,

``MAY, JUN, JUL, AUG, SEP, OCT, NOV, DEC. Wildcard "\*"``

specifies all months.

/I idletime Specifies the amount of idle time to wait before

running a scheduled ONIDLE task.

Valid range: 1 - 999 minutes.

/TN taskname Specifies a name which uniquely

identifies this scheduled task.

/TR taskrun Specifies the path and file name of the program to be

run at the scheduled time.

``Example: C:\windows\system32\calc.exe``

/ST starttime Specifies the start time to run the task. The time

format is HH:mm (24 hour time) for example, 14:30 for

2:30 PM. Defaults to current time if /ST is not

specified. This option is required with /SC ONCE.

/RI interval Specifies the repetition interval in minutes. This is

not applicable for schedule types: MINUTE, HOURLY,

ONSTART, ONLOGON, ONIDLE, ONEVENT.

Valid range: 1 - 599940 minutes.

If either /ET or /DU is specified, then it defaults to

10 minutes.

/ET endtime Specifies the end time to run the task. The time format

is HH:mm (24 hour time) for example, 14:50 for 2:50 PM.

This is not applicable for schedule types: ONSTART,

ONLOGON, ONIDLE, ONEVENT.

/DU duration Specifies the duration to run the task. The time

format is HH:mm. This is not applicable with /ET and

for schedule types: ONSTART, ONLOGON, ONIDLE, ONEVENT.

For /V1 tasks, if /RI is specified, duration defaults

to 1 hour.

/K Terminates the task at the endtime or duration time.

This is not applicable for schedule types: ONSTART,

ONLOGON, ONIDLE, ONEVENT. Either /ET or /DU must be

specified.

/SD startdate Specifies the first date on which the task runs. The

format is mm/dd/yyyy. Defaults to the current

date. This is not applicable for schedule types: ONCE,

ONSTART, ONLOGON, ONIDLE, ONEVENT.

/ED enddate Specifies the last date when the task should run. The

format is mm/dd/yyyy. This is not applicable for

schedule types: ONCE, ONSTART, ONLOGON, ONIDLE, ONEVENT.

/EC ChannelName Specifies the event channel for OnEvent triggers.

/IT Enables the task to run interactively only if the /RU

user is currently logged on at the time the job runs.

This task runs only if the user is logged in.

/NP No password is stored. The task runs non-interactively

as the given user. Only local resources are available.

/Z Marks the task for deletion after its final run.

/XML xmlfile Creates a task from the task XML specified in a file.

Can be combined with /RU and /RP switches, or with /RP

alone, when task XML already contains the principal.

/V1 Creates a task visible to pre-Vista platforms.

Not compatible with /XML.

/F Forcefully creates the task and suppresses warnings if

the specified task already exists.

/RL level Sets the Run Level for the job. Valid values are

LIMITED and HIGHEST. The default is LIMITED.

/DELAY delaytime Specifies the wait time to delay the running of the

task after the trigger is fired. The time format is

mmmm:ss. This option is only valid for schedule types

ONSTART, ONLOGON, ONEVENT.

/? Displays this help message.

Modifiers: Valid values for the /MO switch per schedule type:

MINUTE: 1 - 1439 minutes.

HOURLY: 1 - 23 hours.

DAILY: 1 - 365 days.

WEEKLY: weeks 1 - 52.

ONCE: No modifiers.

ONSTART: No modifiers.

ONLOGON: No modifiers.

ONIDLE: No modifiers.

MONTHLY: 1 - 12, or

FIRST, SECOND, THIRD, FOURTH, LAST, LASTDAY.

ONEVENT: XPath event query string.

Examples:

``\==> Creates a scheduled task "doc" on the remote machine "ABC"``

which runs notepad.exe every hour under user "runasuser".

SCHTASKS /Create /S ABC /U user /P password /RU runasuser

/RP runaspassword /SC HOURLY /TN doc /TR notepad

``\==> Creates a scheduled task "accountant" on the remote machine``

"ABC" to run calc.exe every five minutes from the specified

start time to end time between the start date and end date.

``SCHTASKS /Create /S ABC /U domain\user /P password /SC MINUTE``

/MO 5 /TN accountant /TR calc.exe /ST 12:00 /ET 14:00

/SD 06/06/2006 /ED 06/06/2006 /RU runasuser /RP userpassword

``\==> Creates a scheduled task "gametime" to run freecell on the``

first Sunday of every month.

SCHTASKS /Create /SC MONTHLY /MO first /D SUN /TN gametime

``/TR c:\windows\system32\freecell``

``\==> Creates a scheduled task "report" on remote machine "ABC"``

to run notepad.exe every week.

SCHTASKS /Create /S ABC /U user /P password /RU runasuser

/RP runaspassword /SC WEEKLY /TN report /TR notepad.exe

``\==> Creates a scheduled task "logtracker" on remote machine "ABC"``

to run notepad.exe every five minutes starting from the

specified start time with no end time. The /RP password will be

prompted for.

``SCHTASKS /Create /S ABC /U domain\user /P password /SC MINUTE``

/MO 5 /TN logtracker

``/TR c:\windows\system32\notepad.exe /ST 18:30``

/RU runasuser /RP

``\==> Creates a scheduled task "gaming" to run freecell.exe starting``

at 12:00 and automatically terminating at 14:00 hours every day

``SCHTASKS /Create /SC DAILY /TN gaming /TR c:\freecell /ST 12:00``

/ET 14:00 /K

``\==> Creates a scheduled task "EventLog" to run wevtvwr.msc starting``

whenever event 101 is published in the System channel

SCHTASKS /Create /TN EventLog /TR wevtvwr.msc /SC ONEVENT

``/EC System /MO \*\[System/EventID=101]``

``\==> Spaces in file paths can be used by using two sets of quotes, one``

set for CMD.EXE and one for SchTasks.exe. The outer quotes for CMD

need to be double quotes; the inner quotes can be single quotes or

escaped double quotes:

SCHTASKS /Create

``/tr "'c:\program files\internet explorer\iexplorer.exe'``

``\\"c:\log data\today.xml\\"" ...``

``C:\Windows\System32>``

#### SetX.exe {#h.gdu3xlo8yd9f" id="h.gdu3xlo8yd9f

``C:\Windows\System32>setx.exe /?``

SetX has three ways of working:

Syntax 1:

``SETX \[/S system \[/U \[domain\\]user \[/P \[password]]]] var value \[/M]``

Syntax 2:

``SETX \[/S system \[/U \[domain\\]user \[/P \[password]]]] var /K regpath \[/M]``

Syntax 3:

``SETX \[/S system \[/U \[domain\\]user \[/P \[password]]]]``

/F file {var {/A x,y | /R x,y string}\[/M] | /X} \[/D delimiters]

Description:

Creates or modifies environment variables in the user or system

environment. Can set variables based on arguments, regkeys or

file input.

Parameter List:

/S system Specifies the remote system to connect to.

``/U \[domain\\]user Specifies the user context under which``

the command should execute.

``/P \[password] Specifies the password for the given``

user context. Prompts for input if omitted.

var Specifies the environment variable to set.

value Specifies a value to be assigned to the

environment variable.

/K regpath Specifies that the variable is set based

on information from a registry key.

Path should be specified in the format of

``hive\key\\...\value. For example,``

``HKEY\_LOCAL\_MACHINE\System\CurrentControlSet\\``

``Control\TimeZoneInformation\StandardName.``

/F file Specifies the filename of the text file

to use.

/A x,y Specifies absolute file coordinates

(line X, item Y) as parameters to search

within the file.

/R x,y string Specifies relative file coordinates with

respect to "string" as the search parameters.

/M Specifies that the variable should be set in

``the system wide (HKEY\_LOCAL\_MACHINE)``

environment. The default is to set the

``variable under the HKEY\_CURRENT\_USER``

environment.

/X Displays file contents with x,y coordinates.

/D delimiters Specifies additional delimiters such as ","

``or "\\". The built-in delimiters are space,``

tab, carriage return, and linefeed. Any

ASCII character can be used as an additional

delimiter. The maximum number of delimiters,

including the built-in delimiters, is 15.

/? Displays this help message.

NOTE: 1) SETX writes variables to the master environment in the registry.

``2\) On a local system, variables created or modified by this tool``

will be available in future command windows but not in the

current CMD.exe command window.

``3\) On a remote system, variables created or modified by this tool``

will be available at the next logon session.

``4\) The valid Registry Key data types are REG\_DWORD, REG\_EXPAND\_SZ,``

``REG\_SZ, REG\_MULTI\_SZ.``

``5\) Supported hives: HKEY\_LOCAL\_MACHINE (HKLM),``

``HKEY\_CURRENT\_USER (HKCU).``

``6\) Delimiters are case sensitive.``

``7\) REG\_DWORD values are extracted from the registry in decimal``

format.

Examples:

`SETX MACHINE COMPAQ`

`SETX MACHINE "COMPAQ COMPUTER" /M`

``SETX MYPATH "%PATH%"``

``SETX MYPATH \~PATH\~``

`SETX /S system /U user /P password MACHINE COMPAQ`

``SETX /S system /U user /P password MYPATH ^%PATH^%``

``SETX TZONE /K HKEY\_LOCAL\_MACHINE\System\CurrentControlSet\\``

``Control\TimeZoneInformation\StandardName``

``SETX BUILD /K "HKEY\_LOCAL\_MACHINE\Software\Microsoft\Windows``

``NT\CurrentVersion\CurrentBuildNumber" /M``

``SETX /S system /U user /P password TZONE /K HKEY\_LOCAL\_MACHINE\\``

``System\CurrentControlSet\Control\TimeZoneInformation\\``

StandardName

`SETX /S system /U user /P password BUILD /K`

``"HKEY\_LOCAL\_MACHINE\Software\Microsoft\Windows NT\\``

``CurrentVersion\CurrentBuildNumber" /M``

`SETX /F ipconfig.out /X`

`SETX IPADDR /F ipconfig.out /A 5,11`

``SETX OCTET1 /F ipconfig.out /A 5,3 /D "#$\*."``

`SETX IPGATEWAY /F ipconfig.out /R 0,7 Gateway`

``SETX /S system /U user /P password /F c:\ipconfig.out /X``

``C:\Windows\System32>``

#### auditpol.exe {#h.4bvv3hc75hy2" id="h.4bvv3hc75hy2

``C:\Windows\System32>auditpol.exe /?``

``Usage: AuditPol command \[\<sub-command>\<options>]``

Commands (only one command permitted per execution)

/? Help (context-sensitive)

/get Displays the current audit policy.

/set Sets the audit policy.

/list Displays selectable policy elements.

/backup Saves the audit policy to a file.

/restore Restores the audit policy from a file.

/clear Clears the audit policy.

/remove Removes the per-user audit policy for a user account.

/resourceSACL Configure global resource SACLs

``Use AuditPol \<command> /? for details on each command``

``C:\Windows\System32>auditpol.exe /get /?``

Usage: AuditPol /get \[/user\[:\<username>|<{sid}>]]

\[/category:\*|\<name>|<{guid}>\[,:\<name>|<{guid}>...]]

\[/subcategory:\<name>|<{guid}>\[,:\<name>|<{guid}>...]]

``\[/option:\<option name>]``

``\[/sd]``

``\[/r]``

This command displays the current audit policy.

Commands

/? Help (context-sensitive)

/user The security principal for whom the per-user audit

policy is queried. Either the /category or /subcategory

option must be specified. The user may be specified as

a SID or name. If no user account is specified, then

the system audit policy is queried.

/category One or more audit categories specified by GUID or name.

``An asterisk ("\*") may be used to indicate that all audit``

categories should be queried.

/subcategory One or more audit subcategories specified by GUID or

name.

/sd Retrieves the security descriptor used to delegate

access to the audit policy.

/option Retrieve existing policy for CrashOnAuditFail,

FullPrivilegeAuditing, AuditBaseObjects or

AuditBaseDirectories.

/r Display the output in report (CSV) format.

Sample usage:

``auditpol /get /user:domain\user /Category:"Detailed Tracking","Object Access"``

auditpol /get /Subcategory:{0cce9212-69ae-11d9-bed3-505054503030} /r

auditpol /get /option:CrashOnAuditFail

auditpol /get /user:{S-1-5-21-397123417-1234567} /Category:"System"

auditpol /get /sd

``C:\Windows\System32>auditpol.exe /set /?``

Usage: AuditPol /set

\[/user\[:\<username>|<{sid}>]\[/include]\[/exclude]]

\[/category:\<name>|<{guid}>\[,:\<name>|<{guid}>...]]

\[/success:\<enable>|\<disable>]\[/failure:\<enable>|\<disable>]

\[/subcategory:\<name>|<{guid}>\[,:\<name>|<{guid}>...]]

\[/success:\<enable>|\<disable>]\[/failure:\<enable>|\<disable>]

\[/option:\<option name> /value:\<enable>|\<disable>]

This command sets the current audit policy.

Commands

/? Help (context-sensitive)

/user The security principal for whom per-user audit policy

specified by the category/subcategory is set. Either

the category or subcategory option must be specified,

as a SID or name.

/include Specified with /user; indicates that user's per-user

policy will cause audit to be generated even if not

specified by the system audit policy. This setting is

the default and is automatically applied if neither

the /include nor /exclude options are explicitly

specified.

/exclude Specified with /user; indicates that the user's per-user

policy will cause audit to be suppressed regardless of

the system audit policy. This setting is not honored for

users who are members of the Administrators local group.

/category One or more audit categories specified by GUID or name.

If no user is specified, the system policy is set.

/subcategory One or more audit subcategories specified by GUID or

name. If no user is specified, system policy is set.

/success Specifies success auditing. This setting is the default

and is automatically applied if neither the /success nor

/failure options are explicitly specified. This setting

must be used with a parameter indicating whether to

enable or disable the setting.

/failure Specifies failure auditing. This setting must be used with

a parameter indicating whether to enable or disable the

setting.

/option Set the audit policy for CrashOnAuditFail,

FullPrivilegeAuditing, AuditBaseObjects or

AuditBaseDirectories.

/sd Sets the security descriptor used to delegate access

to the audit policy. The security descriptor must be

specified using SDDL. The security descriptor must have a

DACL.

Example:

``auditpol /set /user:domain\user /Category:"System" /success:enable /include``

auditpol /set /subcategory:{0cce9212-69ae-11d9-bed3-505054503030} /failure:disable

auditpol /set /option:CrashOnAuditFail /value:enable

auditpol /set /sd:D:(A;;DCSWRPDTRC;;;BA)(A;;DCSWRPDTRC;;;SY)

The command was successfully executed.

``C:\Windows\System32>auditpol.exe /list /?``

Usage: AuditPol /list

\[/user|/category|/subcategory\[:\<categoryname>|<{guid}>|\*]

``\[/v] \[/r]``

This command lists audit policy categories, subcategories, or lists users for

whom per-user audit policy is defined.

Commands

/? Help (context-sensitive)

/user Retrieves all users for whom per-user audit policy

has been defined. If used with the /v option, the

sid of the user is also displayed.

/category Displays the names of categories understood by the

system. If used with the /v option, the category

GUID is also displayed.

/subcategory Displays the names of subcategories understood by the

system, for subcategories in a specified category.

The subcategory GUIDs are also displayed if the /v

option is used.

Example:

auditpol /list /user

auditpol /list /category /v

auditpol /list /subcategory:"Detailed Tracking","Object Access"

``C:\Windows\System32>Auditpol /list /subcategory:\*``

Category/Subcategory

System

Security State Change

Security System Extension

System Integrity

IPsec Driver

Other System Events

Logon/Logoff

Logon

Logoff

Account Lockout

IPsec Main Mode

IPsec Quick Mode

IPsec Extended Mode

Special Logon

Other Logon/Logoff Events

Network Policy Server

Object Access

File System

Registry

Kernel Object

SAM

Certification Services

Application Generated

Handle Manipulation

File Share

Filtering Platform Packet Drop

Filtering Platform Connection

Other Object Access Events

Detailed File Share

Privilege Use

Sensitive Privilege Use

Non Sensitive Privilege Use

Other Privilege Use Events

Detailed Tracking

Process Creation

Process Termination

DPAPI Activity

RPC Events

Policy Change

Audit Policy Change

Authentication Policy Change

Authorization Policy Change

MPSSVC Rule-Level Policy Change

Filtering Platform Policy Change

Other Policy Change Events

Account Management

User Account Management

Computer Account Management

Security Group Management

Distribution Group Management

Application Group Management

Other Account Management Events

DS Access

Directory Service Access

Directory Service Changes

Directory Service Replication

Detailed Directory Service Replication

Account Logon

Credential Validation

Kerberos Service Ticket Operations

Other Account Logon Events

Kerberos Authentication Service

``C:\Windows\System32>``

#### bitsadmin.exe {#h.lp81vy51i0ky" id="h.lp81vy51i0ky

``C:\Windows\System32>bitsadmin.exe /?``

``BITSADMIN version 3.0 \[ 7.5.7601 ]``

BITS administration utility.

(C) Copyright 2000-2006 Microsoft Corp.

BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.

Administrative tools for the BITS service are now provided by BITS PowerShell cmdlets.

USAGE: BITSADMIN \[/RAWRETURN] \[/WRAP | /NOWRAP] command

The following commands are available:

/HELP Prints this help

/? Prints this help

/UTIL /? Prints the list of utilities commands

/PEERCACHING /? Prints the list of commands to manage Peercaching

/CACHE /? Prints the list of cache management commands

/PEERS /? Prints the list of peer management commands

``/LIST \[/ALLUSERS] \[/VERBOSE] List the jobs``

``/MONITOR \[/ALLUSERS] \[/REFRESH sec] Monitors the copy manager``

``/RESET \[/ALLUSERS] Deletes all jobs in the manager``

``/TRANSFER \<job name> \[type] \[/PRIORITY priority] \[/ACLFLAGS flags]``

``remote\_url local\_name``

Transfers one of more files.

``\[type] may be /DOWNLOAD or /UPLOAD; default is download``

Multiple URL/file pairs may be specified.

``Unlike most commands, \<job name> may only be a name and not a GUID.``

``/CREATE \[type] \<job name> Creates a job``

``\[type] may be /DOWNLOAD, /UPLOAD, or /UPLOAD-REPLY; default is download``

``Unlike most commands, \<job name> may only be a name and not a GUID.``

``/INFO \<job> \[/VERBOSE] Displays information about the job``

``/ADDFILE \<job> \<remote\_url> \<local\_name> Adds a file to the job``

``/ADDFILESET \<job> \<textfile> Adds multiple files to the job``

``Each line of \<textfile> lists a file's remote name and local name, separated``

by spaces. A line beginning with '#' is treated as a comment.

Once the file set is read into memory, the contents are added to the job.

``/ADDFILEWITHRANGES \<job> \<remote\_url> \<local\_name range\_list>``

Like /ADDFILE, but BITS will read only selected byte ranges of the URL.

``range\_list is a comma-delimited series of offset and length pairs.``

For example,

0:100,2000:100,5000:eof

instructs BITS to read 100 bytes starting at offset zero, 100 bytes starting

at offset 2000, and the remainder of the URL starting at offset 5000.

``/REPLACEREMOTEPREFIX \<job> \<old\_prefix> \<new\_prefix>``

``All files whose URL begins with \<old\_prefix> are changed to use \<new\_prefix>``

Note that BITS currently supports HTTP/HTTPS downloads and uploads.

It also supports UNC paths and file:// paths as URLS

``/LISTFILES \<job> Lists the files in the job``

``/SUSPEND \<job> Suspends the job``

``/RESUME \<job> Resumes the job``

``/CANCEL \<job> Cancels the job``

``/COMPLETE \<job> Completes the job``

``/GETTYPE \<job> Retrieves the job type``

``/GETACLFLAGS \<job> Retrieves the ACL propagation flags``

``/SETACLFLAGS \<job> \<ACL\_flags> Sets the ACL propagation flags for the job``

O - OWNER G - GROUP

D - DACL S - SACL

Examples:

bitsadmin /setaclflags MyJob OGDS

bitsadmin /setaclflags MyJob OGD

``/GETBYTESTOTAL \<job> Retrieves the size of the job``

``/GETBYTESTRANSFERRED \<job> Retrieves the number of bytes transferred``

``/GETFILESTOTAL \<job> Retrieves the number of files in the job``

``/GETFILESTRANSFERRED \<job> Retrieves the number of files transferred``

``/GETCREATIONTIME \<job> Retrieves the job creation time``

``/GETMODIFICATIONTIME \<job> Retrieves the job modification time``

``/GETCOMPLETIONTIME \<job> Retrieves the job completion time``

``/GETSTATE \<job> Retrieves the job state``

``/GETERROR \<job> Retrieves detailed error information``

``/GETOWNER \<job> Retrieves the job owner``

``/GETDISPLAYNAME \<job> Retrieves the job display name``

``/SETDISPLAYNAME \<job> \<display\_name> Sets the job display name``

``/GETDESCRIPTION \<job> Retrieves the job description``

``/SETDESCRIPTION \<job> \<description> Sets the job description``

``/GETPRIORITY \<job> Retrieves the job priority``

``/SETPRIORITY \<job> \<priority> Sets the job priority``

Priority usage choices:

FOREGROUND

HIGH

NORMAL

LOW

``/GETNOTIFYFLAGS \<job> Retrieves the notify flags``

``/SETNOTIFYFLAGS \<job> \<notify\_flags> Sets the notify flags``

For more help on this option, please refer to the MSDN help page for SetNotifyFlags

``/GETNOTIFYINTERFACE \<job> Determines if notify interface is registered``

``/GETMINRETRYDELAY \<job> Retrieves the retry delay in seconds``

``/SETMINRETRYDELAY \<job> \<retry\_delay> Sets the retry delay in seconds``

``/GETNOPROGRESSTIMEOUT \<job> Retrieves the no progress timeout in seconds``

``/SETNOPROGRESSTIMEOUT \<job> \<timeout> Sets the no progress timeout in seconds``

``/GETMAXDOWNLOADTIME \<job> Retrieves the download timeout in seconds``

``/SETMAXDOWNLOADTIME \<job> \<timeout> Sets the download timeout in seconds``

``/GETERRORCOUNT \<job> Retrieves an error count for the job``

``/SETPROXYSETTINGS \<job> \<usage> Sets the proxy usage``

usage choices:

PRECONFIG - Use the owner's default Internet settings.

AUTODETECT - Force autodetection of proxy.

``NO\_PROXY - Do not use a proxy server.``

OVERRIDE - Use an explicit proxy list and bypass list.

Must be followed by a proxy list and a proxy bypass list.

NULL or "" may be used for an empty proxy bypass list.

Examples:

bitsadmin /setproxysettings MyJob PRECONFIG

bitsadmin /setproxysettings MyJob AUTODETECT

``bitsadmin /setproxysettings MyJob NO\_PROXY``

``bitsadmin /setproxysettings MyJob OVERRIDE proxy1:80 "\<local>"``

bitsadmin /setproxysettings MyJob OVERRIDE proxy1,proxy2,proxy3 NULL

``/GETPROXYUSAGE \<job> Retrieves the proxy usage setting``

``/GETPROXYLIST \<job> Retrieves the proxy list``

``/GETPROXYBYPASSLIST \<job> Retrieves the proxy bypass list``

``/TAKEOWNERSHIP \<job> Take ownership of the job``

``/SETNOTIFYCMDLINE \<job> \<program\_name> \[program\_parameters]``

Sets a program to execute for notification, and optionally parameters.

The program name and parameters can be NULL.

IMPORTANT: if parameters are non-NULL, then the program name should be the

first parameter.

Examples:

``bitsadmin /SetNotifyCmdLine MyJob c:\winnt\system32\notepad.exe NULL``

``bitsadmin /SetNotifyCmdLine MyJob c:\foo.exe "c:\foo.exe parm1 parm2"``

bitsadmin /SetNotifyCmdLine MyJob NULL NULL

``/GETNOTIFYCMDLINE \<job> Returns the job's notification command line``

``/SETCREDENTIALS \<job> \<target> \<scheme> \<username> \<password>``

Adds credentials to a job.

``\<target> may be either SERVER or PROXY``

``\<scheme> may be BASIC, DIGEST, NTLM, NEGOTIATE, or PASSPORT.``

``/REMOVECREDENTIALS \<job> \<target> \<scheme>``

Removes credentials from a job.

``/GETCUSTOMHEADERS \<job> Gets the Custom HTTP Headers``

``/SETCUSTOMHEADERS \<job> \<header1> \<header2> <...> Sets the Custom HTTP Headers``

``/GETCLIENTCERTIFICATE \<job> Gets the job's Client Certificate Information``

``/SETCLIENTCERTIFICATEBYID \<job> \<store\_location> \<store\_name> \<hexa-decimal\_cert\_id>``

Sets a client authentication certificate to a job.

``\<store\_location> may be``

``1(CURRENT\_USER), 2(LOCAL\_MACHINE), 3(CURRENT\_SERVICE),``

``4(SERVICES), 5(USERS), 6(CURRENT\_USER\_GROUP\_POLICY),``

``7(LOCAL\_MACHINE\_GROUP\_POLICY) or 8(LOCAL\_MACHINE\_ENTERPRISE).``

``/SETCLIENTCERTIFICATEBYNAME \<job> \<store\_location> \<store\_name> \<subject\_name>``

Sets a client authentication certificate to a job.

``\<store\_location> may be``

``1(CURRENT\_USER), 2(LOCAL\_MACHINE), 3(CURRENT\_SERVICE),``

``4(SERVICES), 5(USERS), 6(CURRENT\_USER\_GROUP\_POLICY),``

``7(LOCAL\_MACHINE\_GROUP\_POLICY) or 8(LOCAL\_MACHINE\_ENTERPRISE).``

``/REMOVECLIENTCERTIFICATE \<job> Removes the Client Certificate Information from the job``

``/SETSECURITYFLAGS \<job> \<value>``

Sets the HTTP security flags for URL redirection and checks performed on the server certificate during the transfer.

The value is an unsigned integer with the following interpretation for the bits in the binary representation.

Enable CRL Check : Set the least significant bit

Ignore invalid common name in server certificate : Set the 2nd bit from right

Ignore invalid date in server certificate : Set the 3rd bit from right

Ignore invalid certificate authority in server

certificate : Set the 4th bit from right

Ignore invalid usage of certificate : Set the 5th bit from right

Redirection policy : Controlled by the 9th-11th bits from right

0,0,0 - Redirects will be automatically allowed.

0,0,1 - Remote name in the IBackgroundCopyFile interface will be updated if a redirect occurs.

0,1,0 - BITS will fail the job if a redirect occurs.

Allow redirection from HTTPS to HTTP : Set the 12th bit from right

``/GETSECURITYFLAGS \<job>``

Reports the HTTP security flags for URL redirection and checks performed on the server certificate during the transfer.

/SETVALIDATIONSTATE \<job> \<file-index> \<true|false>

``\<file-index> starts from 0``

Sets the content-validation state of the given file within the job.

``/GETVALIDATIONSTATE \<job> \<file-index>``

``\<file-index> starts from 0``

Reports the content-validation state of the given file within the job.

``/GETTEMPORARYNAME \<job> \<file-index>``

``\<file-index> starts from 0``

Reports the temporary filename of the given file within the job.

The following options control peercaching of a particular job:

``/SETPEERCACHINGFLAGS \<job> \<value>``

Sets the flags for the job's peercaching behavior.

The value is an unsigned integer with the following interpretation for the bits in the binary representation.

Allow the job's data to be downloaded from a peer : Set the least significant bit

Allow the job's data to be served to peers : Set the 2nd bit from right

``/GETPEERCACHINGFLAGS \<job>``

Reports the flags for the job's peercaching behavior.

The following options are valid for UPLOAD-REPLY jobs only:

``/GETREPLYFILENAME \<job> Gets the path of the file containing the server reply``

``/SETREPLYFILENAME \<job> \<path> Sets the path of the file containing the server reply``

``/GETREPLYPROGRESS \<job> Gets the size and progress of the server reply``

``/GETREPLYDATA \<job> Dumps the server's reply data in hex format``

The following options can be placed before the command:

/RAWRETURN Return data more suitable for parsing

/WRAP Wrap output around console (default)

/NOWRAP Don't wrap output around console

The /RAWRETURN option strips new line characters and formatting.

``It is recognized by the /CREATE and /GET\* commands.``

``Commands that take a \<job> parameter will accept either a job name or a job ID``

GUID inside braces. BITSADMIN reports an error if a name is ambiguous.

``C:\Windows\System32>bitsadmin.exe /LIST``

``BITSADMIN version 3.0 \[ 7.5.7601 ]``

BITS administration utility.

(C) Copyright 2000-2006 Microsoft Corp.

BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.

Administrative tools for the BITS service are now provided by BITS PowerShell cmdlets.

Listed 0 job(s).

``C:\Windows\System32>bitsadmin.exe /UTIL /?``

``BITSADMIN version 3.0 \[ 7.5.7601 ]``

BITS administration utility.

(C) Copyright 2000-2006 Microsoft Corp.

BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.

Administrative tools for the BITS service are now provided by BITS PowerShell cmdlets.

The following UTIL commands are available:

``/UTIL /SETIEPROXY \<account> \<usage> \[/CONN \<connection name>]``

``Sets the Internet proxy settings for the \<account> system account.``

Settings are applied to the default network connection, unless

``\<connection name> is specified.``

account choices:

LOCALSYSTEM

NETWORKSERVICE

LOCALSERVICE

usage choices:

``NO\_PROXY - Specify direct connection (no proxy server).``

AUTODETECT - Turn on autodetection of proxy.

``MANUAL\_PROXY - Use an explicit proxy list and bypass list.``

Must be followed by a proxy list and a proxy bypass list.

NULL or "" may be used for an empty proxy bypass list.

AUTOSCRIPT - Specify a script to be executed during proxy auto discovery.

Must be followed by a script URL.

connection name indicates the network connection for which the new proxy

settings should be applied. If not specified, the default connection will

be used (usually the LAN connection). To get a list of possible connection

names, use /CONN /?.

Examples:

bitsadmin /util /setieproxy localsystem AUTODETECT

``bitsadmin /util /setieproxy networkservice NO\_PROXY``

``bitsadmin /util /setieproxy localsystem MANUAL\_PROXY proxy1:80 "\<local>"``

``bitsadmin /util /setieproxy localsystem MANUAL\_PROXY pxy1,pxy2,pxy3 NULL``

bitsadmin /util /setieproxy networkservice AUTOSCRIPT http://server/get.asp

``bitsadmin /util /setieproxy networkservice NO\_PROXY /CONN "XYZ Dialup"``

``/UTIL /GETIEPROXY \<account> \[/CONN \<connection name>]``

``Retrieves the Internet proxy settings for the \<account> system``

account. Settings refer to the default network connection, unless

``\<connection name> is specified.``

account choices:

LOCALSYSTEM

NETWORKSERVICE

LOCALSERVICE

connection name indicates the network connection for which the new proxy

settings should be applied. If not specified, the default connection

will be used (usually the LAN connection). To get a list of possible

connection names, use /CONN /?.

``/UTIL /VERSION \[/VERBOSE]``

Displays the version of BITS currently active on the system.

The switch /VERBOSE prints additional information useful for

troubleshooting purposes.

``/UTIL /REPAIRSERVICE \[/FORCE]``

Attempts to repair a malfunctioning BITS service by inspecting some of the

service configuration settings. The switch /FORCE indicates that the BITS

service should be deleted and re-created if repairing the settings does not

clear the errors in starting the BITS service. Use this command with caution

as it is not possible to revert the changes.

/UTIL /ENABLEANALYTICCHANNEL TRUE/FALSE

Enables/Disables the BITS Client Analytic channel

Note that for /SETIEPROXY, /ENABLEANALYTICCHANNEL, and /REPAIRSERVICE commands administrator privileges

are required.

``C:\Windows\System32>``

#### Get-BitsTransfer (PS) {#h.kugcnc7ckidb" id="h.kugcnc7ckidb

``PowerShell equivalent of BITSADMIN.\[2]``

Get-BitsTransfer -AllUsers | select -ExpandProperty FileList

#### printbrm.exe {#h.is4i98v4q2ae" id="h.is4i98v4q2ae

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

#### RegSvr32.exe {#h.qyybo8erkc2p" id="h.qyybo8erkc2p

``C:\Windows\System32\regsvr32.exe``

To register a module, you must provide a binary name.

``Usage: regsvr32 \[/u] \[/s] \[/n] \[/i\[:cmdline]] dllname``

/u - Unregister server

/s - Silent; display no message boxes

``/i - Call DllInstall passing it an optional \[cmdline]; when used with /u calls dll uninstall``

/n - do not call DllRegisterServer; this option must be used with /i

#### mmc.exe {#h.qnjsjazfhtq3" id="h.qnjsjazfhtq3

mmc path\filename.msc \[/a] \[/{64|32}]

path/filename Opens a saved console

/a Opens a saved console in author mode. Used to make changes to saved consoles. When consoles are opened with this option, they are opened in author mode, regardless of their default mode. This does not permanently change the default mode setting for files; when you omit this option, MMC opens console files according to their default mode settings. After you open MMC or a console file in author mode, you can open any existing console by clicking **Open** on the **Console** menu.

/64 Opens the 64-bit version of MMC (MMC64). Use this option only if you are running a Microsoft 64-bit operating system and want to use a 64-bit snap-in.

/32 Opens the 32-bit version of MMC (MMC32). When running a Microsoft 64-bit operating system, you can run 32-bit snap-ins by opening MMC with this command-line option when you have 32-bit only snap-ins.

#### Bcdboot.exe {#h.n0ys4lbhe2or" id="h.n0ys4lbhe2or

``C:\Windows\System32>bcdboot /?``

Bcdboot - Bcd boot file creation and repair tool.

The bcdboot.exe command-line tool is used to copy critical boot files to the

system partition and to create a new system BCD store.

``bcdboot \<source> \[/l \<locale>] \[/s \<volume-letter>] \[/v]``

``\[/m \[{OS Loader ID}]]``

source Specifies the location of the windows system root.

/l Specifies an optional locale parameter to use when

initializing the BCD store. The default is US English.

/s Specifies an optional volume letter parameter to designate

the target system partition where boot environment files are

copied. The default is the system partition identified by

the firmware.

/v Enables verbose mode.

/m If an OS loader GUID is provided, this option merges the

given loader object with the system template to produce a

bootable entry. Otherwise, only global objects are merged.

``Examples: bcdboot c:\windows /l en-us``

``bcdboot c:\windows /s h:``

``bcdboot c:\windows /m {d58d10c6-df53-11dc-878f-00064f4f4e08}``

#### bcdedit.exe {#h.mr7oaj2nombp" id="h.mr7oaj2nombp

``C:\Windows\System32>bcdedit /?``

BCDEDIT - Boot Configuration Data Store Editor

The Bcdedit.exe command-line tool modifies the boot configuration data store.

The boot configuration data store contains boot configuration parameters and

controls how the operating system is booted. These parameters were previously

in the Boot.ini file (in BIOS-based operating systems) or in the nonvolatile

RAM entries (in Extensible Firmware Interface-based operating systems). You can

use Bcdedit.exe to add, delete, edit, and append entries in the boot

configuration data store.

``For detailed command and option information, type bcdedit.exe /? \<command>. For``

example, to display detailed information about the /createstore command, type:

bcdedit.exe /? /createstore

For an alphabetical list of topics in this help file, run "bcdedit /? TOPICS".

Commands that operate on a store

``\================================``

/createstore Creates a new and empty boot configuration data store.

/export Exports the contents of the system store to a file. This file

can be used later to restore the state of the system store.

/import Restores the state of the system store using a backup file

created with the /export command.

/sysstore Sets the system store device (only affects EFI systems, does

not persist across reboots, and is only used in cases where

the system store device is ambiguous).

Commands that operate on entries in a store

``\===========================================``

/copy Makes copies of entries in the store.

/create Creates new entries in the store.

/delete Deletes entries from the store.

/mirror Creates mirror of entries in the store.

Run bcdedit /? ID for information about identifiers used by these commands.

Commands that operate on entry options

``\======================================``

/deletevalue Deletes entry options from the store.

/set Sets entry option values in the store.

Run bcdedit /? TYPES for a list of datatypes used by these commands.

Run bcdedit /? FORMATS for a list of valid data formats.

Commands that control output

``\============================``

/enum Lists entries in the store.

/v Command-line option that displays entry identifiers in full,

rather than using names for well-known identifiers.

Use /v by itself as a command to display entry identifiers

in full for the ACTIVE type.

Running "bcdedit" by itself is equivalent to running "bcdedit /enum ACTIVE".

Commands that control the boot manager

``\======================================``

/bootsequence Sets the one-time boot sequence for the boot manager.

/default Sets the default entry that the boot manager will use.

/displayorder Sets the order in which the boot manager displays the

multiboot menu.

/timeout Sets the boot manager time-out value.

/toolsdisplayorder Sets the order in which the boot manager displays

the tools menu.

Commands that control Emergency Management Services for a boot application

``\==========================================================================``

/bootems Enables or disables Emergency Management Services

for a boot application.

/ems Enables or disables Emergency Management Services for an

operating system entry.

/emssettings Sets the global Emergency Management Services parameters.

Command that control debugging

``\==============================``

/bootdebug Enables or disables boot debugging for a boot application.

/dbgsettings Sets the global debugger parameters.

/debug Enables or disables kernel debugging for an operating system

entry.

/hypervisorsettings Sets the hypervisor parameters.

``C:\Windows\System32>``

#### compact.exe {#h.sz4aseeppgbp" id="h.sz4aseeppgbp

``C:\Windows\System32>compact /?``

Displays or alters the compression of files on NTFS partitions.

COMPACT \[/C | /U] \[/S\[:dir]] \[/A] \[/I] \[/F] \[/Q] \[filename \[...]]

/C Compresses the specified files. Directories will be marked

so that files added afterward will be compressed.

/U Uncompresses the specified files. Directories will be marked

so that files added afterward will not be compressed.

/S Performs the specified operation on files in the given

directory and all subdirectories. Default "dir" is the

current directory.

/A Displays files with the hidden or system attributes. These

files are omitted by default.

/I Continues performing the specified operation even after errors

have occurred. By default, COMPACT stops when an error is

encountered.

/F Forces the compress operation on all specified files, even

those which are already compressed. Already-compressed files

are skipped by default.

/Q Reports only the most essential information.

filename Specifies a pattern, file, or directory.

Used without parameters, COMPACT displays the compression state of

the current directory and any files it contains. You may use multiple

filenames and wildcards. You must put spaces between multiple

parameters.

``C:\Windows\System32>``

#### csvde.exe {#h.dpg2d0eaaozw" id="h.dpg2d0eaaozw

``C:\Windows\System32>csvde -?``

Unknown Option

CSV Directory Exchange

General Parameters

``\==================``

``\-i Turn on Import Mode (The default is Export)``

``\-f filename Input or Output filename``

``\-s servername The server to bind to (Default to DC of computer's domain)``

``\-v Turn on Verbose Mode``

``\-c FromDN ToDN Replace occurences of FromDN to ToDN``

``\-j path Log File Location``

``\-t port Port Number (default = 389)``

``\-u Use Unicode format``

``\-? Help``

Export Specific

``\===============``

``\-d RootDN The root of the LDAP search (Default to Naming Context)``

``\-r Filter LDAP search filter (Default to "(objectClass=\*)")``

``\-p SearchScope Search Scope (Base/OneLevel/Subtree)``

``\-l list List of attributes (comma separated) to look for in an``

LDAP search

``\-o list List of attributes (comma separated) to omit from input.``

``\-g Disable Paged Search.``

``\-m Enable the SAM logic on export.``

``\-n Do not export binary values``

Import

``\======``

``\-k The import will go on ignoring 'Constraint Violation' and``

'Object Already Exists' errors

Credentials Establishment

``\=========================``

Note that if no credentials is specified, CSVDE will bind as the currently

logged on user, using SSPI.

\-a UserDN \[Password | \*] Simple authentication

\-b UserName Domain \[Password | \*] SSPI bind method

Example: Simple import of current domain

csvde -i -f INPUT.CSV

Example: Simple export of current domain

csvde -f OUTPUT.CSV

Example: Export of specific domain with credentials

csvde -m -f OUTPUT.CSV

``\-b USERNAME DOMAINNAME \*``

``\-s SERVERNAME``

``\-d "cn=users,DC=DOMAINNAME,DC=Microsoft,DC=Com"``

``\-r "(objectClass=user)"``

No log files were written. In order to generate a log file, please

specify the log file path via the -j option.

#### diantz.exe {#h.in7pggjkhzqe" id="h.in7pggjkhzqe

``C:\Windows\System32>diantz /?``

Cabinet Maker - Lossless Data Compression Tool

``MAKECAB \[/V\[n]] \[/D var=value ...] \[/L dir] source \[destination]``

``MAKECAB \[/V\[n]] \[/D var=value ...] /F directive\_file \[...]``

source File to compress.

destination File name to give compressed file. If omitted, the

last character of the source file name is replaced

``with an underscore (\_) and used as the destination.``

/F directives A file with MakeCAB directives (may be repeated). Refer to

``Microsoft Cabinet SDK for information on directive\_file.``

/D var=value Defines variable with specified value.

/L dir Location to place destination (default is current directory).

``/V\[n] Verbosity level (1..3).``

#### diskraid.exe {#h.lwdtyeqzkcta" id="h.lwdtyeqzkcta

``C:\Windows\System32>diskraid /?``

Microsoft DiskRAID version 6.1.7601

Copyright (C) 2003-2007 Microsoft Corporation.

On computer: ITTECH

Usage: DISKRAID \[/? | \[/s \<script>] \[/v]]

Launches the DiskRAID application.

/? specifies that DiskRAID should display this usage text.

``/s \<script> specifies that DiskRAID should execute commands from the script``

file at the location specified.

/v specifies that DiskRAID should run in verbose mode, printing

out additional information about each command being executed.

Examples:

DISKRAID

DISKRAID /v

``C:\Windows\System32>``

#### vssadmin.exe {#h.em4pf6v16n18" id="h.em4pf6v16n18

``C:\Windows\System32>vssadmin``

vssadmin 1.1 - Volume Shadow Copy Service administrative command-line tool

(C) Copyright 2001-2005 Microsoft Corp.

Error: Invalid command.

``\---- Commands Supported ----``

Delete Shadows - Delete volume shadow copies

List Providers - List registered volume shadow copy providers

List Shadows - List existing volume shadow copies

List ShadowStorage - List volume shadow copy storage associations

List Volumes - List volumes eligible for shadow copies

List Writers - List subscribed volume shadow copy writers

Resize ShadowStorage - Resize a volume shadow copy storage association

``C:\Windows\System32>``

#### cipher.exe {#h.pamigd89rng4" id="h.pamigd89rng4

``C:\\>cipher /?``

``Displays or alters the encryption of directories \[files] on NTFS partitions.``

CIPHER \[/E | /D | /C]

``\[/S:directory] \[/B] \[/H] \[pathname \[...]]``

CIPHER /K \[/ECC:256|384|521]

CIPHER /R:filename \[/SMARTCARD] \[/ECC:256|384|521]

``CIPHER /U \[/N]``

CIPHER /W:directory

``CIPHER /X\[:efsfile] \[filename]``

CIPHER /Y

CIPHER /ADDUSER \[/CERTHASH:hash | /CERTFILE:filename | /USER:username]

``\[/S:directory] \[/B] \[/H] \[pathname \[...]]``

``CIPHER /FLUSHCACHE \[/SERVER:servername]``

CIPHER /REMOVEUSER /CERTHASH:hash

``\[/S:directory] \[/B] \[/H] \[pathname \[...]]``

``CIPHER /REKEY \[pathname \[...]]``

/B Abort if an error is encountered. By default, CIPHER continues

executing even if errors are encountered.

/C Displays information on the encrypted file.

/D Decrypts the specified files or directories.

/E Encrypts the specified files or directories. Directories will be

marked so that files added afterward will be encrypted. The

encrypted file could become decrypted when it is modified if the

parent directory is not encrypted. It is recommended that you

encrypt the file and the parent directory.

/H Displays files with the hidden or system attributes. These files

are omitted by default.

/K Creates a new certificate and key for use with EFS. If this

option is chosen, all the other options will be ignored.

Note: By default, /K creates a certificate and key that conform

to current group policy. If ECC is specified, a self-signed

certificate will be created with the supplied key size.

/N This option only works with /U. This will prevent keys being

updated. This is used to find all the encrypted files on the

local drives.

/R Generates an EFS recovery key and certificate, then writes them

to a .PFX file (containing certificate and private key) and a

.CER file (containing only the certificate). An administrator may

add the contents of the .CER to the EFS recovery policy to create

the recovery key for users, and import the .PFX to recover

individual files. If SMARTCARD is specified, then writes the

recovery key and certificate to a smart card. A .CER file is

generated (containing only the certificate). No .PFX file is

generated.

Note: By default, /R creates an 2048-bit RSA recovery key and

certificate. If ECC is specified, it must be followed by a

key size of 256, 384, or 521.

/S Performs the specified operation on the given directory and all

files and subdirectories within it.

/U Tries to touch all the encrypted files on local drives. This will

update user's file encryption key or recovery keys to the current

ones if they are changed. This option does not work with other

options except /N.

/W Removes data from available unused disk space on the entire

volume. If this option is chosen, all other options are ignored.

The directory specified can be anywhere in a local volume. If it

is a mount point or points to a directory in another volume, the

data on that volume will be removed.

/X Backup EFS certificate and keys into file filename. If efsfile is

provided, the current user's certificate(s) used to encrypt the

file will be backed up. Otherwise, the user's current EFS

certificate and keys will be backed up.

/Y Displays your current EFS certificate thumbnail on the local PC.

/ADDUSER Adds a user to the specified encrypted file(s). If CERTHASH is

provided, cipher will search for a certificate with this SHA1

hash. If CERTFILE is provided, cipher will extract the

certificate from the file. If USER is provided, cipher will

try to locate the user's certificate in Active Directory Domain

Services.

/FLUSHCACHE

Clears the calling user's EFS key cache on the specified server.

If servername is not provided, cipher clears the user's key cache

on the local machine.

/REKEY Updates the specified encrypted file(s) to use the configured

EFS current key.

/REMOVEUSER

Removes a user from the specified file(s). CERTHASH must be the

SHA1 hash of the certificate to remove.

directory A directory path.

filename A filename without extensions.

pathname Specifies a pattern, file or directory.

efsfile An encrypted file path.

Used without parameters, CIPHER displays the encryption state of the

current directory and any files it contains. You may use multiple directory

names and wildcards. You must put spaces between multiple parameters.

``C:\\>cipher /w:C:\\``

To remove as much data as possible, please close all other applications while

running CIPHER /W.

Writing 0x00

................................................................................................................................

Writing 0xFF

...............................................................................................................................

Writing Random Numbers

..............................................................................................................................

``C:\\>``

zipfldr.dll

rundll32 zipfldr.dll,registersendto

Restore missing Send to Compressed file

krdeploy.cmd

#### msg.exe {#h.9we2ibcuigvi" id="h.9we2ibcuigvi

``C:\Windows\System32>msg.exe /?``

Send a message to a user.

MSG {username | sessionname | sessionid | @filename | \*}

``\[/SERVER:servername] \[/TIME:seconds] \[/V] \[/W] \[message]``

username Identifies the specified username.

sessionname The name of the session.

sessionid The ID of the session.

@filename Identifies a file containing a list of usernames,

sessionnames, and sessionids to send the message to.

``\* Send message to all sessions on specified server.``

/SERVER:servername server to contact (default is current).

/TIME:seconds Time delay to wait for receiver to acknowledge msg.

/V Display information about actions being performed.

/W Wait for response from user, useful with /V.

message Message to send. If none specified, prompts for it

or reads from stdin.

``C:\Windows\System32>``

#### outlook.exe {#h.u4nnvx2slo9w" id="h.u4nnvx2slo9w

[http://office.microsoft.com/en-us/outlook-help/command-line-switches-for-outlook-2010-HP010354956.aspx](http://office.microsoft.com/en-us/outlook-help/command-line-switches-for-outlook-2010-HP010354956.aspx)

**Available switches**

| **Switch**                                                                                                              | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /a                                                                                                                      | <p>Creates an item with the specified file as an attachment.</p><p>Example:</p><ul><li>"c:\program files\microsoft office\office14\outlook.exe" /a "c:\my documents\labels.doc"</li></ul><p>If no item type is specified, IPM.Note is assumed. Cannot be used with message classes that are not based on Outlook.</p>                                                                                                                                                                                                                                                        |
| /altvba _otmfilename_                                                                                                   | <p>Opens the VBA program specified in <em>otmfilename</em>, instead of %appdata%\microsoft\outlook\vbaproject.otm.</p><p><strong>Note</strong> This command line switch is only available if the following Windows registry DWORD value is set to 1. HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Outlook\Security\EnableAltVba</p>                                                                                                                                                                                                                                      |
| /c _messageclass_                                                                                                       | <p>Creates a new item of the specified message class (Outlook forms or any other valid MAPI form).</p><p>Examples:</p><ul><li>/c ipm.activity creates a <strong>Journal</strong> entry</li><li>/c ipm.appointment creates an appointment</li><li>/c ipm.contact creates a contact</li><li>/c ipm.note creates an e-mail message</li><li>/c ipm.stickynote creates a note</li><li>/c ipm.task creates a task</li></ul>                                                                                                                                                        |
| /checkclient                                                                                                            | Prompts for the default manager of e-mail, news, and contacts.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /cleanautocompletecache                                                                                                 | Removes all names and e-mail addresses from the Auto-Complete list.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| /cleancategories                                                                                                        | Deletes any custom category names that you have created. Restores categories to the default names.                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| /cleanclientrules                                                                                                       | Starts Outlook and deletes client-based rules.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /cleanconvongoingactions                                                                                                | Deletes the Conversations Actions Table (CAT). CAT entries for a conversation thread usually expire 30 days after no activity. The command-line switch clears all conversation tagging, ignore, and moving rules immediately stopping any additional actions.                                                                                                                                                                                                                                                                                                                |
| /cleandmrecords                                                                                                         | Deletes the logging records saved when a manager or a delegate declines a meeting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| /cleanfinders                                                                                                           | Resets all Search Folders in the Microsoft Exchange mailbox for only the first profile opened.                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /cleanfreebusy                                                                                                          | Clears and regenerates free/busy information. This switch can be used only when you are able to connect to the server that runs Exchange.                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| /cleanfromaddresses                                                                                                     | Removes all manually added **From** entries from the profile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| /cleanmailtipcache                                                                                                      | Removes all MailTips from the cache.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| /cleanreminders                                                                                                         | Clears and regenerates reminders.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| /cleanroamedprefs                                                                                                       | All previous roamed preferences are deleted and copied again from the local settings on the computer where this switch is used. This includes the roaming settings for reminders, free/busy grid, working hours, calendar publishing, and RSS rules.                                                                                                                                                                                                                                                                                                                         |
| /cleanrules                                                                                                             | Starts Outlook and deletes client-based and server-based rules.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| /cleanserverrules                                                                                                       | Starts Outlook and deletes server-based rules.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /cleansharing                                                                                                           | Removes all RSS, Internet Calendar, and SharePoint subscriptions from Account Settings, but leaves all the previously downloaded content on your computer. This is useful if you cannot delete one of these subscriptions within Outlook 2010.                                                                                                                                                                                                                                                                                                                               |
| /cleansniff                                                                                                             | Overrides the programmatic lockout that determines which of your computers (when you run Outlook at the same time) processes meeting items. The lockout process helps prevent duplicate reminder messages. This switch clears the lockout on the computer it is used. This enables Outlook to process meeting items.                                                                                                                                                                                                                                                         |
| /cleansubscriptions                                                                                                     | Deletes the subscription messages and properties for subscription features.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| /cleanviews                                                                                                             | Restores default views. All custom views that you created are lost.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| /embedding                                                                                                              | Used without command-line parameters for standard OLE co-create.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| /f _msgfilename_                                                                                                        | Opens the specified message file (.msg) or Microsoft Office saved search (.oss).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| /finder                                                                                                                 | Opens the **Advanced Find** dialog box.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| /hol _holfilename_                                                                                                      | Opens the specified .hol file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /ical _icsfilename_                                                                                                     | Opens the specified .ics file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /importNK2                                                                                                              | Imports the contents of an .nk2 file which contains the nickname list that is used by both the automatic name checking and Auto-Complete features.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| /importprf _prffilename_                                                                                                | Starts Outlook and opens/imports the defined MAPI profile (\*.prf). If Outlook is already open, queues the profile to be imported on the next clean start.                                                                                                                                                                                                                                                                                                                                                                                                                   |
| /launchtraininghelp _assetid_                                                                                           | Opens a Help window with the Help topic specified in _assetid_ displayed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| /m _emailname_                                                                                                          | <p>Provides a way for the user to add an e-mail name to the item. Only works together with the /c command-line parameter.</p><p>Example:</p><ul><li>Outlook.exe /c ipm.note /m <em>emailname</em></li></ul>                                                                                                                                                                                                                                                                                                                                                                  |
| /nopreview                                                                                                              | Starts Outlook with the Reading Pane off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| /p _msgfilename_                                                                                                        | Prints the specified message (.msg).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| /profile _profilename_                                                                                                  | Loads the specified profile. If your profile name contains a space, enclose the profile name in quotation marks (" ").                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| /profiles                                                                                                               | Opens the **Choose Profile** dialog box regardless of the **Options** setting on the **Tools** menu.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| /promptimportprf                                                                                                        | Same as /importprf except that a prompt appears and the user can cancel the import.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| /recycle                                                                                                                | Starts Outlook by using an existing Outlook window, if one exists.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| /remigratecategories                                                                                                    | <p>Starts Outlook and starts the following commands on the default mailbox:</p><ul><li>Upgrades colored For Follow Up flags to Outlook 2010 color categories.</li><li>Upgrades calendar labels to Outlook 2010 color categories.</li><li>Adds all categories used on non-mail items into the Master Category List</li></ul><p><strong>Note</strong> This is the same command as <strong>Upgrade to Color Categories</strong> in each Outlook mailbox properties dialog box.</p>                                                                                              |
| /resetfolders                                                                                                           | Restores missing folders at the default delivery location.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| /resetfoldernames                                                                                                       | <p>Resets default folder names (such as <strong>Inbox</strong> or <strong>Sent Items</strong>) to default names in the current Office user interface language.</p><p>For example, if you first connect to your mailbox in Outlook by using a Russian user interface, the Russian default folder names cannot be renamed. To change the default folder names to another language, such as Japanese or English, you can use this switch to reset the default folder names after you change the user interface language or install a different language version of Outlook.</p> |
| /resetformregions                                                                                                       | Empties the form regions cache and reloads the form region definitions from the Windows registry.                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| /resetnavpane                                                                                                           | Clears and regenerates the Navigation Pane for the current profile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| /resetquicksteps                                                                                                        | Restores the default Quick Steps. All user-created Quick Steps are deleted.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| /resetsearchcriteria                                                                                                    | Resets all Instant Search criteria so that the default set of criteria is shown in each module.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| /resetsharedfolders                                                                                                     | Removes all shared folders from the Navigation Pane.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| /resettodobar                                                                                                           | Clears and regenerates the To-Do Bar task list for the current profile. The To-Do Bar search folder is deleted and re-created.                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /restore                                                                                                                | Attempts to open the same profile and folders that were open prior to an abnormal Outlook shutdown.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| /rpcdiag                                                                                                                | Opens Outlook and displays the remote procedure call (RPC) connection status dialog box.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| /safe                                                                                                                   | Starts Outlook without the Reading Pane or toolbar customizations. Both native and managed Component Object Model (COM) add-ins are turned off.                                                                                                                                                                                                                                                                                                                                                                                                                              |
| /safe:1                                                                                                                 | Starts Outlook with the Reading Pane off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| /safe:3                                                                                                                 | Both native and managed Component Object Model (COM) add-ins are turned off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| /select _foldername_                                                                                                    | Starts Outlook and opens the specified folder in a new window. For example, to open Outlook and display the default calendar, use: "c:\program files\microsoft office\office14\outlook.exe" /select outlook:calendar.                                                                                                                                                                                                                                                                                                                                                        |
| <p>/share feed://<em>URL/filename</em></p><p>/share stssync://<em>URL</em></p><p>/share web://<em>URL/filename</em></p> | Specifies a sharing URL to connect to Outlook. For example, use stssync://URL to connect a SharePoint list to Outlook.                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| /sniff                                                                                                                  | Starts Outlook, forces a detection of new meeting requests in the **Inbox**, and then adds them to the calendar.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| /t _oftfilename_                                                                                                        | Opens the specified .oft file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /v _vcffilename_                                                                                                        | Opens the specified .vcf file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| /vcal _vcsfilename_                                                                                                     | Opens the specified .vcs file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

dcpromo

/adv

/force

regini.exe

NTFS and AD permissions document

any user can join PC to domain (10 times)

what attributes are visible to all

what attributes are replicated

what attributes are copied with copy user

who can see Notes on ADUC Telephone tab

default container for PC joining domain

``1. [http://en.wikipedia.org/wiki/Run\_command](http://en.wikipedia.org/wiki/Run\_command) ↑``
2. [http://blogs.technet.com/b/cmpfekevin/archive/2014/01/29/troubleshooting-bits-with-powershell.aspx](http://blogs.technet.com/b/cmpfekevin/archive/2014/01/29/troubleshooting-bits-with-powershell.aspx) ↑
