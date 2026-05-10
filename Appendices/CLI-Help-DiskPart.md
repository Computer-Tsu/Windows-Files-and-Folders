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
