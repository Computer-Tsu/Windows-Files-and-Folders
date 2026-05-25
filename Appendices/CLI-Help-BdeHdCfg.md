# BitLocker Drive Preparation Tool

`C:\Windows\System32>BdeHdCfg.exe /?`
```
BitLocker Drive Preparation Tool version 10.0.22621
Copyright (C) 2013 Microsoft Corporation. All rights reserved.

Usage:

BdeHdCfg[.exe]
               [-driveinfo]
               [-target {default | unallocated |
                         TargetDriveLetter {shrink | merge}}]
               [-newdriveletter DriveLetter]
               [-size SizeInMegabytes]
               [-quiet] [-restart] [{-? | /?}]

Description:
  This command prepares your hard drive for BitLocker Drive Encryption.

  Command line parameters are not case-sensitive.

Parameters:
  -driveinfo
        Displays information about valid target drives.

  -target
        Specifies the target and operation.

        Specify 'shrink' to create a new active partition.
        Specify 'merge' to make an existing partition active.
        Specify 'unallocated' to use unformatted space on disk.
        Specify 'default' for the target to be chosen automatically.

        Examples: -target D: merge
                  -target C: shrink
                  -target unallocated
                  -target default

  -newdriveletter
        Specifies the desired drive letter for the new drive. This option is
        only valid when a new drive is created.

        Example: -newdriveletter S:

  -size
        Specifies the desired size of the new drive. This option is only valid
        when a new drive is created.

        If not specified, the Drive Preparation Tool assumes the required
        minimum size of 799 megabytes.

        Example: -size 700

  -quiet
        Specifies operation in quiet mode. No output from the drive preparation
        tool is displayed.

  -restart
        Enables an automatic restart after drive preparation.

        You must restart your computer before enabling BitLocker.

  -? or /?
        Displays help for this command.

Examples:
    BdeHdCfg -target c: shrink -newdriveletter x: -size 799 -quiet -restart
    BdeHdCfg -target d: merge -quiet -restart
    BdeHdCfg -target unallocated -newdriveletter s:
    BdeHdCfg -target default
```

    
