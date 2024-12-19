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

### List of Microsoft Commands {#hcommand-list}


NTFS and AD permissions document

any user can join PC to domain (10 times)

what attributes are visible to all

what attributes are replicated

what attributes are copied with copy user

who can see Notes on ADUC Telephone tab

default container for PC joining domain

``1. [http://en.wikipedia.org/wiki/Run\_command](http://en.wikipedia.org/wiki/Run\_command) ↑``
2. [http://blogs.technet.com/b/cmpfekevin/archive/2014/01/29/troubleshooting-bits-with-powershell.aspx](http://blogs.technet.com/b/cmpfekevin/archive/2014/01/29/troubleshooting-bits-with-powershell.aspx) ↑
