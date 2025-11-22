### Popular Applications
[Common Applications](Common-Apps.md)

#### Internet Explorer

Windows 7 (IE version 9)

`C:\Users\<USERNAME>\Downloads`

`C:\Users\UserName\AppData\Local\Microsoft\Windows\Temporary Internet Files`

`C:\Windows\Downloaded Program Files`

Internet Explorer Temp Folder (IE Cache)

``C:\Users\UserName\AppData\Local\Microsoft\Windows\Temporary Internet Files``

IE Cookies

`C:\Users\username\AppData\Roaming\Microsoft\Windows\Cookies`

Good to export this file using IE, File, Export when moving a user to another computer.

Internet Explorer History

`C:\Users\<USERNAME>\AppData\Local\Microsoft\Windows\History`

IE Typed URLs<br>
`HKCU\Software\Microsoft\Internet Explorer\TypedUrls`

not be 100% certain, google Julie Amero

Internet Explorer Forms AutoComplete<br>
`HKCU\Software\Microsoft\Internet Explorer\IntelliForms\Storage1`<br>
obfuscated form

Internet Explorer Password AutoComplete<br>
`HKCU\Software\Microsoft\Internet Explorer\IntelliForms\Storage2`<br>
obfuscated form

**Links and Shortcuts**

``C:\Users\UserName\Links``

Windows XP

``C:\Documents and Settings\<UserName>\Application Data\Microsoft\Internet Explorer\Quick Launch``

Must also enable the Toolbar, right click Toolbars, select

Windows 7

``%APPDATA%\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar``

``HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Taskband``

**Internet Explorer image in web page, Set as background**

``C:\Users\UserName\AppData\Roaming\Microsoft\Internet Explorer\Internet Explorer Wallpaper.bmp``

**Internet Security Properties, Sites, Add website to the zone**

What sites/locations are classified automatically

Local

Local Intranet

Internet/Untrusted

URL Wildcard Sequence:

Examples of valid patterns:
```
*://*.microsoft.com
http://*.microsoft.co.jp
ftp://157.54.23.41/
file:\localsvr\share
*://157.54.100-200.*
```

Examples of invalid patterns:
```
http://microsoft.*.com
ftp://*
```

Windows Update URLs to add to Trusted

Outlook Emails and Attachments classified under which Security Zone?

**Content Adviser**

URLs to add for viewing system files in MMC

``about:\_?\_``

**Internet Explorer Administration Kit**

`.ins` automatic configuration file for customized browser configuration settings created with the Profile Manager

#### Windows Live

``C:\Program Files (x86)\Common Files\Windows Live\.cache\``

#### Outlook Express

**Outlook Express E-Mail Storage**

``C:\Documents and Settings\Username\Local\Application Data\Identities``

**Outlook Express Address Book Contacts**

Address Book used by Outlook Express ``[9]``<br>
``C:\Documents and Settings\<UserName>\Application Data\Microsoft\Address Book``

Do other applications use it? Outlook, Windows? (`*.pab`, `*.wab`)

#### Microsoft Office

Components

See Appendix

**Installation Files or CD**

```
setup.exe /?

Setup Controller Command-Line Help

/? - Display this command-line help
/admin - Launch the Office Customization Tool
/adminfile <admin file> - Specify a customization patch of folder containing a customization patch
/config <config file> - Specify a config.xml file
/modify <product ID> - Enter Maintenance Mode for a product
/repair <product ID> - Repair a product
/uninstall <product ID> - Uninstall a product
```

What are the product IDs?

**Changes to Installation**

* Excel auto save now included, used to require manual selection
* Outlook Social Connector still requires manual install of 3rd-party add ons
* Does converters and graphics filters affect file preview of .GIF, .JPG?
* OCR tools removed from 64-bit. Were part of discontinued Picture/Imaging Manager? Some work arounds include installing Sharepoint designer? or using OneNote and TIF file?

**How To Outlook LDAP directory to use AD**

1. Add account, Address Books tab, Microsoft LDAP Directory
2. Server Name: FQDN to server
3. Logon Information
4. This server requires me to log on: Checked (User Name and Password can be left blank)
5. Require Secure Password Authentication (SPA) Checked
6. More Settings ... button
7. Connection tab
8. Display Name: The name of the address book your users will see
10. Connection Details: no change needed
11. Search tab
12. Specify the maximum number of entries you want to return after a successful search: 200
13. Search Base, Custom: `dc=domainname,dc=com`
14. Enable Browsing **(requires server support)**

**Differences with Service Pack 1**

``Office 2010 Standard with SP1 has the following additional files in the .\Updates folder``
```
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
```

**Microsoft Office Customization Tool**

As of Microsoft Office 2010, there is no separate download
1. `SETUP.EXE /admin` to open Office Customization Tool<br>
2. Creates a `.MSP` file to be placed in the `.\Updates` folder

Windows Live has Skydrive? which will replicate certain office settings to other computers.

These settings include dictionary, word.dot?, ...

Recently Opened Office Docs<br>
``C:\Users\<USERNAME>\AppData\Roaming\Microsoft\Office\Recent``

**Recovered Office files**<br>
`C:\Users\<UserName>\AppData\Local\Microsoft\Office\UnsavedFiles`

**Connect to database and execute SQL**<br>
Microsoft Query `"C:\Program Files\Microsoft Office\Office14\MSQRY32.EXE"`

**Custom Dictionary**<br>
`C:\Users\<UserName>\AppData\Roaming\Microsoft\UProof\CUSTOM.DIC`

**Dictionary (.dic)**

**Windows 7 and Windows Vista** `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\UProof`<br>
**Windows XP** `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\UProof`

**Templates (.oft)**

**Windows 7 and Windows Vista** `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\Templates`<br>
**Windows XP** `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Templates`

**Templates**

**Add-Ons**

**Data Connections**

``C:\Program Files\Microsoft Office\Office14\QUERIES``
```
MSN MoneyCentral Investor Currency Rates.iqy
MSN MoneyCentral Investor Major Indicies.iqy
MSN MoneyCentral Investor Stock Quotes.iqy
```

``%USERPROFILE%\Documents\My Data Sources\<ServerName>\__SQLInstance_ _DatabaseName_.odc``

**Visual Basic for Applications**

VBA settings migration ``[10]``

In Office 2010, Visual Basic for Applications (VBA) 6.0 was updated to VBA 7.0. VBA 7.0 settings were reset to their defaults after migration instead of automatically repopulating. This occurred because the registry settings for VBA are in a different hive in Office 2010, as shown in the following table.

Office 2000 through Office 2007<br>
``HKCU\SOFTWARE\Microsoft\VBA\6.0\Common``
<br>
Office 2010<br>
``HKCU\SOFTWARE\Microsoft\VBA\7.0\Common``


| Office 9 through Office 12 | Office 14|
| -------------------------- | -------------------------------------- |
|   HKCU\SOFTWARE\Microsoft\VBA\6.0\Common  | HKCU\SOFTWARE\Microsoft\VBA\7.0\Common |

To correct this problem, copy the VBA 6.0 registry keys from the 6.0 hive to the 7.0 hive.

**Digital Certificate for VBA**

`SelfCert.exe` can also be used to sign PowerShell and documents such as Access databases and installers

`C:\Program Files\Microsoft Office\root\Office16\SelfCert.exe` usage & switches

**Create Digital Certificate**<br>
This program creates a self-signed digital certificate that beats the name you type below. This type of certificate does not verify your identity.

Since a self-signed digital certificate might be a forgery, users will receive a security warning when they open a file that contains a macro project with a self-signed signature.

Office will only allow you to trust a self-signed certificate on the machine on which it was created.

A self-signed certificate is only for personal use. If you need an authenticated code signing certificate for signing commercial or broadly distributed macros, you will need to contact a certification authority.

[Click here for a list of commercial certificate authorites](https://learn.microsoft.com/en-us/previous-versions/ms995347(v=msdn.10)?redirectedfrom=MSDN)

_Y_our certificate's name:<br>
<kbd> OK </kbd> <kbd> Cancel </kbd>


**other cert tools**

certutil

signtool

certreq

mmc.exe cert*.msc (certmgr and certlm)

additional MMC .MSC for AD CS

**Document Inspector**

customize the Document Inspector by adding Inspector modules

**Microsoft Visio**

* In Windows 7 and Windows Vista, the **My Shapes** directory is located at `C:\Users\<USERNAME>\Documents\My Shapes`.
* In Windows XP and earlier, the **My Shapes** directory is located at `C:\Documents and Settings\<USERNAME>\My Documents\My Shapes`.

**Microsoft Office 2013 Activation**

[http://www.askvg.com/fix-the-products-we-found-in-your-account-cant-be-used-to-activate-error-message-in-microsoft-office-2013-applications/](http://technet.microsoft.com/en-us/library/cc771151.aspx)

trying to activate the product using your Windows Live ID (Microsoft account) or Office 365 account credentials, the product doesn't get activated

Don't activate the product using your account credentials. Just enter your product key manually to activate Office 2013 copy.

You can follow these simple steps to fix the problem and successfully activate Office 2013 in your system:

1. Open **Control Panel** and click on **Programs and Features** icon.
2. Now click on **Microsoft Office 2013** entry given in the list and then click on **Change** button given in the toolbar.
3. It'll open Office 2013 setup wizard and will show following options to select:
  * Add or Remove Features
  * Repair
  * Remove
  * Enter a Product Key

manually uninstall product keys installed by Preview version of Office 2013

```
CD C:\Program Files\Microsoft Office\Office15
cscript ospp.vbs /dstatus
```

Note down the **last 5 characters of product keys** given in each section.<br>
Now run following command for each product key:
``cscript ospp.vbs /unpkey:_last_5_characters_of_product_key_``
For example if the last 5 characters of one product key are ABCDE, then run following command:
`cscript ospp.vbs /unpkey:ABCDE`
Uninstall all existing versions of Office from your system and then reinstall Office 2013. Now it should activate itself without any problem.

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

#### Microsoft Outlook

Outlook-specific

Exchange (SMTP):

``HKLM\SOFTWARE\Microsoft\Exchange\ContentFilter\`` `"ArchiveSCL"=dword:00000001`

see also: [http://office.microsoft.com/en-us/outlook-help/where-does-microsoft-outlook-2010-save-my-information-and-configurations-HP010354943.aspx](http://technet.microsoft.com/en-us/library/cc732406.aspx)

**64-bit edition**<br>
Tell if the Outlook 2010 is a 32-bit or 64-bit installation ``[11]``

``HKLM\Software\Microsoft\Office\14.0\Outlook``

Bitness: x86 or x64

``IF EXIST "%ProgramFiles%\Microsoft Office\Office14\outlook.exe"``
or ``"%ProgramFiles(x86)%\Microsoft Office\Office14\outlook.exe"``

``Social Connectors and other Add-ons are specific to 32 or 64-bit editions. 32-bit compiled add-ons will not work in 64-bit office. See Microsoft notes on this \[Link here]``

Calendar settings, Working Hours ``[12]``

``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefStart``<br>
``HKCU\Software\Microsoft\Office\12.0\Outlook\Options\Calendar\CalDefEnd``

**Outlook command line switches**

``cannot use "%ProgramFiles%\Microsoft Office\Office14\outlook.exe" /?``

``Switches Detailed in Appendix \_?\_``

.PRF file for Outlook profile<br>
`outlook.exe /importprf MigrateEmail.PRF`

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

The Auto-Complete List is a feature which displays suggestions for names and e-mail addresses as you begin to type them. These suggestions are possible matches from a list of names and e-mail addresses from the e-mail messages that you have sent.<br>
<br>
In Outlook 2010, the Auto-Complete List file (.nk2) is discontinued. The Auto-Complete List entries are now saved in your Microsoft Exchange Server mailbox or for POP3, IMAP, or Hotmail \& Windows Live accounts, in the Outlook Data File (.pst) for your account.<br>

Temp folder for Outlook attachments

``HKCU\Software\Microsoft\Office\12.0\Outlook\Security``<br>
``C:\Users\<UserName>\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook\<random value>\``

**Personal Storage and Offline Storage**

**Outlook Data File .PST**

Earlier Outlook on XP, `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Outlook`<br>
Earlier Outlook on Vista `C:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook`<br>
For Outlook 2010, `C:\Users\<Username>\Documents\Outlook`<br>

Offline Outlook Mailbox<br>
``C:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook\outlook.ost``

**Outlook Data File .OST**

If you enable use Cached Exchange Mode or to work offline, items in your Exchange mailbox are copied in an offline Outlook Data File (.ost)

Outlook on XP, `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Outlook`<br>
Outlook on Vista `C:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook`

**Outlook Archive**

Outlook 2010 stores PST in `Documents\Email` folder?

**Microsoft Outlook Inbox Repair Tool**

PST file repair `"C:\Program Files\Microsoft Office\Office14\SCANPST.EXE"`

**Outlook Temp directory**

for opening attachments `C:\Users\<UserName>\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook`

**Outlook logging (troubleshooting)**

Diagnostics log location`[15]` (File, Options, Advanced, Other, Enable troubleshooting logging)

The calendar log file is a binary file that cannot be read without a conversion process. Contact Microsoft Support.

MAPI (Exchange), POP3, and SMTP log file:

* Windows Vista \& 7 - `c:\Users\<USERNAME>\AppData\Local\Temp\Outlook Logging\OPMLog.log`
* Windows XP - `c:\Documents and Settings\<USERNAME>\Local Settings\Temp\Outlook Logging\OPMLog.log`
* `%temp%\olkas\yymmdd-time-fb.log` ?

IMAP transport name is similar to:

* Windows Vista \& 7 - `c:\Users\<USERNAME>\AppData\Local\Temp\Outlook Logging\IMAP-ExampleCom-07_19_2012-14_03_44_865.log`
* Windows XP - `c:\Documents and Settings\<USERNAME>\Local Settings\Temp\Outlook Logging\IMAP-ExampleCom-07_19_2012-14_03_44_865.log`

Outlook Profile

`HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows Messaging Subsystem\Profiles`

Microsoft Outlook Configuration Analyzer Tool 2.0 (OCAT)

**Outlook Autodiscover**

`Ctrl+Right click` on Outlook icon in System Tray

Test E-mail AutoConfiguration...

**Personal Address Book (.PAB)**

**Windows 7 and Windows Vista** `<DRIVE>:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook`<br>
**Windows XP** `<DRIVE>:\Documents and Settings\<USERNAME>\Local Settings\Application Data\Microsoft\Outlook`

Personal Address Books (.pab) are not supported in Outlook 2010. When you upgrade to Outlook 2010, you are prompted to import any .pab file into Contacts. If you choose not to import the .pab file when you first run Outlook 2010, you can import it later by using the **Import** command in the Microsoft Office Backstage view.

**Offline Address Book**

The Offline Address Book (.oab) is used by Microsoft Exchange Server accounts. It contains information, such as names, e-mail address, titles, and office locations, from the Global Address List (GAL) on the server that runs Exchange.

You do not have to back up or restore this file. This is file is created and updated automatically.

**Windows 7 and Windows Vista** `<DRIVE>:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook`<br>
**Windows XP** `<DRIVE>:\Documents and Settings\<USERNAME>\Local Settings\Application Data\Microsoft\Outlook`

**Navigation Pane settings (.xml)**

This file includes information about the contents of the Navigation Pane.

**Windows 7 and Windows Vista** `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Outlook\<profile name>.xml`<br>
**Windows XP** `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Outlook\<profile name>.xml`

**Registered Microsoft Exchange extensions (.dat)**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\AppData\Local\Microsoft\Outlook`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Local Settings\Application Data\Microsoft\Outlook`

**Rules (.rwz)**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\Outlook`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Outlook`

**Note** If you upgraded to Outlook 2010 from a version of Outlook earlier than Microsoft Outlook 2002, you might have an .rwz file on your computer's hard disk drive. The .rwz file is no longer needed, and the information about rules is now kept on the server running Microsoft Exchange, and in the Outlook Data File (.pst) for POP3 and IMAP e-mail accounts. You can delete the file.

If you use the Rules Import and Export feature, the default location for .rwz files is your **Documents** folder.

**Print styles (Outlprnt with no extension)**

`**Windows Vista** <DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\Outlook`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Outlook`

**Signatures (.rtf, .txt, .htm)**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\Signatures`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Signatures`

A signature named “Company default” will generate the following files and folder structure.<br>
```
C:\Users\UserName\AppData\Roaming\Microsoft\Signatures\`
+--Company default.htm
+--Company default.rtf
+--Company default.txt
+--Company default\files\
+--colorschememapping.xml
+--filelist.xml
+--themedata.thmx
```

**Stationery (.htm)**

If installed, and personal or computer-wide.

**Windows 7 and Windows Vista**  `<DRIVE>:\Program Files\Common Files\Microsoft Shared\Stationery`

**Windows 7 and Windows Vista 64-bit with Outlook 2010 32-bit** `<DRIVE>:\Program Files (x86)\Common Files\Microsoft Shared\Stationery`

**Windows XP**<br>
`<DRIVE>:\Program Files\Common Files\Microsoft Shared\Stationery`<br>
`C:\Users\UserName\AppData\Roaming\Microsoft\Stationery`

**Custom forms**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\AppData\Local\Microsoft\Forms`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Local Settings\Application Data\Microsoft\Forms`

Forms

``Program Files\<Office folder>\Office 14\Forms\<language ID>``

.ico, cfg, see SCL.CFG commonly used for Exchange/Outlook spam confidence level

**Send/Receive settings (.srs)**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\AppData\Roaming\Microsoft\Outlook`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\Application Data\Microsoft\Outlook`

``\<Profile Name>.srs``

**Message (.msg, .htm, .rtf)**

**Windows 7 and Windows Vista**  `<DRIVE>:\Users\<USERNAME>\Documents`

**Windows XP**  `<DRIVE>:\Documents and Settings\<USERNAME>\My Documents`

**.PRF file for Outlook profile**

`"%ProgramFiles%\Microsoft Office\Office14\outlook.exe" /importprf %LogonServer%\NETLOGON\MigrateEmail.PRF`<br>
`"%ProgramFiles(x86)%\Microsoft Office\Office14\outlook.exe" /importprf %LogonServer%\NETLOGON\MigrateEmail.PRF`

Use[ ](http://technet.microsoft.com/en-us/library/cc772168.aspx#heading=h.96ds1q77m2pr)[Microsoft Office Customization Tool](http://technet.microsoft.com/en-us/library/cc753151.aspx#heading=h.96ds1q77m2pr) for creating Outlook Profiles (.PRF)

**MAPI Tools**

MFCMAPI

MRMAPI

#### Microsoft Media Player

Files recently accessed by Windows Media Player

`HKCU\Software\Microsoft\MediaPlayer\Player\RecentFileList`

(XP Only?)

#### Microsoft Media Center

Windows 8 Media Center includes DVD playing CODEC, not Blu-Ray, and codec doesn’t work for Media Player.

Program schedule downloads directory

Recorded show directory

DRM files for moving recorded content

How to Backup and Restore Windows Media Player DRM Licenses or Media Usage Rights

[http://www.mydigitallife.info/how-to-backup-and-restore-windows-media-player-drm-licenses-or-media-usage-rights/](http://www.mydigitallife.info/how-to-backup-and-restore-windows-media-player-drm-licenses-or-media-usage-rights/)

[http://www.mydigitallife.info/individualize-windows-media-player-wmp-for-fairuse4wm-and-invalid-license-error/](http://www.mydigitallife.info/individualize-windows-media-player-wmp-for-fairuse4wm-and-invalid-license-error/)

#### Mozilla Firefox

**User Profile**

``C:\Users\<UserName>\AppData\Roaming\Mozilla\Firefox\Profiles``<br>
``%APPDATA%\Mozilla\Firefox\Profiles\``

**Bookmarks**

Firefox bookmarks (favorites)``[16]``

The places.sqlite file contains all your Firefox bookmarks and the list of all the websites you’ve visited.

**Custom Dictionary**

``C:\users\[username]\AppData\Roaming\Mozilla\Firefox\Profiles\[unique-alphanumeric-string].default\persdict.dat``<br>
``C:\Documents and Settings\[username]\ApplicationData\Mozilla\Firefox\Profiles\[unique-alphanumeric-string].default\persdict.dat``

Firefox:

``C:\Users\<USERNAME>\AppData\Local\Mozilla\Firefox\Profiles\<some profile number>.default\``

``\*.sqllite files``

* [SQLLiteStudio](http://www.sqlite.org/cvstrac/wiki?p=ManagementTools)
* dBeaver

Firefox Cached Pages

``C:\Users\<USERNAME>\AppData\Local\Mozilla\Firefox\Profiles\<some profile number>.default\Cache``

[http://www.securityfocus.com/infocus/1832](http://www.securityfocus.com/infocus/1832)

Firefox Form History File<br>
``C:\Users\<USERNAME>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\formhistory.sqlite``

Firefox Passwords File<br>
``C:\Users\<USERNAME>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\signons.sqlite``

Firefox Cookies<br>
``C:\Users\<USERNAME>\AppData\Roaming\Mozilla\Firefox\Profiles\<some profile number>.default\cookies.sqlite``

#### Adobe Flash Player {#FlashPlayer}

Flash Cookies Location<br>
``C:\Users\<USERNAME>\AppData\Roaming\Macromedia\Flash Player\\#SharedObjects\<random value>\``

Adobe Flash Player Update Configuration

Adobe Flash Player Background Updater

``C:\Windows\System32\Macromed\Flash\mms.cfg``<br>
``C:\Windows\SysWOW64\Macromed\Flash\mms.cfg``

Administrator Guide[17]

#### Apple iTunes

Beginning with new installations of version 10.? `C:\Users\UserName\Music\iTunes\iTunes Media`

Music `C:\Users\<UserName>\Music\iTunes\iTunes Media\Music`

AudioBooks<br>
Pickup Folder (Automatically add to itunes) ``C:\Users\UserName\Music\iTunes\iTunes Media\Automatically Add to iTunes``<br>
Books<br>
Podcasts<br>
iTunes U<br>
Movies<br>
TV Shows<br>
Compilations ``C:\Users\<UserName>\Music\iTunes\iTunes Media\Music\Compilations``<br>
Apps<br>
Device backups `C:\Users\<UserName>\AppData\Roaming\Apple Computer\MobileSync\Backup\78193d251bbc7f3bb18de246a16b8fe6ceba2cf7\` and `.\Manifest.mbdb`<br>
Device firmware updates `C:\Users\<UserName>\AppData\Roaming\Apple Computer\iTunes\iPod Software Updates``<br>
Apple Software Updates `C:\Users\<UserName>\AppData\Local\Apple\Apple Software Update``<br>
iTunes Library files (*.itl)\`[18]` \[sql lite] C:\Users\<UserName>\Music\iTunes\iTunes Library.itl`<br>
iTunes Library file XML `C:\Users\<UserName>\Music\iTunes\iTunes Music Library.xml`<br>
Cover images `C:\Users\<UserName>\Music\iTunes\Album Artwork`<br>

the iTunes configuration files (delete the "SC Info.sidb" file)[19]

 * The preference files for Windows Vista and 7 `[20]` are here:
   - ``C:\Users\username\AppData\Local\Apple Computer\iTunes\``
   - ``C:\Users\username\AppData\Roaming\Apple Computer\iTunes``
 * In Windows XP and 2000 the iTunes preference files`[21]` are here:
   - ``C:\Documents and Settings\username\Application Data\Apple Computer\iTunes\``
   - ``C:\Documents and Settings\username\Local Settings\Application Data\Apple Computer\iTunes``
 * In Windows XP and 2000 the iTunes configuration files `[22]` are here:
   - ``C:\Documents and Settings\All Users\Application Data\Apple Computer\iTunes\SC Info``

Devices

``C:\Users\UserName\AppData\Local\Apple Computer\iTunes\iPodDevices.xml``

**iCloud**

``Photostream My Pictures\Photostream\My Photostream ?``

**Safari**

#### Java (Sun/Oracle) {#h.ol8w38ugj79h" id="h.ol8w38ugj79h

**Offline MSI Installer files**

Java doesn’t provide downloads of MSI files. They can be located here during/after installation``[23]``<br>
``C:\Users\<user>\AppData\LocalLow\Sun\Java\jre1.7.0_09\jre1.7.0_09.msi``<br>
``C:\Documents and Settings\<USERNAME>\Local Settings\ApplicationData\Sun\Java\jre1.6.0_37_x64\jre1.6.0_37.msi``

**Autoupdate Registry key**

``HKLM\SOFTWARE\JavaSoft\Java Update\Policy\EnableJavaUpdate=0``<br>
``HKLM\SOFTWARE\WOW6432Node\JavaSoft\Java Update\Policy\EnableJavaUpdate=0``

**Java Temporary files**

Jar file cache``[24]`` (Good to clean following of virus?)<br>
Java 6 or 7, Windows Vista or above `C:\Users\UserName\AppData\LocalLow\Sun\Java\Deployment\cache`

**High-Security Option**

Security files area for getting higher level security certificates.

Also settings to help protect from exploits<br>
``HKCU\Software\AppDataLow\Software\JavaSoft\DeploymentProperties\\"deployment.security.level"="HIGH"``<br>
Setting the Security Level of the Java Client``[25]``<br>
``jre-7u10-windows-i586.exe with flags: /s WEB\_JAVA=1 WEB\_JAVA\_SECURITY\_LEVEL=H``

**Install**

Download site: http://java.com/en/download/manual.jsp

Admin guide:

Command Line: (see msiexec)
```
Windows ® Installer. V 5.0.7601.17514
msiexec /Option \<Required Parameter> \[Optional Parameter]

Install Options
</package | /i> <Product.msi>
Installs or configures a product
/a <Product.msi>
Administrative install - Installs a product on the network
/j<u|m> <Product.msi> [/t <Transform List>] [/g <Language ID>]
Advertises a product - m to all users, u to current user
</uninstall | /x> <Product.msi | ProductCode>
Uninstalls the product
Display Options
/quiet
Quiet mode, no user interaction
/passive
Unattended mode - progress bar only
/q[n|b|r|f]
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
/l[i|w|e|a|r|u|c|m|o|p|v|x|+|!|*] <LogFile>
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
+ - Append to existing log file
! - Flush each line to the log
* - Log all information, except for v and x options
/log <LogFile>
Equivalent of /l* <LogFile>
Update Options
/update <Update1.msp>[;Update2.msp]
Applies update(s)
/uninstall <PatchCodeGuid>[;Update2.msp] /package <Product.msi | ProductCode>
Remove update(s) for a product
Repair Options
/f[p|e|c|m|s|o|d|a|u|v] <Product.msi | ProductCode>
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
[PROPERTY=PropertyValue]

Consult the Windows ® Installer SDK for additional documentation on the command line syntax.

Copyright © Microsoft Corporation. All rights reserved.
Portions of this software are based in part on the work of the Independent JPEG Group.
```

#### Dell

Get/Convert Service Tag and Express Service Code

Default folder for extracted drivers

Digital Line Detect

Internet Name Lookup helper(sp?)

#### HP

Default folder for extracted drivers (SP*nnnn* files and printer drivers)

