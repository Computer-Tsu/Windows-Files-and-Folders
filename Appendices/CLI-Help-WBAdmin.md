# 

`WBAddmin.exe /?`
```
C:\Windows\System32>wbadmin.exe /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

---- Commands Supported ----

ENABLE BACKUP             -- Creates or modifies a daily backup schedule.
DISABLE BACKUP            -- Disables the scheduled backups.
START BACKUP              -- Runs a one-time backup.
STOP JOB                  -- Stops the currently running backup or recovery
                              operation.
GET VERSIONS              -- Lists details of backups that can be recovered
                              from a specified location.
GET ITEMS                 -- Lists items contained in a backup.
GET STATUS                -- Reports the status of the currently running
                              operation.
DELETE BACKUP             -- Deletes one or more backups.

C:\Windows\System32>wbadmin.exe enable backup /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax:  WBADMIN ENABLE BACKUP
    [-addtarget:<BackupTarget>]
    [-removetarget:<BackupTarget>]
    [-schedule:<TimeToRunBackup>]
    [-include:<ItemsToInclude>
    [-nonRecurseInclude:<ItemsToInclude>]
    [-exclude:<ItemsToExclude>]
    [-nonRecurseExclude:<ItemsToExclude>]
    [-allCritical]
    [-vssFull | -vssCopy]
    [-user:<UserName>]
    [-password:<Password>]
    [-quiet]
    [-allowDeleteOldBackups]

Description:  Creates a daily backup schedule or modifies an existing backup
schedule. With no options specified, displays the current scheduled backup
settings.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Parameters:
-addtarget     Specifies the storage location for backups. Requires you to
                specify the location as a disk, volume, or Universal Naming
                Convention (UNC) path to a remote shared folder
                (\\<servername>\<sharename>\). By default, the backup will be
                saved at:  \\<servername>\<sharename>\WindowsImageBackup\
                <ComputerBackedUp>\. If you specify a disk, the disk will be
                formatted before use, and any existing data on it is
                permanently erased. If you specify a shared folder, you cannot
                add more locations. You can only specify one shared folder as
                a storage location at a time.
                Important: If you save a backup to a remote shared folder,
                that backup will be overwritten if you use the same folder to
                backup the same computer again. In addition, if the backup
                operation fails, you may end up with no backup because the
                older backup will be overwritten, but the newer backup will
                not be usable. You can avoid this by creating subfolders in
                the remote shared folder to organize your backups. If you do
                this, the subfolders will need twice the space of the parent
                folder.
                Only one location can be specified in a single command.
                Multiple volume and disk backup storage locations can be added
                by running the command again.

-removetarget  Specifies the storage location that you want to remove from the
                existing backup schedule.

-schedule      Specifies the times of day to create a backup (comma-delimited
                and formatted as HH:MM).

-include       Specifies the comma-delimited list of items to include in the
                backup. You can include multiple files, folders, or volumes.
                Volume paths can be specified using volume drive letters,
                volume mount points, or GUID-based volume names. If you use a
                GUID-based volume name, it should be terminated with a
                backslash (\). You can use the wildcard character (*) in the
                file name when specifying a path to a file.

-nonRecurseInclude   Specifies the non-recursive, comma-delimited list of
                items to include in the backup. You can include multiple
                files, folders, or volumes. Volume paths can be specified
                using volume drive letters, volume mount points, or GUID-based
                volume names. If you use a GUID-based volume name, it should
                be terminated with a backslash (\). You can use the wildcard
                character (*) in the file name when specifying a path to a
                file. Should be used only when the -backupTarget parameter is
                used.

-exclude       Specifies the comma-delimited list of items to exclude from the
                backup. You can exclude files, folders, or volumes. Volume
                paths can be specified using volume drive letters, volume
                mount points, or GUID-based volume names. If you use a
                GUID-based volume name, it should be terminated with a
                backslash (\). You can use the wildcard character (*) in the
                file name when specifying a path to a file.

-nonRecurseExclude   Specifies the non-recursive, comma-delimited list of
                items to exclude from the backup. You can exclude files,
                folders, or volumes. Volume paths can be specified using
                volume drive letters, volume mount points, or GUID-based
                volume names. If you use a GUID-based volume name, it should
                be terminated with a backslash (\). You can use the wildcard
                character (*) in the file name when specifying a path to a
                file.

-allCritical   Creates a backup that includes all critical volumes (critical
                volumes contain the operating system files and components) in
                addition to any other items that you specified with the
                -include parameter. This parameter is useful if you are
                creating a backup for bare metal recovery.

-vssFull       Performs a full backup using the Volume Shadow Copy Service
                (VSS). Each file's history is updated to reflect that it was
                backed up. If this parameter is not used WBADMIN START BACKUP
                makes a copy backup, but the history of files being backed up
                is not updated.
                Caution: Do not use this parameter if you are using a product
                other than Windows Server Backup to back up applications that
                are on the volumes included in the current backup. Doing so
                can potentially break the incremental, differential, or other
                type of backups that the other backup product is creating.

-vssCopy       Performs a copy backup using VSS. The history of the files
                being backed up is not updated. This is the default value.

-user          Specifies the user with write permission to the backup storage
                destination (if it is a remote shared folder). The user needs
                to be a member of the Administrators group or Backup Operators
                group on the computer that is getting backed up.

-password      Specifies the password for the user name provided by the
                parameter -user.

-quiet         Runs the command with no prompts to the user.

-allowDeleteOldBackups   Overwrites the backups found before upgrade.

Examples:
WBADMIN ENABLE BACKUP -include:c:\dir1\* -addtarget:e: -schedule:00:00
WBADMIN ENABLE BACKUP -addtarget:e: -schedule:00:00 -allCritical
```


C:\Windows\System32>wbadmin.exe disable backup /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN DISABLE BACKUP [-quiet]

Description: Stops running the existing scheduled daily backups.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Parameters:
-quiet          Runs the command with no prompts to the user.

Remarks:  If you stop the scheduled backups, the disks where you stored the
backups cannot be used again to store backups until they are reformatted (so
that all existing backups are deleted).




C:\Windows\System32>wbadmin.exe start backup /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN START BACKUP
    [-backupTarget:{<BackupDestinationVolume> | <TargetNetworkShare>}]
    [-include:<VolumesToInclude>]
    [-allCritical]
    [-user:<UserName>]
    [-password:<Password>]
    [-noInheritAcl]
    [-noVerify]
    [-vssFull | -vssCopy]
    [-quiet]

Description:  Creates a backup using specified parameters. If no parameters
are specified and you have created a scheduled daily backup, this command
creates the backup by using the settings for the scheduled backup.

Parameters:
-backupTarget  Specifies the storage location for this backup. Requires a
                hard disk drive letter (f:), a volume GUID-based path in the
                format of \\?\Volume{GUID}, or a Universal Naming Convention
                (UNC) path to a remote shared folder
                (\\<servername>\<sharename>\).
                By default, the backup will be saved at: \\<servername>
                \<sharename>\WindowsImageBackup\<ComputerBackedUp>\.
                Important: If you save a backup to a remote shared folder,
                that backup will be overwritten if you use the same folder to
                back up the same computer again. In addition, if the backup
                operation fails, you may finish with no backup because the
                older backup will be overwritten, but the newer backup will
                not be usable.
                You can avoid this by creating subfolders in the remote shared
                folder to organize your backups. If you do this, the
                subfolders will need twice the space of the parent folder.

-include       Specifies the comma-delimited list of items to include in the
                backup. You can include multiple volumes. Volume paths can be
                specified using volume drive letters, volume mount points, or
                GUID-based volume names. If you use a GUID-based volume
                name, it should be terminated with a backslash (\). You can
                use the wildcard character (*) in the file name when
                specifying a path to a file. Should be used only when the
                -backupTarget parameter is used.

-allCritical   Creates a backup that includes all critical volumes (critical
                volumes contain the operating system files and components) in
                addition to any other items that you specified with the
                -include parameter. This parameter is useful if you are
                creating a backup for bare metal recovery or system state
                recovery. Should be used only when the -backupTarget
                parameter is used.

-user          If the backup is saved to a remote shared folder, specifies
                the user name with write permission to the folder.

-password      Specifies the password for the user name that is provided by
                the parameter -user.

-noInheritAcl  Applies the access control list (ACL) permissions that
                correspond to the credentials specified by -user and
                -password to \\<servername>\<sharename>\WindowsImageBackup
                \<ComputerBackedUp>\ (the folder that contains the backup).
                To access the backup later, you must use these credentials or
                be a member of the Administrators group or the Backup
                Operators group on the computer with the shared folder.
                If -noInheritAcl is not used, the ACL permissions from the
                remote shared folder are applied to the
                <ComputerBackedUp> folder by default so that anyone with
                access to the remote shared folder can access the backup.

-noVerify      Specifies that backups written to removable media (such as a
                DVD) are not verified for errors. If you do not use this
                parameter, backups saved to removable media are verified for
                errors.

-vssFull       Performs a full backup using the Volume Shadow Copy Service
                (VSS). Each file's history is updated to reflect that it was
                backed up. If this parameter is not used WBADMIN START BACKUP
                makes a copy backup, but the history of files being backed up
                is not updated.
                Caution: Do not use this parameter if you are using a product
                other than Windows Server Backup to back up applications that
                are on the volumes included in the current backup. Doing so
                can potentially break the incremental, differential, or other
                type of backups that the other backup product is creating.

-vssCopy       Performs a copy backup using VSS. The history of the files
                being backed up is not updated. This is the default value.

-quiet         Runs the command with no prompts to the user.

Example: WBADMIN START BACKUP -backupTarget:f: -include:e:,d:\mountpoint,
\\?\Volume{cc566d14-44a0-11d9-9d93-806e6f6e6963}\


C:\Windows\System32>wbadmin.exe stop job /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN STOP JOB [-quiet]

Description:  Cancels the backup or recovery operation that is currently
running.
Canceled operations cannot be restarted - you must rerun a canceled backup
or recovery operation from the beginning.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Parameters:
-quiet         Runs the command with no prompts to the user.




```
C:\Windows\System32>wbadmin.exe GET VERSIONS /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN GET VERSIONS
    [-backupTarget:{<BackupDestinationVolume> | <NetworkSharePath>}]
    [-machine:<BackupMachineName>]

Description:  Lists details about the available backups that are stored on
the local computer or on another computer. When this command is used without
parameters, it lists all backups of the local computer, even if those backups
are not available. The details provided for a backup include the backup time,
the backup storage location, the version identifier (needed for
WBADMIN GET ITEMS and to perform recoveries), and the type of recoveries you
can perform. To use this command, you must be a member of the Backup
Operators group or Administrators group.

Parameters:
-backupTarget  Specifies the storage location that contains the backups that
                you want the details for. Use for listing information about
                backups that were not of the local computer. Alternate
                locations can be locally attached hard disk drives, DVD
                drives, or remote shared folders.

-machine       Specifies the computer that you want backup details for.
                Use when backups of multiple computers are stored in the
                same location. Should be used when -backupTarget is specified.

Examples:
WBADMIN GET VERSIONS -backupTarget:h:
WBADMIN GET VERSIONS -backupTarget:\\servername\share -machine:server01

Remarks:  To list items available for recovery from a specific backup, use
WBADMIN GET ITEMS.


C:\Windows\System32>wbadmin.exe GET items /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN GET ITEMS
    -version:<VersionIdentifier>
    [-backupTarget:{<BackupDestinationVolume> | <NetworkSharePath>}]
    [-machine:<BackupMachineName>]

Description:  Lists the items included in a specific backup.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Parameters:
-version       Specifies the version of the backup in MM/DD/YYYY-HH:MM format.
                If you do not know the version information, type WBADMIN GET
                VERSIONS.

-backupTarget  Specifies the storage location that contains the backups for
                which you want the details. The storage location can be a
                locally attached disk drive or a remote shared folder. If
                WBADMIN GET VERSIONS is run on the same server where the
                backup was created, this parameter is not needed. However,
                this parameter is required to get information about a backup
                created from another server.

-machine       Specifies the name of the computer that you want the backup
                details for. Useful when multiple computers have been backed
                up to the same location. Should be used when -backupTarget is
                specified.

Examples:
WBADMIN GET ITEMS -version:03/31/2005-09:00
WBADMIN GET ITEMS -version:04/30/2005-09:00 -backupTarget:\\servername\share
-machine:server01


C:\Windows\System32>wbadmin.exe GET status /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN GET STATUS

Description:  Reports the status of the currently running backup or recovery
operation.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Remarks:  This command will not stop until the current backup or recovery
operation is finished - it will continue to run even if you close the command
window. If you want to stop the operation instead, use the WBADMIN STOP
JOB command.
```

```
C:\Windows\System32>wbadmin.exe delete backup /?
wbadmin 1.0 - Backup command-line tool
(C) Copyright Microsoft Corporation. All rights reserved.

ERROR - Command syntax incorrect. Error: /?. See the command
syntax below.

Syntax: WBADMIN DELETE BACKUP
  {-keepVersions:<No. of copies> | -version:<VersionIdentifier> | -deleteOldest}
  [-backupTarget:<VolumeName>]
  [-machine:<BackupMachineName>]
  [-quiet]

Description:  Deletes the backups that you specify. If the
specified volume contains backups other than backups of the local
server, those backups will not be deleted.
To use this command, you must be a member of the Backup Operators group
or Administrators group.

Parameters:
-keepVersions  Specifies the number of the latest backups to
                keep. The value must be a positive integer. The option value
                -keepVersions:0 deletes all the backups.

-version       Version identifier of the backup in MM/DD/YYYY-HH:MM format.
                If you do not know the version identifier, at a command
                prompt, type:  WBADMIN GET VERSIONS. Versions that are
                exclusively backups can be deleted using this
                command. Use WBADMIN GET ITEMS to view the version type.

-deleteOldest  Deletes the oldest backup.

-backupTarget  Specifies the storage location for the backup that you want
                to delete. The storage location for backups is a
                drive letter, a mount point, or a GUID-based volume path. This
                value only needs to be specified for locating backups that are
                not of the local computer. Information about backups for the
                local computer will be available in the backup catalog on the
                local computer.

-machine       Specifies the computer whose backup you want to
                delete. Useful when multiple computers were backed up to
                the same location. Should be used when -backupTarget is
                specified.

-quiet         Runs the command with no prompts to the user.

Remarks: One, and only one, of these parameters must be specified:
-keepVersions, -version, or -deleteOldest.

Examples:
WBADMIN DELETE BACKUP -version:03/31/2006-10:00
WBADMIN DELETE BACKUP -keepVersions:3
WBADMIN DELETE BACKUP -backupTarget:f: -deleteOldest
```

