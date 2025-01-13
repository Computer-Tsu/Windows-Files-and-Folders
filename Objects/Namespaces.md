### Shell Namespace Extensions {#ShellExtension}

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
