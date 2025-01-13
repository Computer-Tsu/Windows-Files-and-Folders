### Popular Applications {#h.8dwdprfc5vfh" id="h.8dwdprfc5vfh
[Common Applications](Common-Apps.md)

#### Internet Explorer {#h.6ottd7anoz6k" id="h.6ottd7anoz6k

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

``file:\localsvr\share``

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

```
setup.exe /?

Setup Controller Command-Line Help

/? - Display this command-line help
/admin - Launch the Office Customization Tool
/adminfile \<admin file> - Specify a customization patch of folder containing a customization patch
/config \<config file> - Specify a config.xml file
/modify \<product ID> - Enter Maintenance Mode for a product
/repair \<product ID> - Repair a product
/uninstall \<product ID> - Uninstall a product
```

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

| -------------------------- | -------------------------------------- |
| Office 9 through Office 12 | HKCU\SOFTWARE\Microsoft\VBA\6.0\Common |
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

`cscript ospp.vbs /dstatus`

Note down the **last 5 characters of product keys** given in each section.

Now run following command for each product key:

``cscript ospp.vbs /unpkey:_last_5_characters_of_product_key_``

For example if the last 5 characters of one product key are ABCDE, then run following command:

`cscript ospp.vbs /unpkey:ABCDE`

uninstall all existing versions of Office from your system and then reinstall Office 2013. Now it should activate itself without any problem.

**Microsoft Office 2007-2013 File Format**

XML, 'Open Document'

File extensions: DOCX, XLSX, ...

are actually zip files, if extension changed to ZIP, then XML files and folders can be extracted

Sample:

```
C:.
| [Content_Types].xml
|
+-----customXml
| | item1.xml
| | itemProps1.xml
| |
| +-----_rels
| item1.xml.rels
|
+-----docProps
| app.xml
| core.xml
|
+-----word
| | document.xml Contains the content
| | fontTable.xml
| | settings.xml
| | styles.xml
| | stylesWithEffects.xml
| | webSettings.xml
| |
| +-----theme
| | theme1.xml
| |
| +-----_rels
| document.xml.rels
|
+-----_rels
.rels
```

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
or ``"%ProgramFiles(x86)%\Microsoft Office\Office14\outlook.exe"``

``Social Connectors and other Add-ons are specific to 32 or 64-bit editions. 32-bit compiled add-ons will not work in 64-bit office. See Microsoft notes on this \[Link here]``

``Calendar settings, Working Hours\[12]``

``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefStart``
``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefEnd``

**Outlook command line switches**

``cannot use "%ProgramFiles%\Microsoft Office\Office14\outlook.exe" /?``

``Switches Detailed in Appendix \_?\_``

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

In Outlook 2010, the Auto-Complete List file (.nk2) is discontinued. The Auto-Complete List entries are now saved in your Microsoft Exchange Server mailbox or for POP3, IMAP, or Hotmail \& Windows Live accounts, in the Outlook Data File (.pst) for your account.

Temp folder for Outlook attachments

``HKCU\Software\Microsoft\Office\12.0\Outlook\Security``

``C:\Users\\_\<UserName>_\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook\\_\<random value>_\\``

**Personal Storage and Offline Storage**

**Outlook Data File .PST**

``Earlier Outlook on XP, C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Outlook``

``Earlier Outlook on Vista C:\Users\\_user_\AppData\Local\Microsoft\Outlook``

``For Outlook 2010, C:\Users\<Username>\Documents\Outlook``

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

``* Windows Vista \\& 7 - c:\Users\\_user name_\AppData\Local\Temp\Outlook Logging\OPMLog.log``
``* Windows XP - c:\Documents and Settings\\_user name_\Local Settings\Temp\Outlook Logging\OPMLog.log``
``* %temp%\olkas\yymmdd-time-fb.log ?``

IMAP transport name is similar to:

``* Windows Vista \\& 7 - c:\Users\\_user name_\AppData\Local\Temp\Outlook Logging\IMAP-ExampleCom-07\_19\_2012-14\_03\_44\_865.log``
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

+--Company default.htm

+--Company default.rtf

+--Company default.txt

``+--Company default\_files\\``

+--colorschememapping.xml

+--filelist.xml

+--themedata.thmx

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

``Program Files\<Office folder>\Office 14\Forms\<language ID>``

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

``C:\Users\<UserName>\AppData\Roaming\Mozilla\Firefox\Profiles``

``%APPDATA%\Mozilla\Firefox\Profiles\\``

**Bookmarks**

``Firefox bookmarks (favorites)\[16]``

The places.sqlite file contains all your Firefox bookmarks and the list of all the websites you’ve visited.

**Custom Dictionary**

``C:\users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[unique-alphanumeric-string].default\persdict.dat``

``C:\Documents and Settings\[username]\ApplicationData\Mozilla\Firefox\Profiles\[unique-alphanumeric-string].default\persdict.dat``

Firefox:

``C:\Users\<user name>\AppData\Local\Mozilla\Firefox\Profiles\<some profile number>.default\\``

``\*.sqllite files``

SQLLiteStudio or http://www.sqlite.org/cvstrac/wiki?p=ManagementTools

Firefox Cached Pages

``C:\Users\<user name>\AppData\Local\Mozilla\Firefox\Profiles\<some profile number>.default\Cache``

[http://www.securityfocus.com/infocus/1832](http://www.securityfocus.com/infocus/1832)

Firefox Form History File

``C:\Users\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\formhistory.sqlite``

Firefox Passwords File

``C:\Users\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\signons.sqlite``

Firefox Cookies

``C:\Users\<user name>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\cookies.sqlite``

#### Adobe Flash Player {#h.itnceweu7188" id="h.itnceweu7188

Flash Cookies Location

``C:\Users\<username>\AppData\Roaming\Macromedia\Flash Player\\#SharedObjects\<random value>\\``

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

``C:\Users\<user>\AppData\LocalLow\Sun\Java\jre1.7.0\_09\jre1.7.0\_09.msi``

``C:\Documents and Settings\<user>\Local Settings\ApplicationData\Sun\Java\jre1.6.0\_37\_x64\jre1.6.0\_37.msi``

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

