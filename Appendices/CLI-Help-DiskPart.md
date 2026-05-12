create partition efi
create partition extended
create partition logical
create partition msr
create partition primary
create volume mirror
create volume raid
create volume simple
create volume stripe

delete disk
delete partition
delete shadows
delete volume

-----

---
layout: Conceptual
title: diskpart | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the diskpart command interpreter, which helps you manage your computer's drives.
ms.topic: reference
author: robinharwood
ms.author: roharwoo
ms.date: 2022-09-21T00:00:00.0000000Z
locale: en-us
document_id: bca0f8f7-da0d-6340-bf63-f269be5f64d1
document_version_independent_id: 39758423-e92d-d2db-88f3-260dc5a1a26a
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/diskpart.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/diskpart.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 976
asset_id: administration/windows-commands/diskpart
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/diskpart.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 7103cfba-c387-5825-7d03-2b54bae0d9a4
---

# diskpart | Microsoft Learn

> 
> Applies to: Windows Server 2022, Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2, Windows Server 2008

The diskpart command interpreter helps you manage your computer's drives (disks, partitions, volumes, or virtual hard disks).

Before you can use **diskpart** commands, you must first list, and then select an object to give it focus. After an object has focus, any diskpart commands that you type will act on that object.

## Determine focus

When you select an object, the focus remains on that object until you select a different object. For example, if the focus is set on disk 0 and you select volume 8 on disk 2, the focus shifts from disk 0 to disk 2, volume 8.

Some commands automatically change the focus. For example, when you create a new partition, the focus automatically switches to the new partition.

You can only give focus to a partition on the selected disk. After a partition has focus, the related volume (if any) also has focus. After a volume has focus, the related disk and partition also have focus if the volume maps to a single specific partition. If this isn't the case, focus on the disk and partition are lost.

## Syntax

To start the diskpart command interpreter, at the command prompt type:

```cmd
diskpart <parameter>
```

Important

You must be in your local **Administrators** group, or a group with similar permissions, to run diskpart.

### Parameters

You can run the following commands from the Diskpart command interpreter:

| Command | Description |
| --- | --- |
| [active](active) | Marks the disk's partition with focus, as active. |
| [add](add) | Mirrors the simple volume with focus to the specified disk. |
| [assign](assign) | Assigns a drive letter or mount point to the volume with focus. |
| [attach vdisk](attach-vdisk) | Attaches (sometimes called mounts or surfaces) a virtual hard disk (VHD) so that it appears on the host computer as a local hard disk drive. |
| [attributes](attributes) | Displays, sets, or clears the attributes of a disk or volume. |
| [automount](automount) | Enables or disables the automount feature. |
| [break](break) | Breaks the mirrored volume with focus into two simple volumes. |
| [clean](clean) | Removes any and all partition or volume formatting from the disk with focus. |
| [compact vdisk](compact-vdisk) | Reduces the physical size of a dynamically expanding virtual hard disk (VHD) file. |
| [convert](convert) | Converts file allocation table (FAT) and FAT32 volumes to the NTFS file system, leaving existing files and directories intact. |
| [create](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/create) | Creates a partition on a disk, a volume on one or more disks, or a virtual hard disk (VHD). |
| [delete](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/delete) | Deletes a partition or a volume. |
| [detach vdisk](detach-vdisk) | Stops the selected virtual hard disk (VHD) from appearing as a local hard disk drive on the host computer. |
| [detail](detail) | Displays information about the selected disk, partition, volume, or virtual hard disk (VHD). |
| [exit](exit) | Exits the diskpart command interpreter. |
| [expand vdisk](expand-vdisk) | Expands a virtual hard disk (VHD) to the size that you specify. |
| [extend](extend) | Extends the volume or partition with focus, along with its file system, into free (unallocated) space on a disk. |
| [filesystems](filesystems) | Displays information about the current file system of the volume with focus and lists the file systems that are supported for formatting the volume. |
| [format](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc753770(v=ws.11)) | Formats a disk to accept files. |
| [gpt](gpt) | Assigns the gpt attribute(s) to the partition with focus on basic GUID partition table (gpt) disks. |
| [help](help) | Displays a list of the available commands or detailed help information on a specified command. |
| [import](import_1) | Imports a foreign disk group into the disk group of the local computer. |
| [inactive](inactive) | Marks the system partition or boot partition with focus as inactive on basic master boot record (MBR) disks. |
| [list](list) | Displays a list of disks, of partitions in a disk, of volumes in a disk, or of virtual hard disks (VHDs). |
| [merge vdisk](merge-vdisk) | Merges a differencing virtual hard disk (VHD) with its corresponding parent VHD. |
| [offline](offline) | Takes an online disk or volume to the offline state. |
| [online](online) | Takes an offline disk or volume to the online state. |
| [recover](recover) | Refreshes the state of all disks in a disk group, attempt to recover disks in an invalid disk group, and resynchronizes mirrored volumes and RAID-5 volumes that have stale data. |
| [rem](rem) | Provides a way to add comments to a script. |
| [remove](remove) | Removes a drive letter or mount point from a volume. |
| [repair](repair) | Repairs the RAID-5 volume with focus by replacing the failed disk region with the specified dynamic disk. |
| [rescan](rescan) | Locates new disks that may have been added to the computer. |
| [retain](retain) | Prepares an existing dynamic simple volume to be used as a boot or system volume. |
| [san](san) | Displays or sets the storage area network (san) policy for the operating system. |
| [select](select) | Shifts the focus to a disk, partition, volume, or virtual hard disk (VHD). |
| [set id](set-id) | Changes the partition type field for the partition with focus. |
| [shrink](shrink) | Reduces the size of the selected volume by the amount you specify. |
| [uniqueid](uniqueid) | Displays or sets the GUID partition table (GPT) identifier or master boot record (MBR) signature for the disk with focus. |

## Listing available objects

You can view a list of options associated to each command by running the main command followed by what is available to that specific command. Running **list** by itself will display the four parameters below:

![Screenshot of the diskpart list command.](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart/../media/diskpart/diskpart-1.png)

Note

After you run the **list** command, an asterisk (**\***) appears next to the object of focus.

### Examples

To see available disk(s), run **list disk**:

```cmd
list disk
```

To select a disk, run **select disk** followed by the disk number. For example:

```cmd
select disk 1
```

![Screenshot of  diskpart showing available list command options.](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart/../media/diskpart/diskpart-2.png)

Before disk 1 can be utilized, a partition will need to be created by running **create partition primary**:

```cmd
create partition primary
```

Lastly, we can perform a quick format of disk 1 to NTFS with the label "Backup" by running **format fs=ntfs label=Backup quick** as seen below:

```cmd
format fs=ntfs label=Backup quick
```

![Screenshot of diskpart showing how to create a partition and formatting the drive.](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart/../media/diskpart/diskpart-3.png)

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [Disk management overview](../../storage/disk-management/overview-of-disk-management)
- [Storage Cmdlets in Windows PowerShell](/en-us/powershell/module/storage/)


-----


---
layout: Conceptual
title: diskpart scripts and examples | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart-scripts-and-examples
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for diskpart scripts and examples about how to automate disk-related tasks, such as creating volumes or converting disks to dynamic disks.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 0c50c55c-6062-bb83-5f41-73377349c9ca
document_version_independent_id: 68b62cde-c85f-9240-362a-c5702ba10ae7
updated_at: 2025-10-22T17:33:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/diskpart-scripts-and-examples.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/4282dd47a285a65de44c1512e8e9abd2384582a8/WindowsServerDocs/administration/windows-commands/diskpart-scripts-and-examples.md
git_commit_id: 4282dd47a285a65de44c1512e8e9abd2384582a8
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 409
asset_id: administration/windows-commands/diskpart-scripts-and-examples
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/diskpart-scripts-and-examples.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
platformId: d8d8a2b0-b6eb-3f17-57fb-0b6be947dc9f
---

# diskpart scripts and examples | Microsoft Learn

Use `diskpart /s` to run scripts that automate disk-related tasks, such as creating volumes or converting disks to dynamic disks. Scripting these tasks is useful if you deploy Windows by using unattended Setup or the Sysprep tool, which do not support creating volumes other than the boot volume.

To create a diskpart script, create a text file that contains the Diskpart commands that you want to run, with one command per line, and no empty lines. You can start a line with `rem` to make the line a comment. For example, here's a script that wipes a disk and then creates a 300 MB partition for the Windows Recovery Environment:

```
select disk 0
clean
convert gpt
create partition primary size=300
format quick fs=ntfs label=Windows RE tools
assign letter=T
```

## Examples

- To run a diskpart script, at the command prompt, type the following command, where *scriptname* is the name of the text file that contains your script:

```
diskpart /s scriptname.txt
```

- To redirect diskpart's scripting output to a file, type the following command, where *logfile* is the name of the text file where diskpart writes its output:

```
diskpart /s scriptname.txt > logfile.txt
```

### Remarks

- When using the **diskpart** command as a part of a script, we recommend that you complete all of the diskpart operations together as part of a single diskpart script. You can run consecutive diskpart scripts, but you must allow at least 15 seconds between each script for a complete shutdown of the previous execution before running the **diskpart** command again in successive scripts. Otherwise, the successive scripts might fail. You can add a pause between consecutive diskpart scripts by adding the `timeout /t 15` command to your batch file along with your diskpart scripts.
- When diskpart starts, the diskpart version and computer name display at the command prompt. By default, if diskpart encounters an error while attempting to perform a scripted task, diskpart stops processing the script and displays an error code (unless you specified the **noerr** parameter). However, diskpart always returns errors when it encounters syntax errors, regardless of whether you used the **noerr** parameter. The **noerr** parameter enables you to perform useful tasks such as using a single script to delete all partitions on all disks regardless of the total number of disks.

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [Sample: Configure UEFI/GPT-Based Hard Drive Partitions by Using Windows PE and DiskPart](/en-us/previous-versions/windows/it-pro/windows-8.1-and-8/hh825686%28v=win.10%29)
- [Sample: Configure BIOS/MBR-Based Hard Disk Partitions by Using Windows PE and DiskPart](/en-us/previous-versions/windows/it-pro/windows-8.1-and-8/hh825677%28v=win.10%29)
- [Storage Cmdlets in Windows PowerShell](/en-us/powershell/module/storage/)

-----

---
layout: Conceptual
title: active | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/active
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the active command, which on basic disks, marks the partition with focus as active.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 223974fe-b7c4-6ff2-73c5-939403da80a8
document_version_independent_id: e9f30af6-812b-b206-1a3c-fe48cb2b58a9
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/active.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/active.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 134
asset_id: administration/windows-commands/active
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/active.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 9f81efb8-87b8-a337-ec55-bd01be30ede4
---

# active | Microsoft Learn

On basic disks, marks the partition with focus as active. Only partitions can be marked as active. A partition must be selected for this operation to succeed. Use the **select partition** command to select a partition and shift the focus to it.

Caution

DiskPart only informs the basic input/output system (BIOS) or Extensible Firmware Interface (EFI) that the partition or volume is a valid system partition or system volume, and is capable of containing the operating system startup files. DiskPart does not check the contents of the partition. If you mistakenly mark a partition as active and it does not contain the operating system startup files, your computer might not start.

## Syntax

```
active
```

## Examples

To mark the partition with focus as the active partition, type:

```
active
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select partition command](select-partition)


-----
-----

---
layout: Conceptual
title: add | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/add_2
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the add command, which adds a disk or volume in an existing RAID configuration.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2023-10-12T00:00:00.0000000Z
locale: en-us
document_id: cb642cdc-6208-8018-8fc5-930a101a76f9
document_version_independent_id: cb642cdc-6208-8018-8fc5-930a101a76f9
updated_at: 2025-10-22T22:35:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/add_2.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/11e81f7dbcef1754ac5a183e38c100af2f728b60/WindowsServerDocs/administration/windows-commands/add_2.md
git_commit_id: 11e81f7dbcef1754ac5a183e38c100af2f728b60
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 235
asset_id: administration/windows-commands/add_2
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/add_2.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c783a8fb-cf36-41ad-90c6-0692a0540484
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 3dfa5f80-e10a-f9e0-a8dd-2cb399fac367
---

# add | Microsoft Learn

Mirrors the simple volume with focus to the specified active disk.

Note

This DiskPart command isn't available in any edition of Windows Vista.

## Syntax

```
add disk=<n> [align=<n>] [wait] [noerr]
```

## Parameters

| Parameter | Description |
| --- | --- |
| disk=`<n>` | Specifies a disk, other than the one containing the existing simple volume, to contain the mirror. You can mirror only simple volumes. The specified disk must have unallocated space at least as large as the size of the simple volume you want to mirror. |
| align=`<n>` | Typically used with hardware RAID Logical Unit Number (LUN) arrays to improve performance. Aligns all volume or partition extents to the closest alignment boundary. `n` is the number of kilobytes (KB) from the beginning of the disk to the closest alignment boundary. |
| wait | Waits for the volume to finish synchronizing with the added disk before returning. Without this parameter, DiskPart returns after the mirrored volume is created and doesn't wait for the synchronization to complete. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error didn't occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Remarks

- A volume must be selected for this operation to succeed. Use the select volume command to select a volume and shift the focus to it.

## Examples

To create a mirror of the volume with focus on disk 2, type:

```
add disk=2
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----
-----

---
layout: Conceptual
title: assign | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/assign
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the assign command, which assigns a drive letter or mount point to the volume with focus.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: ce07a41a-ae09-dbc5-9eeb-9e25538113ad
document_version_independent_id: 22bd174c-d174-961b-1210-c1d6510824c6
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/assign.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/assign.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 236
asset_id: administration/windows-commands/assign
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/assign.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c783a8fb-cf36-41ad-90c6-0692a0540484
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 3eae981e-870e-e1cb-4000-19cbf206ef75
---

# assign | Microsoft Learn

Assigns a drive letter or mount point to the volume with focus. You can also use this command to change the drive letter associated with a removable drive. If no drive letter or mount point is specified, the next available drive letter is assigned. If the drive letter or mount point is already in use, an error is generated.

A volume must be selected for this operation to succeed. Use the **select volume** command to select a volume and shift the focus to it.

Important

You can't assign drive letters to system volumes, boot volumes, or volumes that contain the paging file. In addition, you cannot assign a drive letter to an Original Equipment Manufacturer (OEM) partition or any GUID Partition Table (gpt) partition other than a basic data partition.

## Syntax

```
assign [{letter=<d> | mount=<path>}] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `letter=<d>` | The drive letter you want to assign to the volume. |
| `mount=<path>` | The mount point path you want to assign to the volume. For instructions about how to use this command, see [Assign a mount point folder path to a drive](../../storage/disk-management/assign-a-mount-point-folder-path-to-a-drive). |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To assign the letter E to the volume in focus, type:

```
assign letter=e
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select volume command](select-volume)

-----
-----

---
layout: Conceptual
title: attach vdisk | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/attach-vdisk
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the attach vdisk command, which attaches (sometimes called mounts or surfaces) a virtual hard disk (VHD) so that it appears on the host computer as a local hard disk drive.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 1dcedf1a-0adb-f598-8e28-15e3c9067e3a
document_version_independent_id: cc5641d6-f7f4-0200-bb44-742173d289ce
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/attach-vdisk.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/attach-vdisk.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 325
asset_id: administration/windows-commands/attach-vdisk
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/attach-vdisk.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 8a2893e6-e6c1-c91e-853b-cc19f7512d75
---

# attach vdisk | Microsoft Learn

Attaches (sometimes called mounts or surfaces) a virtual hard disk (VHD) so that it appears on the host computer as a local hard disk drive. If the VHD already has a disk partition and file system volume when you attach it, the volume inside the VHD is assigned a drive letter.

Important

You must choose and detach a VHD for this operation to succeed. Use the **select vdisk** command to select a VHD and shift the focus to it.

## Syntax

```
attach vdisk [readonly] { [sd=<SDDL>] | [usefilesd] } [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| readonly | Attaches the VHD as read-only. Any write operation returns an error. |
| `sd=<SDDL string>` | Sets the user filter on the VHD. The filter string must be in the Security Descriptor Definition Language (SDDL) format. By default the user filter allows access like on a physical disk. SDDL strings can be complex, but in its simplest form, a security descriptor that protects access is known as a discretionary access control list (DACL). It uses the form: `D:<dacl_flags><string_ace1><string_ace2>`... `<string_acen>`<br>Common DACL flags are:<br><br>- **A**. Allow access<br>- **D**. Deny access<br><br>Common rights are:<br>- **GA**. All access<br>- **GR**. Read access<br>- **GW**. Write access<br><br>Common user accounts are:<br>- **BA**. Built in administrators<br>- **AU**. Authenticated users<br>- **CO**. Creator owner<br>- **WD**. Everyone<br><br>Examples:<br>- **D:P:(A;;GR;;;AU**. Gives read-access to all authenticated users.<br>- **D:P:(A;;GA;;;WD**. Gives everyone full access. |
| usefilesd | Specifies that the security descriptor on the .vhd file should be used on the VHD. If the **Usefilesd** parameter is not specified, the VHD will not have an explicit security descriptor unless it is specified with the **Sd** parameter. |
| noerr | Used for scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To attach the selected VHD as read-only, type:

```
attach vdisk readonly
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select vdisk](select-vdisk)
- [compact vdisk](compact-vdisk)
- [detail vdisk](detail-vdisk)
- [detach vdisk](detach-vdisk)
- [expand vdisk](expand-vdisk)
- [merge vdisk](merge-vdisk)
- [list](list)


-----
-----

---
layout: Conceptual
title: attributes | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/attributes
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the attributes command, which displays, sets, or clears the attributes of a disk or volume.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 4325de2a-9e9f-662f-bc86-d725561f907f
document_version_independent_id: 3d6d5b5b-e278-4bc1-7c37-cd70510357bd
updated_at: 2025-10-22T17:33:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/attributes.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/4282dd47a285a65de44c1512e8e9abd2384582a8/WindowsServerDocs/administration/windows-commands/attributes.md
git_commit_id: 4282dd47a285a65de44c1512e8e9abd2384582a8
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 46
asset_id: administration/windows-commands/attributes
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/attributes.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: c8613efd-919a-f137-e97a-fc1c5d45e44a
---

# attributes | Microsoft Learn

Displays, sets, or clears the attributes of a disk or volume.

## Syntax

```
attributes disk
attributes volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [attributes disk](attributes-disk) | Displays, sets, or clears the attributes of a disk. |
| [attributes volume](attributes-volume) | Displays, sets, or clears the attributes of a volume. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: attributes disk | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/attributes-disk
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the attributes disk command, which displays, sets, or clears the attributes of a disk.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: c6fd1d3c-6647-d573-c1a0-3b0409da103d
document_version_independent_id: bd56eeaa-9c4e-a57c-bb0a-939d720d7940
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/attributes-disk.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/attributes-disk.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 183
asset_id: administration/windows-commands/attributes-disk
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/attributes-disk.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
platformId: e80cd96f-30e6-2f36-c627-bf0d46cfb165
---

# attributes disk | Microsoft Learn

Displays, sets, or clears the attributes of a disk. When this command is used to display the current attributes of a disk, the startup disk attribute denotes the disk used to start the computer. For a dynamic mirror, it displays the disk that contains the boot plex of the boot volume.

Important

A disk must be selected for the **attributes disk** command to succeed. Use the **select disk** command to select a disk and shift the focus to it.

## Syntax

```
attributes disk [{set | clear}] [readonly] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| set | Sets the specified attribute of the disk with focus. |
| clear | Clears the specified attribute of the disk with focus. |
| readonly | Specifies that the disk is read-only. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To view the attributes of the selected disk, type:

```
attributes disk
```

To set the selected disk as read-only, type:

```
attributes disk set readonly
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select disk command](select-disk)

-----

---
layout: Conceptual
title: attributes volume | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/attributes-volume
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the attributes volume command, which displays, sets, or clears the attributes of a volume.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: f1d04f2f-5a63-89cf-cfb1-04402e6ee202
document_version_independent_id: a2123510-6feb-f1c5-5d68-6ee0d3e1fecd
updated_at: 2025-10-22T17:33:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/attributes-volume.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/4282dd47a285a65de44c1512e8e9abd2384582a8/WindowsServerDocs/administration/windows-commands/attributes-volume.md
git_commit_id: 4282dd47a285a65de44c1512e8e9abd2384582a8
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 244
asset_id: administration/windows-commands/attributes-volume
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/attributes-volume.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 7645ccd5-0f23-fcb5-e71a-e17bab840776
---

# attributes volume | Microsoft Learn

Displays, sets, or clears the attributes of a volume.

## Syntax

```
attributes volume [{set | clear}] [{hidden | readonly | nodefaultdriveletter | shadowcopy}] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| set | Sets the specified attribute of the volume with focus. |
| clear | Clears the specified attribute of the volume with focus. |
| readonly | Specifies that the volume is read-only. |
| hidden | Specifies that the volume is hidden. |
| nodefaultdriveletter | Specifies that the volume does not receive a drive letter by default. |
| shadowcopy | Specifies that the volume is a shadow copy volume. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Remarks

- On basic master boot record (MBR) disks, the **hidden**, **readonly**, and **nodefaultdriveletter** parameters apply to all volumes on the disk.
- On basic GUID partition table (GPT) disks, and on dynamic MBR and gpt disks, the **hidden**, **readonly**, and **nodefaultdriveletter** parameters apply only to the selected volume.
- A volume must be selected for the **attributes volume** command to succeed. Use the **select volume** command to select a volume and shift the focus to it.

## Examples

To display the current attributes on the selected volume, type:

```
attributes volume
```

To set the selected volume as hidden and read-only, type:

```
attributes volume set hidden readonly
```

To remove the hidden and read-only attributes on the selected volume, type:

```
attributes volume clear hidden readonly
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select volume command](select-volume)

-----
-----

---
layout: Conceptual
title: automount | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/automount
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the automount command, which enables or disables the automount feature.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: f0a74de9-f1e4-5155-1f15-a032791a2794
document_version_independent_id: 37116043-c59b-78ad-fef4-038ff4141940
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/automount.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/automount.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 226
asset_id: administration/windows-commands/automount
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/automount.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
platformId: 0b79817c-2f79-f09a-ea08-a7aabebafa61
---

# automount | Microsoft Learn

- [Command-Line Syntax Key](command-line-syntax-key)

Important

In storage area network (SAN) configurations, disabling automount prevents Windows from automatically mounting or assigning drive letters to any new basic volumes that are visible to the system.

## Syntax

automount [ { enable | disable | scrub } ] [noerr]

### Parameters

| Parameter | Description |
| --- | --- |
| enable | Enables Windows to automatically mount new basic and dynamic volumes that are added to the system and to assign them drive letters. |
| disable | Prevents Windows from automatically mounting any new basic and dynamic volumes that are added to the system.<br>**Note**: Disabling automount can cause failover clusters to fail the storage portion of the Validate a Configuration Wizard. |
| scrub | Removes volume mount point directories and registry settings for volumes that are no longer in the system. This prevents volumes that were previously in the system from being automatically mounted and given their former volume mount point(s) when they are added back to the system. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To see if the automount feature is enabled, type the following commands from within the diskpart command:

```
automount
```

To enable the automount feature, type:

```
automount enable
```

To disable the automount feature, type:

```
automount disable
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [diskpart commands](/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc770877%28v%3dws.11%29)

-----
-----

# break | Microsoft Learn

Important

This command is no longer in use. It is included only to preserve compatibility with existing MS-DOS files, but it has no effect at the command line because the functionality is automatic.

Sets or clears extended CTRL+C checking on MS-DOS systems. If used without parameters, **break** displays the existing setting value.

If command extensions are enabled and running on the Windows platform, inserting the **break** command into a batch file enters a hard-coded breakpoint if being debugged by a debugger.

## Syntax

```
break=[on|off]
```

Note

Because the break command has no effect, it is often used to create empty files or delete the content of an existing file. For example:

```
rem -- cleans the content of the file --
break>log
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [break command](break)

-----
-----

# clean | Microsoft Learn

Removes all partitions or volume formatting from the disk with focus.

Note

For a PowerShell version of this command, see [clear-disk command](/en-us/powershell/module/storage/clear-disk).

## Syntax

```
clean [all]
```

### Parameters

| Parameter | Description |
| --- | --- |
| all | Specifies that each and every sector on the disk is set to zero, which completely deletes all data contained on the disk. |

#### Remarks

- On master boot record (MBR) disks, only the MBR partitioning information and hidden sector information is overwritten.
- On GUID Partition Table (gpt) disks, the gpt partitioning information, including the Protective MBR, is overwritten. There is no hidden sector information.
- A disk must be selected for this operation to succeed. Use the **select disk** command to select a disk and shift the focus to it.

## Examples

To remove all formatting from the selected disk, type:

```
clean
```

## Related links

- [clear-disk command](/en-us/powershell/module/storage/clear-disk)
- [Command-Line Syntax Key](command-line-syntax-key)

-----
-----

# compact vdisk | Microsoft Learn

Reduces the physical size of a dynamically expanding virtual hard disk (VHD) file. This parameter is useful because dynamically expanding VHDs increase in size as you add files, but they do not automatically reduce in size when you delete files.

## Syntax

```
compact vdisk
```

### Remarks

- A dynamically expanding VHD must be selected for this operation to succeed. Use the [select vdisk command](select-vdisk) to select a VHD and shift the focus to it.
- You can only use compact dynamically expanding VHDs that are detached or attached as read-only.

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [attach vdisk command](attach-vdisk)
- [detail vdisk command](detail-vdisk)
- [Detach vdisk command](detach-vdisk)
- [expand vdisk command](expand-vdisk)
- [Merge vdisk command](merge-vdisk)
- [select vdisk command](select-vdisk)
- [list command](list)

-----
-----

# convert | Microsoft Learn

Converts a disk from one disk type to another.

## Syntax

```
convert basic
convert dynamic
convert gpt
convert mbr
```

### Parameters

| Parameter | Description |
| --- | --- |
| [convert basic command](convert-basic) | Converts an empty dynamic disk into a basic disk. |
| [convert dynamic command](convert-dynamic) | Converts a basic disk into a dynamic disk. |
| [convert gpt command](convert-gpt) | Converts an empty basic disk with the master boot record (MBR) partition style into a basic disk with the GUID partition table (GPT) partition style. |
| [convert mbr command](convert-mbr) | Converts an empty basic disk with the GUID Partition Table (GPT) partition style into a basic disk with the master boot record (MBR) partition style. |

-----

# convert basic | Microsoft Learn

Converts an empty dynamic disk to a basic disk. A dynamic disk must be selected for this operation to succeed. Use the [select disk command](select-disk) to select a dynamic disk and shift the focus to it.

Important

The disk must be empty to convert it to a basic disk. Back up your data, and then delete all partitions or volumes before converting the disk.

Note

For instructions regarding how to use this command, see [Change a Dynamic Disk Back to a Basic Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc755238%28v=ws.11%29)).

## Syntax

```
convert basic [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To convert the selected dynamic disk to basic, type:

```
convert basic
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [convert command](convert)


# convert dynamic | Microsoft Learn

Converts a basic disk into a dynamic disk. A basic disk must be selected for this operation to succeed. Use the [select disk command](select-disk) to select a basic disk and shift the focus to it.

Note

For instructions regarding how to use this command, see [Change a Dynamic Disk Back to a Basic Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc755238%28v=ws.11%29)).

## Syntax

```
convert dynamic [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

#### Remarks

- Any existing partitions on the basic disk become simple volumes.

## Examples

To convert a basic disk into a dynamic disk, type:

```
convert dynamic
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [convert command](convert)

-----

# convert gpt | Microsoft Learn

Converts an empty basic disk with the master boot record (MBR) partition style into a basic disk with the GUID partition table (GPT) partition style. A basic MBR disk must be selected for this operation to succeed. Use the [select disk command](select-disk) to select a basic disk and shift the focus to it.

Important

The disk must be empty to convert it to a basic disk. Back up your data, and then delete all partitions or volumes before converting the disk. The required minimum disk size for conversion to GPT is 128 megabytes.

Note

For instructions regarding how to use this command, see [Change a Master Boot Record Disk into a GUID Partition Table Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc725671%28v=ws.11%29).

## Syntax

```
convert gpt [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To convert a basic disc from MBR partition style to GPT partition style, type:

```
convert gpt
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [convert command](convert)

-----

# convert mbr | Microsoft Learn

Converts an empty basic disk with the GUID Partition Table (GPT) partition style into a basic disk with the master boot record (MBR) partition style. A basic disk must be selected for this operation to succeed. Use the [select disk command](select-disk) to select a basic disk and shift the focus to it.

Important

The disk must be empty to convert it to a basic disk. Back up your data, and then delete all partitions or volumes before converting the disk.

Note

For instructions regarding how to use this command, see [Change a GUID Partition Table Disk into a Master Boot Record Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc725797%28v=ws.11%29).

## Syntax

```
convert mbr [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To convert a basic disc from GPT partition style to MBR partition style, type&gt;:

```
convert mbr
```

## Related links

- [convert command](convert)

-----
-----

# create | Microsoft Learn

Creates a partition or shadow on a disk, a volume on one or more disks, or a virtual hard disk (VHD). If you're using this command to create a volume on the shadow disk, you must already have at least one volume in the shadow copy set.

## Syntax

```
create partition
create volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [create partition primary command](create-partition-primary) | Creates a primary partition on the basic disk with focus. |
| [create partition efi command](create-partition-efi) | Creates an Extensible Firmware Interface (EFI) system partition on a GUID Partition Table (gpt) disk on Itanium-based computers. |
| [create partition extended command](create-partition-extended) | Creates an extended partition on the disk with focus. |
| [create partition logical command](create-partition-logical) | Creates a logical partition in an existing extended partition. |
| [create partition msr command](create-partition-msr) | Creates a Microsoft Reserved (MSR) partition on a GUID partition table (gpt) disk. |
| [create volume simple command](create-volume-simple) | Creates a simple volume on the specified dynamic disk. |
| [create volume mirror command](create-volume-mirror) | Creates a volume mirror by using the two specified dynamic disks. |
| [create volume raid command](create-volume-raid) | Creates a RAID-5 volume using three or more specified dynamic disks. |
| [create volume stripe command](create-volume-stripe) | Creates a striped volume using two or more specified dynamic disks. |

-----
-----

# delete | Microsoft Learn

Deletes a partition or a volume. It also deletes a dynamic disk from the list of disks.

## Syntax

```
delete disk
delete partition
delete volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [Delete disk](delete-disk) | Deletes a missing dynamic disk from the list of disks. |
| [Delete partition](delete-partition) | Deletes a partition. |
| [Delete volume](delete-volume) | Deletes a volume. |

-----

# delete disk | Microsoft Learn

Deletes a missing dynamic disk from the list of disks.

Note

For detailed instructions about how to use this command, see [Remove a Missing Dynamic Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc753029%28v=ws.11%29).

## Syntax

```
delete disk [noerr] [override]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |
| override | Enables DiskPart to delete all simple volumes on the disk. If the disk contains half of a mirrored volume, the half of the mirror on the disk is deleted. The delete disk override command fails if the disk is a member of a RAID-5 volume. |

## Examples

To delete a missing dynamic disk from the list of disks, type:

```
delete disk
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [delete command](delete)

-----

# delete partition | Microsoft Learn

Deletes the partition with focus. Before you begin, you must select a partition for this operation to succeed. Use the [select partition](select-partition) command to select a partition and shift the focus to it.

Warning

Deleting a partition on a dynamic disk can delete all dynamic volumes on the disk, destroying any data and leaving the disk in a corrupt state.

You can't delete the system partition, boot partition, or any partition that contains the active paging file or crash dump information.

## Syntax

```
delete partition [noerr] [override]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |
| override | Enables DiskPart to delete any partition regardless of type. Typically, DiskPart only permits you to delete known data partitions. |

#### Remarks

- To delete a dynamic volume, always use the [delete volume](delete-volume) command instead.
- Partitions can be deleted from dynamic disks, but they shouldn't be created. For example, it's possible to delete an unrecognized GUID Partition Table (GPT) partition on a dynamic GPT disk. Deleting such a partition doesn't cause the resulting free space to become available. Instead, This command is intended to allow you to reclaim space on a corrupted offline dynamic disk in an emergency situation where the [clean](clean) command in DiskPart can't be used.

## Examples

To delete the partition with focus, type:

```
delete partition
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select partition](select-partition)
- [delete command](delete)
- [delete volume command](delete-volume)
- [clean command](clean)

-----

# delete volume | Microsoft Learn

Deletes the selected volume. Before you begin, you must select a volume for this operation to succeed. Use the [select volume](select-volume) command to select a volume and shift the focus to it.

Important

You can't delete the system volume, boot volume, or any volume that contains the active paging file or crash dump (memory dump).

## Syntax

```
delete volume [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To delete the volume with focus, type:

```
delete volume
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select volume](select-volume)
- [delete command](delete)

-----
-----

# detach vdisk | Microsoft Learn

Stops the selected virtual hard disk (VHD) from appearing as a local hard disk drive on the host computer. When a VHD is detached, you can copy it to other locations. Before you begin, you must select a VHD for this operation to succeed. Use the [select vdisk](select-vdisk) command to select a VHD and shift the focus to it.

## Syntax

```
detach vdisk [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To detach the selected VHD, type:

```
detach vdisk
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [attach vdisk command](attach-vdisk)
- [compact vdisk command](compact-vdisk)
- [detail vdisk command](detail-vdisk)
- [expand vdisk command](expand-vdisk)
- [Merge vdisk command](merge-vdisk)
- [select vdisk command](select-vdisk)
- [list command](list)

-----
-----

# detail | Microsoft Learn

Displays information about the selected disk, partition, volume, or virtual hard disk (VHD).

## Syntax

```
detail disk
detail partition
detail volume
detail vdisk
```

### Parameters

| Parameter | Description |
| --- | --- |
| [Detail disk](detail-disk) | Displays the properties of the selected disk and the volumes on that disk. |
| [Detail partition](detail-partition) | Displays the properties of the selected partition. |
| [Detail volume](detail-volume) | Displays the disks on which the current volume resides. |
| [Detail vdisk](detail-vdisk) | Displays the properties of the selected VHD. |

-----

# detail disk | Microsoft Learn

Displays the properties of the selected disk and the volumes on that disk. Before you begin, you must select a disk for this operation to succeed. Use the [select disk](select-disk) command to select a disk and shift the focus to it. If you select a virtual hard disk (VHD), this command will show the disk's bus type as *Virtual*.

## Syntax

```
detail disk
```

## Examples

To see the properties of the selected disk, and information about the volumes in the disk, type:

```
detail disk
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [detail command](detail)

-----

# detail partition | Microsoft Learn

Displays the properties of the selected partition. Before you begin, you must select a partition for this operation to succeed. Use the [select partition](select-partition) command to select a partition and shift the focus to it.

## Syntax

```
detail partition
```

## Examples

To see the properties of the selected partition, type:

```
detail partition
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [detail command](detail)

-----

# detail vdisk | Microsoft Learn

Displays the properties of the selected virtual hard disk (VHD). Before you begin, you must select a VHD for this operation to succeed. Use the [select vdisk](select-vdisk) command to select a VHD and shift the focus to it.

## Syntax

```
detail vdisk
```

## Examples

To see details about the selected VHD, type:

```
detail vdisk
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [detail command](detail)
- [attach vdisk command](attach-vdisk)
- [compact vdisk command](compact-vdisk)
- [detach vdisk command](detach-vdisk)
- [expand vdisk command](expand-vdisk)
- [merge vdisk command](merge-vdisk)
- [select vdisk](select-vdisk)
- [list command](list)

-----

# detail volume | Microsoft Learn

Displays the disks on which the current volume resides. Before you begin, you must select a volume for this operation to succeed. Use the [select volume](select-volume) command to select a volume and shift the focus to it. The volume details aren't applicable to read-only volumes, such as a DVD-ROM or CD-ROM drive.

## Syntax

```
detail volume
```

## Examples

To see all the disks in which the current volume resides, type:

```
detail volume
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select volume](select-volume)
- [detail command](detail)

-----
-----

# exit | Microsoft Learn

Exits the command interpreter or the current batch script.

## Syntax

```
exit [/b] [<exitcode>]
```

### Parameters

| Parameter | Description |
| --- | --- |
| /b | Exits the current batch script instead of exiting Cmd.exe. If executed from outside a batch script, exits Cmd.exe. |
| `<exitcode>` | Specifies a numeric number. If **/b** is specified, the ERRORLEVEL environment variable is set to that number. If you are quitting the command interpreter, the process exit code is set to that number. |
| /? | Displays help at the command prompt. |

## Examples

To close the command interpreter, type:

```
exit
```

-----
-----

# expand vdisk | Microsoft Learn

Expands a virtual hard disk (VHD) to a specified size.

A VHD must be selected and detached for this operation to succeed. Use the [select vdisk command](select-vdisk) to select a volume and shift the focus to it.

## Syntax

```
expand vdisk maximum=<n>
```

### Parameters

| Parameter | Description |
| --- | --- |
| maximum=`<n>` | Specifies the new size for the VHD in megabytes (MB). |

### Examples

To expand the selected VHD to 20 GB, type:

```
expand vdisk maximum=20000
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select vdisk command](select-vdisk)
- [attach vdisk command](attach-vdisk)
- [compact vdisk command](compact-vdisk)
- [detach vdisk command](detach-vdisk)
- [detail vdisk command](detail-vdisk)
- [merge vdisk command](merge-vdisk)
- [list command](list)

-----
-----

# extend | Microsoft Learn

Extends the volume or partition with focus and its file system into free (unallocated) space on a disk.

## Syntax

```
extend [size=<n>] [disk=<n>] [noerr]
extend filesystem [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| size=`<n>` | Specifies the amount of space in megabytes (MB) to add to the current volume or partition. If no size is given, all of the contiguous free space that is available on the disk is used. |
| disk=`<n>` | Specifies the disk on which the volume or partition is extended. If no disk is specified, the volume or partition is extended on the current disk. |
| filesystem | Extends the file system of the volume with focus. For use only on disks where the file system was not extended with the volume. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

#### Remarks

- On basic disks, the free space must be on the same disk as the volume or partition with focus. It must also immediately follow the volume or partition with focus (that is, it must start at the next sector offset).
- On dynamic disks with simple or spanned volumes, a volume can be extended to any free space on any dynamic disk. Using this command, you can convert a simple dynamic volume into a spanned dynamic volume. Mirrored, RAID-5 and striped volumes cannot be extended.
- If the partition was previously formatted with the NTFS file system, the file system is automatically extended to fill the larger partition and no data loss will occur.
- If the partition was previously formatted with a file system other than NTFS, the command fails with no change to the partition.
- If the partition was not previously formatted with a file system, the partition will still be extended.
- The partition must have an associated volume before it can be extended.

## Examples

To extend the volume or partition with focus by 500 megabytes, on disk 3, type:

```
extend size=500 disk=3
```

To extend the file system of a volume after it was extended, type:

```
extend filesystem
```

-----
-----

# filesystems | Microsoft Learn

Displays information about the current file system of the volume with focus and lists the file systems that are supported for formatting the volume.

A volume must be selected for this operation to succeed. Use the [select volume command](select-volume) to select a volume and shift the focus to it.

## Syntax

```
filesystems
```

-----
-----

# format | Microsoft Learn

The **format** command formats a drive to accept Windows files. You must be a member of the Administrators group to format a hard drive.

Note

You can also use the **format** command, with different parameters, from the Recovery Console. For more information about the Recovery Console, see [Windows Recovery Environment (Windows RE)](/en-us/windows-hardware/manufacture/desktop/windows-recovery-environment--windows-re--technical-reference).

## Syntax

```
format volume [/FS:file-system] [/V:label] [/Q] [/L[:state]] [/A:size] [/C] [/I:state] [/X] [/P:passes] [/S:state]
format volume [/V:label] [/Q] [/F:size] [/P:passes]
format volume [/V:label] [/Q] [/T:tracks /N:sectors] [/P:passes]
format volume [/V:label] [/Q] [/P:passes]
format volume [/Q]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<volume>` | Specifies the mount point, volume name, or drive letter (followed by a colon) of the drive that you want to format. If you don't specify any of the following command-line options, **format** uses the volume type to determine the default format for the disk. |
| /FS:`<filesystem>` | Specifies the type of file system (FAT, FAT32, NTFS, exFAT, ReFS, or UDF). |
| /V:`<label>` | Specifies the volume label. If you omit the **/V** command-line option or use it without specifying a volume label, **format** prompts you for the volume label after the formatting is complete. Use the syntax **/V:** to prevent the prompt for a volume label. If you use a single **format** command to format more than one disk, all of the disks are given the same volume label. |
| /Q | Performs a quick format. Deletes the file table and the root directory of a previously formatted volume, but doesn't perform a sector-by-sector scan for bad areas. You should use the **/Q** command-line option to format only previously formatted volumes that you know are in good condition. **/Q** overrides **/P**. |
| /C | **NTFS Only**: Files created on the new volume are compressed by default. |
| /X | Forces the volume to dismount, if necessary, before it's formatted. Any open handles to the volume are no longer be valid. |
| /R | **NTFS Only**: Files created on the new volume are compressed by default. |
| /D | UDF 2.50 only. Metadata is duplicated. |
| /L:`<state>` | NTFS only. Overrides the default size of file record. By default, a nontiered volume is formatted with small size file records and a tiered volume is formatted with large size file records. **/L** and **/L:enable** forces format to use large size file records and **/L:disable** forces format to use small size file records. |
| /A:`<size>` | Specifies the allocation unit size to use on FAT, FAT32, NTFS, exFAT, or ReFS volumes. If you don't specify *unit size*, it's chosen based on volume size. Default settings are recommended for general use. The following list presents valid values for each type of file system *unit size*:<br>- **FAT and FAT32**: `512`, `1024`, `2048`, `4096`, `8192`, `16K`, `32K`, `64K`. Also `128K` and `256K` for a sector size greater than 512 bytes.<br>- **NTFS**: `512`, `1024`, `2048`, `4096`, `8192`, `16K`, `32K`, `64K`, `128K`, `256K`, `512K`, `1M`, `2M`<br>- **exFAT**: `12`, `1024`, `2048`, `4096`, `8192`, `16K`, `32K`, `64K`, `128K`, `256K`, `512K`, `1M`, `2M`, `4M`, `8M`, `16M`, `32M`<br>- **ReFS**: `4096`, `64K` |
| /F:`<size>` | Specifies the size of the floppy disk to format. When possible, use this command-line option instead of the **/T** and **/T** command-line options. Windows accepts the following values for size:<br>- `1440` or `1440k` or `1440kb`<br>- `1.44` or `1.44m` or `1.44mb`<br>- `1.44-MB`, `double-sided`, `quadruple-density`, `3.5-inch disk` |
| /T:`<tracks>` | Specifies the number of tracks on the disk. When possible, use the **/F** command-line option instead. If you use the **/T** option, you must also use the **/N** option. These options together provide an alternative method of specifying the size of the disk that's being formatted. This option isn't valid with the **/F** option. |
| /N:`<sectors>` | Specifies the number of sectors per track. When possible, use the **/F** command-line option instead of **/N**. If you use **/N**, you must also use **/T**. These two options together provide an alternative method of specifying the size of the disk that's being formatted. This option isn't valid with the **/F** option. |
| /P:`<count>` | Zero every sector on the volume. After that, the volume will be overwritten **count** times using a different random number each time. If **count** is zero, no other overwrites are made after zeroing every sector. This switch is ignored when **/Q** is specified. |
| /S:`<state>` | Specifies support for short filenames. State is either **enable** or **disable**. Short names are disabled by default. |
| /TXF:`<state>` | Specifies TxF is enabled/disabled. State is either **enable** or **disable**. TxF is enabled by default |
| /I:`<state>` | **ReFS Only**: Specifies whether integrity should be enabled on the new volume. State is either **enable** or **disable**. Integrity is enabled on storage that supports data redundancy by default. |
| /DAX:`<state>` | **NTFS Only**: Enable direct access storage (DAX) mode for this volume. In DAX mode, the volume is accessed via the memory bus, boosting IO performance. A volume can be formatted with DAX mode only if the hardware is DAX capable. State is either **enable** or **disable**. **/DAX** is considered the same as **/DAX:enable**. |
| /LogSize::`<size>` | **NTFS Only**: Specifies the size for NTFS log file in kilobytes. The minimum supported size is 2MB, so specifying a size smaller than 2MB results in a 2MB log file. Zero indicates the default value. The default value generally depends on the volume size. |
| /NoRepairLogs | **NTFS Only**: Disables NTFS repair logs. If the **spotfix** flag for chkdsk is specified, then the **/NoReairLogs** parameter doesn't work. |
| /NoTrim | Skips sending trim (delete notification) during a format. |
| /DevDrv | **ReFS Only**: Formats the volume as a dev drive. A dev drive or a developer volume is a volume optimized for performance of developer scenarios. Gives administrators control over what mini-filters are attached to this volume. |
| /SHA256Checksums | **ReFS Only**: Uses SHA-256 in all operations involving checksums. |
| /Y | Doesn't prompt to force the volume to dismount and assumes an empty label when no label is specified. |
| /? | Displays help at the command prompt. |

## Remarks

- The **format** command creates a new root directory and file system for the disk. It can also check for bad areas on the disk, and it can delete all data on the disk. To be able to use a new disk, you must first use this command to format the disk.
- After formatting a floppy disk, **format** displays the following message:

    `Volume label (11 characters, ENTER for none)?`

    To add a volume label, type up to 11 characters (including spaces). If you don't want to add a volume label to the disk, press ENTER.
- When you use the **format** command to format a hard disk, a warning message similar to the following displays:

    ```
    WARNING, ALL DATA ON NON-REMOVABLE DISK
    DRIVE x: WILL BE LOST!
    Proceed with Format (Y/N)? _
    ```

    To format the hard disk, press **Y**. If you don't want to format the disk, press **N**.
- FAT file systems restrict the number of clusters to no more than 65526. FAT32 file systems restrict the number of clusters to between 65527 and 4177917.
- NTFS compression isn't supported for allocation unit sizes above 4096.

    Note

    **Format** will immediately stop processing if it determines that the previous requirements can't be met using the specified cluster size.
- When formatting is complete, **format** displays messages that show the total disk space, the spaces marked as defective, and the space available for your files.
- You can speed up the formatting process by using the **/q** command-line option. Use this option only if there are no bad sectors on your hard disk.
- You shouldn't use the **format** command on a drive that was prepared by using the **subst** command. You can't format disks over a network.
- The following table lists each exit code and a brief description of its meaning.

    | Exit code | Description |
    | --- | --- |
    | 0 | The format operation was successful. |
    | 1 | Incorrect parameters were supplied. |
    | 4 | A fatal error occurred (which is any error other than 0, 1, or 5). |
    | 5 | The user pressed N in response to the prompt "Proceed with Format (Y/N)?" to stop the process. |

    You can check these exit codes by using the ERRORLEVEL environment variable with the **if** batch command.

## Examples

To format a new floppy disk in drive A using the default size, type:

```
format a:
```

To perform a quick format operation on a previously formatted floppy disk in drive A, type:

```
format a: /q
```

To format a floppy disk in drive A and assign it the volume label *DATA*, type:

```
format a: /v:DATA
```

-----
-----

# gpt | Microsoft Learn

On basic GUID partition table (gpt) disks, this command assigns the gpt attribute(s) to the partition with focus. Gpt partition attributes give additional information about the use of the partition. Some attributes are specific to the partition type GUID.

You must choose a basic gpt partition for this operation to succeed. Use the [select partition command](select-partition) to select a basic gpt partition and shift the focus to it.

Caution

Changing the gpt attributes might cause your basic data volumes to fail to be assigned drive letters, or to prevent the file system from mounting. We strongly recommend that you don't change the gpt attributes unless you're an original equipment manufacturer (OEM) or an IT professional who's experienced with gpt disks.

## Syntax

```
gpt attributes=<n>
```

### Parameters

| Parameter | Description |
| --- | --- |
| attributes=`<n>` | Specifies the value for the attribute that you want to apply to the partition with focus. The gpt attribute field is a 64-bit field that contains two subfields. The higher field is interpreted only in the context of the partition ID, while the lower field is common to all partition IDs. Accepted values include:<br>- **0x0000000000000001** - Specifies that the partition is required by the computer to function properly.<br>- **0x8000000000000000** - Specifies that the partition won't receive a drive letter by default when the disk is moved to another computer, or when the disk is seen for the first time by a computer.<br>- **0x4000000000000000** - Hides a partition's volume so it's not detected by the mount manager.<br>- **0x2000000000000000** - Specifies that the partition is a shadow copy of another partition.<br>- **0x1000000000000000** - Specifies that the partition is read-only. This attribute prevents the volume from being written to.<br><br><br>For more information about these attributes, see the attributes section at [create_PARTITION_PARAMETERS Structure](/en-us/windows/win32/api/vds/ns-vds-create_partition_parameters). |

#### Remarks

- The EFI System partition contains only those binaries necessary to start the operating system. This makes it easy for OEM binaries or binaries specific to an operating system to be placed in other partitions.

### Examples

To prevent the computer from automatically assigning a drive letter to the partition with focus, while moving a gpt disk, type:

```
gpt attributes=0x8000000000000000
```

## Related links

- [select partition command](select-partition)
- [create_PARTITION_PARAMETERS Structure](/en-us/windows/win32/api/vds/ns-vds-create_partition_parameters)

-----
-----

# import diskpart | Microsoft Learn

Imports a foreign disk group into the disk group of the local computer. This command imports every disk that is in the same group as the disk with focus.

> 
> [IMPORTANT] Before you can use this command, you must use the [select disk command](select-disk) to select a dynamic disk in a foreign disk group and shift the focus to it.

## Syntax

```
import [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To import every disk that is in the same disk group as the disk with focus into the disk group of the local computer, type:

```
import
```

## Related links

- [diskpart command](diskpart)

-----
-----

# inactive | Microsoft Learn

Marks the system partition or boot partition with focus as inactive on basic master boot record (MBR) disks.

An active system or boot partition must be selected for this operation to succeed. Use the [select partition command](select-partition) command to select the active partition and shift the focus to it.

Caution

Your computer might not start without an active partition. Don't mark a system or boot partition as inactive unless you are an experienced user with a thorough understanding of the Windows family of operating systems.

If you're unable to start your computer after marking the system or boot partition as inactive, insert the Windows Setup CD in the CD-ROM drive, restart the computer, and then repair the partition using the **fixmbr** and **fixboot** commands in the Recovery Console.

After you mark the system partition or boot partition as inactive, your computer starts from the next option specified in the BIOS, such as the CD-ROM drive or a Pre-Boot eXecution Environment (PXE).

## Syntax

```
inactive
```

### Examples

```
inactive
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select partition command](select-partition)
- [Advanced troubleshooting for Windows boot problems](/en-us/windows/client-management/advanced-troubleshooting-boot-problems)

-----
-----

# list | Microsoft Learn

Displays a list of disks, of partitions in a disk, of volumes in a disk, or of virtual hard disks (VHDs).

## Syntax

```
list { disk | partition | volume | vdisk }
```

### Parameters

| Parameter | Description |
| --- | --- |
| disk | Displays a list of disks and information about them, such as their size, amount of available free space, whether the disk is a basic or dynamic disk, and whether the disk uses the master boot record (MBR) or GUID partition table (GPT) partition style. |
| partition | Displays the partitions listed in the partition table of the current disk. |
| volume | Displays a list of basic and dynamic volumes on all disks. |
| vdisk | Displays a list of the VHDs that are attached and/or selected. This command lists detached VHDs if they are currently selected; however, the disk type is set to Unknown until the VHD is attached. The VHD marked with an asterisk (\*) has focus. |

#### Remarks

- When listing partitions on a dynamic disk, the partitions might not correspond to the dynamic volumes on the disk. This discrepancy occurs because dynamic disks contain entries in the partition table for the system volume or boot volume (if present on the disk). They also contain a partition that occupies the remainder of the disk in order to reserve the space for use by dynamic volumes.
- The object marked with an asterisk (\*) has focus.
- When listing disks, if a disk is missing, its disk number is prefixed with M. For example, the first missing disk is numbered *M0*.

### Examples

```
list disk
list partition
list volume
list vdisk
```

-----
-----

# merge vdisk | Microsoft Learn

Merges a differencing virtual hard disk (VHD) with its corresponding parent VHD. The parent VHD will be modified to include the modifications from the differencing VHD. This command modifies the parent VHD. As a result, other differencing VHDs that are dependent on the parent will no longer be valid.

Important

You must choose and detach a VHD for this operation to succeed. Use the **select vdisk** command to select a VHD and shift the focus to it.

## Syntax

```
merge vdisk depth=<n>
```

### Parameters

| Parameter | Description |
| --- | --- |
| depth=`<n>` | Indicates the number of parent VHD files to merge together. For example, `depth=1` indicates that the differencing VHD will be merged with one level of the differencing chain. |

### Examples

To merge a differencing VHD with its parent VHD, type:

```
merge vdisk depth=1
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [attach vdisk command](attach-vdisk)
- [compact vdisk command](compact-vdisk)
- [detail vdisk command](detail-vdisk)
- [detach vdisk command](detach-vdisk)
- [expand vdisk command](expand-vdisk)
- [select vdisk command](select-vdisk)
- [list command](list)

-----
-----

# offline | Microsoft Learn

Takes an online disk or volume to the offline state.

## Syntax

```
offline disk
offline volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [offline disk](offline-disk) | Takes the online disk with focus to the offline state. |
| [offline volume](offline-volume) | Takes the online volume with focus to the offline state. |

-----

# offline disk | Microsoft Learn

Takes the online disk with focus to the offline state. If a dynamic disk in a disk group is taken offline, the status of the disk changes to **missing** and the group shows a disk that's offline. The missing disk is moved to the invalid group. If the dynamic disk is the last disk in the group, then the status of the disk changes to **offline**, and the empty group is removed.

Note

A disk must be selected for the **offline disk** command to succeed. Use the [select disk](select-disk) command to select a disk and shift the focus to it.

This command also works on disks in SAN online mode by changing the SAN mode to offline.

## Syntax

```
offline disk [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To take the disk with focus offline, type:

```
offline disk
```

-----

# offline volume | Microsoft Learn

Takes the online volume with focus to the offline state.

Note

A volume must be selected for the **offline volume** command to succeed. Use the [select volume](select-volume) command to select a disk and shift the focus to it.

## Syntax

```
offline volume [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To take the disk with focus offline, type:

```
offline volume
```

-----
-----

# online | Microsoft Learn

Takes an offline disk or volume to the online state.

## Syntax

```
online disk
online volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [online disk](online-disk) | Takes the offline disk with focus to the online state. |
| [online volume](online-volume) | Takes the offline volume with focus to the online state. |

-----

# online disk | Microsoft Learn

Takes the offline disk to the online state. For basic disks, this command attempts to bring online the selected disk and all volumes on that disk. For dynamic disks, this command attempts to bring online all disks that are not marked as foreign on the local computer. It also attempts to bring online all volumes on the set of dynamic disks.

If a dynamic disk in a disk group is brought online and it's the only disk in the group, then the original group is recreated and the disk is moved to that group. If there are other disks in the group and they're online, then the disk is simply added back into the group. If the group of a selected disk contains mirrored or RAID-5 volumes, this command also resynchronizes these volumes.

Note

A disk must be selected for the **online disk** command to succeed. Use the [select disk](select-disk) command to select a disk and shift the focus to it.

Important

This command will fails if it's used on a read-only disk.

## Syntax

```
online disk [noerr]
```

### Parameters

For instructions about using this command, see [Reactivate a Missing or Offline Dynamic Disk](/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc732026%28v=ws.11%29).

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To take the disk with focus online, type:

```
online disk
```

-----

# online volume | Microsoft Learn

Takes the offline volume to the online state. This command works on volumes that have failed, are failing, or are in failed redundancy state.

Note

A volume must be selected for the **online volume** command to succeed. Use the [select volume](select-volume) command to select a volume and shift the focus to it.

Important

This command will fails if it's used on a read-only disk.

## Syntax

```
online volume [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To take the volume with focus online, type:

```
online volume
```

-----
-----

# recover | Microsoft Learn

Recovers readable information from a bad or defective disk. This command reads a file, sector-by-sector, and recovers data from the good sectors. Data in bad sectors is lost. Because all data in bad sectors is lost when you recover a file, you should recover only one file at a time.

Bad sectors reported by the **chkdsk** command were marked as bad when your disk was prepared for operation. They pose no danger, and **recover** does not affect them.

## Syntax

```
recover [<drive>:][<path>]<filename>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `[<drive>:][<path>]<filename>` | Specifies the file name (and the location of the file if it is not in the current directory) you want to recover. *Filename* is required and wildcards aren't supported. |
| /? | Displays help at the command prompt. |

### Examples

To recover the file *story.txt* in the *\fiction* directory on drive D, type:

```
recover d:\fiction\story.txt
```

-----
-----

# rem | Microsoft Learn

Records comments in a script, batch, or config.sys file. If no comment is specified, **rem** adds vertical spacing.

Note

This command is internal to the command-line interpreter, cmd.exe.

## Syntax

```
rem [<comment>]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<comment>` | Specifies a string of characters to include as a comment. |
| /? | Displays help at the command prompt. |

#### Remarks

- The **rem** command doesn't display comments on the screen. To display comments on the screen, you must include the **echo on** command in your file.
- You can't use a redirection character (`<` or `>`) or pipe (`|`) in a batch file comment.
- Although you can use **rem** without a comment to add vertical spacing to a batch file, you can also use blank lines. Blank lines are ignored when a batch program is processed.

### Examples

To add vertical spacing through batch file comments, type:

```
@echo off
rem  This batch program formats and checks new disks.
rem  It is named Checknew.bat.
rem
rem echo Insert new disk in Drive B.
pause
format b: /v chkdsk b:
```

To include an explanatory comment before the **prompt** command in a config.sys file, type:

```
rem Set prompt to indicate current directory
prompt $p$g
```

To provide a comment about what a script does, type:

```
rem The commands in this script set up 3 drives.
rem The first drive is a primary partition and is
rem assigned the letter D. The second and third drives
rem are logical partitions, and are assigned letters
rem E and F.
create partition primary size=2048
assign d:
create partition extended
create partition logical size=2048
assign e:
create partition logical
assign f:
```

For multi-line comments, use conditional execution:

```
  Rem/||(
    The REM statement evaluates to success,
    so these lines will never be executed.
    Keep in mind that you will need to escape closing parentheses
    within multi-line comment blocks like shown in this example. ^)
  )
```

-----
-----

# remove | Microsoft Learn

Removes a drive letter or mount point from the volume with focus. If the all parameter is used, all current drive letters and mount points are removed. If no drive letter or mount point is specified, then DiskPart removes the first drive letter or mount point it encounters.

The remove command can also be used to change the drive letter associated with a removable drive. You can't remove the drive letters on system, boot, or paging volumes. In addition, you can't remove the drive letter for an OEM partition, any GPT partition with an unrecognized GUID, or any of the special, non-data, GPT partitions such as the EFI system partition.

Note

A volume must be selected for the **remove** command to succeed. Use the [select volume](select-volume) command to select a disk and shift the focus to it.

## Syntax

```
remove [{letter=<drive> | mount=<path> [all]}] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| letter=`<drive>` | The drive letter to remove. |
| mount=`<path>` | The mount point path to remove. |
| all | Removes all current drive letters and mount points. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To remove the d:\ drive, type:

```
remove letter=d
```

-----
-----

# repair | Microsoft Learn

Repairs the RAID-5 volume with focus by replacing the failed disk region with the specified dynamic disk.

A volume in a RAID-5 array must be selected for this operation to succeed. Use the **select volume** command to select a volume and shift the focus to it.

## Syntax

```
repair disk=<n> [align=<n>] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| disk=`<n>` | Specifies the dynamic disk that will replace the failed disk region. Where *n* must have free space greater than or equal to the total size of the failed disk region in the RAID-5 volume. |
| align=`<n>` | Aligns all volume or partition extents to the closest alignment boundary. Where *n* is the number of kilobytes (KB) from the beginning of the disk to the closest alignment boundary. |
| noerr | for scripting only. When an error is encountered, DiskPart continues to process commands as if the error didn't occur. Without this parameter, an error causes DiskPart to exit with an error code. |

### Examples

To replace the volume with focus by replacing it with dynamic disk 4, type:

```
repair disk=4
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select volume command](select-volume)

-----
-----

# rescan | Microsoft Learn

Using the diskpart command interpreter, you can locate new disks added to your computer.

## Syntax

```
rescan
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [Diskpart command](diskpart)

-----
-----

# retain | Microsoft Learn

Prepares an existing simple dynamic volume for use as a boot or system volume. If you use a master boot record (MBR) dynamic disk, this command creates a partition entry in the master boot record. If you use a GUID partition table (GPT) dynamic disk, this command creates a partition entry in the GUID partition table.

## Syntax

```
retain
```

-----
-----

# san | Microsoft Learn

Displays or sets the storage area network (san) policy for the operating system. If used without parameters, the current san policy is displayed.

## Syntax

```
san [policy={onlineAll | offlineAll | offlineShared}] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| policy={onlineAll|offlineAll|offlineShared}] | Sets the san policy for the currently booted operating system. The san policy determines whether a newly discovered disk is brought online or remains offline, and whether it becomes read/write or remains read-only. When a disk is offline, the disk layout can be read, but no volume devices are surfaced through Plug and Play. When offline no file system can be mounted on the disk. When a disk is online, one or more volume devices are installed for the disk. The following parameter can be set:<br>- **onlineAll**. Specifies that all newly discovered disks are online and made read/write. **IMPORTANT:** Specifying **onlineAll** on a server that shares disks could lead to data corruption. Therefore, you shouldn't set this policy if disks are shared among servers unless the server is part of a cluster.<br>- **offlineAll**. Specifies that all newly discovered disks except the startup disk are offline and read-only by default.<br>- **offlineShared**. Specifies that all newly discovered disks that don't reside on a shared bus (such as SCSI and iSCSI) are brought online and made read-write. Disks that are left offline are read-only by default.<br><br>For more information, see [VDS_san_POLICY Enumeration](/en-us/windows/win32/api/vds/ne-vds-vds_san_policy). |
| noerr | Used for scripting only. When an error is encountered, DiskPart continues to process commands as if the error didn't occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To view the current policy, type:

```
san
```

To make all newly discovered disks, except the startup disk, offline and read-only by default, type:

```
san policy=offlineAll
```

-----
-----

# select commands | Microsoft Learn

Shifts the focus to a disk, partition, volume, or virtual hard disk (VHD).

## Syntax

```
select disk
select partition
select vdisk
select volume
```

### Parameters

| Parameter | Description |
| --- | --- |
| [Select disk](select-disk) | Shifts the focus to a disk. |
| [Select partition](select-partition) | Shifts the focus to a partition. |
| [Select vdisk](select-vdisk) | Shifts the focus to a VHD. |
| [Select volume](select-volume) | Shifts the focus to a volume. |

#### Remarks

- If a volume is selected with a corresponding partition, the partition will be automatically selected.
- If a partition is selected with a corresponding volume, the volume will be automatically selected.

-----

# select disk | Microsoft Learn

Selects the specified disk and shifts the focus to it.

## Syntax

```
select disk={<n>|<disk path>|system|next}
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<n>` | Specifies the number of the disk to receive focus. You can view the numbers for all the disks on the computer by using the **list disk** command in DiskPart.<br>**NOTE**When configuring systems with multiple disks, don't use **select disk=0** to specify the system disk. The computer may reassign disk numbers when you reboot, and different computers with the same disk configuration can have different disk numbers. |
| `<disk path>` | Specifies the location of the disk to receive focus, for example, `PCIROOT(0)#PCI(0F02)#atA(C00T00L00)`. To view the location path of a disk, select it and then type **detail disk**. |
| system | On BIOS computers, this option specifies that disk 0 receives focus. On EFI computers, the disk containing the EFI system partition (ESP), used for the current boot, receives focus. On EFI computers, the command will fail if there's no ESP, if there's more than one ESP, or if the computer is booted from Windows Preinstallation Environment (Windows PE). |
| next | After a disk is selected, this option iterates over all disks in the disk list. When you run this option, the next disk in the list receives focus. |

## Examples

To shift the focus to disk 1, type:

```
select disk=1
```

To select a disk by using its location path, type:

```
select disk=PCIROOT(0)#PCI(0100)#atA(C00T00L01)
```

To shift the focus to the system disk, type:

```
select disk=system
```

To shift the focus to the next disk on the computer, type:

```
select disk=next
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select partition command](select-partition)
- [select vdisk command](select-vdisk)
- [select volume command](select-volume)

-----

# select partition | Microsoft Learn

Selects the specified partition and shifts the focus to it. This command can also be used to display the partition that currently has the focus in the selected disk.

## Syntax

```
select partition=<n>
```

### Parameters

| Parameter | Description |
| --- | --- |
| partition=`<n>` | The number of the partition to receive the focus. You can view the numbers for all partitions on the disk currently selected by using the **list partition** command in DiskPart. |

#### Remarks

- Before you can select a partition you must first select a disk using the **select disk** command.

    - If no partition number is specified, this option displays the partition that currently has the focus in the selected disk.
    - If a volume is selected with a corresponding partition, the partition is automatically selected.
    - If a partition is selected with a corresponding volume, the volume is automatically selected.

## Examples

To shift the focus to *partition 3*, type:

```
select partitition=3
```

To display the partition that currently has the focus in the selected disk, type:

```
select partition
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [create partition efi command](create-partition-efi)
- [create partition extended command](create-partition-extended)
- [create partition logical command](create-partition-logical)
- [create partition msr command](create-partition-msr)
- [create partition primary command](create-partition-primary)
- [delete partition command](delete-partition)
- [detail partition command](detail-partition)
- [select disk command](select-disk)
- [select vdisk command](select-vdisk)
- [select volume command](select-volume)

-----

# select vdisk | Microsoft Learn

Selects the specified virtual hard disk (VHD) and shifts the focus to it.

## Syntax

```
select vdisk file=<full path> [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| file=`<full path>` | Specifies the full path and file name of an existing VHD file. |
| noerr | Used for scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To shift the focus to the VHD named *c:\test\test.vhd*, type:

```
select vdisk file=c:\test\test.vhd
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [attach vdisk](attach-vdisk)
- [compact vdisk](compact-vdisk)
- [detach vdisk](detach-vdisk)
- [detail vdisk](detail-vdisk)
- [expand vdisk](expand-vdisk)
- [merge vdisk](merge-vdisk)
- [list](list)
- [select disk command](select-disk)
- [select partition command](select-partition)
- [select volume command](select-volume)

-----

# select volume | Microsoft Learn

Selects the specified volume and shifts the focus to it. This command can also be used to display the volume that currently has the focus in the selected disk.

## Syntax

```
select volume={<n>|<d>}
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<n>` | The number of the volume to receive the focus. You can view the numbers for all volumes on the disk currently selected by using the **list volume** command in DiskPart. |
| `<d> ` | The drive letter or mount point path of the volume to receive the focus. |

## Remarks

- If no volume is specified, this command displays the volume that currently has the focus in the selected disk.
- On a basic disk, selecting a volume also gives the focus to the corresponding partition.

    - If a volume is selected with a corresponding partition, the partition will be automatically selected.
    - If a partition is selected with a corresponding volume, the volume will be automatically selected.

## Examples

To shift the focus to *volume 2*, type:

```
select volume=2
```

To shift the focus to *Drive C*, type:

```
select volume=c
```

To shift the focus to the volume mounted on a folder named *c:\mountpath*, type:

```
select volume=c:\mountpath
```

To display the volume that currently has the focus in the selected disk, type:

```
select volume
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [add volume command](add-volume)
- [attributes volume command](attributes-volume)
- [create volume mirror command](create-volume-mirror)
- [create volume raid command](create-volume-raid)
- [create volume simple command](create-volume-simple)
- [create volume stripe command](create-volume-stripe)
- [delete volume command](delete-volume)
- [detail volume command](detail-volume)
- [fsutil volume command](fsutil-volume)
- [list volume command](list-volume)
- [offline volume command](offline-volume)
- [onine volume command](online-volume)
- [select disk command](select-disk)
- [select partition command](select-partition)
- [select vdisk command](select-vdisk)

-----
-----

# set id | Microsoft Learn

Changes the partition type field for the partition with focus. This command doesn't work on dynamic disks or on Microsoft Reserved partitions.

Important

This command is intended for use by original equipment manufacturers (OEMs) only. Changing partition type fields with this parameter might cause your computer to fail or be unable to boot. Unless you are an OEM or experienced with gpt disks, you should not change partition type fields on gpt disks by using this parameter. Instead, always use the [create partition efi](create-partition-efi) command to create EFI system partitions, the [create partition msr](create-partition-msr) command to create Microsoft Reserved partitions, and the [create partition primary](create-partition-primary) command without the ID parameter to create primary partitions on gpt disks.

## Syntax

```
set id={ <byte> | <GUID> } [override] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<byte>` | For master boot record (MBR) disks, specifies the new value for the type field, in hexadecimal form, for the partition. Any partition type **byte** can be specified with this parameter except for type 0x42, which specifies an LDM partition. Note that the leading 0x is omitted when specifying the hexadecimal partition type. |
| `<GUID>` | For GUID partition table (gpt) disks, specifies the new GUID value for the type field for the partition. Recognized GUIDs include:<br>- **EFI system partition:** c12a7328-f81f-11d2-ba4b-00a0c93ec93b<br>- **Basic data partition:** ebd0a0a2-b9e5-4433-87c0-68b6b72699c7<br><br>Any partition type GUID can be specified with this parameter except the following:<br>- **Microsoft Reserved partition:** e3c9e316-0b5c-4db8-817d-f92df00215ae<br>- **LDM metadata partition on a dynamic disk:** 5808c8aa-7e8f-42e0-85d2-e1e90434cfb3<br>- **LDM data partition on a dynamic disk:** af9b60a0-1431-4f62-bc68-3311714a69ad<br>- **Cluster metadata partition:** db97dba9-0840-4bae-97f0-ffb9a327c7e1 |
| override | forces the file system on the volume to dismount before changing the partition type. When you run the **set id** command, DiskPart attempts to lock and dismount the file system on the volume. If **override** isn't specified, and the call to lock the file system fails (for example, because there is an open handle), the operation fails. If **override** is specified, DiskPart forces the dismount even if the call to lock the file system fails, and any open handles to the volume will stop being valid. |
| noerr | Used for scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Remarks

- Other than the limitations previously mentioned, DiskPart doesn't check the validity of the value that you specify (except to ensure that it is a byte in hexadecimal form or a GUID).

## Examples

To set the type field to *0x07* and force the file system to dismount, type:

```
set id=0x07 override
```

To set the type field to be a basic data partition, type:

```
set id=ebd0a0a2-b9e5-4433-87c0-68b6b72699c7
```

-----
-----

# shrink | Microsoft Learn

The Diskpart shrink command reduces the size of the selected volume by the amount you specify. This command makes free disk space available from the unused space at the end of the volume.

A volume must be selected for this operation to succeed. Use the **select volume** command to select a volume and shift the focus to it.

Note

This command works on basic volumes, and on simple or spanned dynamic volumes. It doesn't work on original equipment manufacturer (OEM) partitions, Extensible Firmware Interface (EFI) system partitions, or recovery partitions.

## Syntax

```
shrink [desired=<n>] [minimum=<n>] [nowait] [noerr]
shrink querymax [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| desired=`<n>` | Specifies the desired amount of space in megabytes (MB) to reduce the size of the volume by. |
| minimum=`<n>` | Specifies the minimum amount of space in MB to reduce the size of the volume by. |
| querymax | Returns the maximum amount of space in MB by which the volume can be reduced. This value may change if applications are currently accessing the volume. |
| nowait | Forces the command to return immediately while the shrink process is still in progress. |
| noerr | For scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code. |

#### Remarks

- You can reduce the size of a volume only if it is formatted using the NTFS file system or if it does not have a file system.
- If a desired amount isn't specified, the volume is reduced by the minimum amount (if specified).
- If a minimum amount isn't specified, the volume is reduced by the desired amount (if specified).
- If neither a minimum amount nor a desired amount is specified, the volume is reduced by as much as possible.
- If a minimum amount is specified, but not enough free space is available, the command fails.

## Examples

To reduce the size of the selected volume by the largest possible amount between 250 and 500 megabytes, type:

```
shrink desired=500 minimum=250
```

To display the maximum number of MB that the volume can be reduced by, type:

```
shrink querymax
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [Resize-Partition](/en-us/powershell/module/storage/resize-partition?view=win10-ps&amp;preserve-view=true)

-----
-----

# uniqueid | Microsoft Learn

Displays or sets the GUID partition table (GPT) identifier or master boot record (MBR) signature for the basic or dynamic disk with focus. A basic or dynamic disk must be selected for this operation to succeed. Use the [select disk command](select-disk) to select a disk and shift the focus to it.

## Syntax

```
uniqueid disk [id={<dword> | <GUID>}] [noerr]
```

### Parameters

| Parameter | Description |
| --- | --- |
| id=`{<dword> | <GUID>}` | For MBR disks, this parameter specifies a 4-byte (DWORD) value in hexadecimal form for the signature. For GPT disks, this parameter specifies a GUID for the identifier. |
| noerr | For scripting only. When an error occurs, DiskPart continues to process commands as if the error didn't occur. Without this parameter, an error causes DiskPart to exit with an error code. |

## Examples

To display the signature of the MBR disk with focus, type:

```
uniqueid disk
```

To set the signature of the MBR disk with focus to the DWORD value *5f1b2c36*, type:

```
uniqueid disk id=5f1b2c36
```

To set the identifier of the GPT disk with focus to the GUID value baf784e7-6bbd-4cfb-aaac-e86c96e166ee, type:

```
uniqueid disk id=baf784e7-6bbd-4cfb-aaac-e86c96e166ee
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [select disk command](select-disk)
