# Windows Preinstallation & Recovery Environments

### Tools only in PE

`WPEUtile.exe`

```
Syntax
      Wpeutil CreatePageFile [/path=path] [/size=size]
      Wpeutil DisableExtendedCharactersForVolume path_on_target_volume
      Wpeutil Disablefirewall
      Wpeutil EnableExtendedCharactersForVolume path_on_target_volume
      Wpeutil Enablefirewall
      Wpeutil InitializeNetwork
      Wpeutil ListKeyboardLayouts LCID
      Wpeutil Reboot
      Wpeutil SaveProfile
      Wpeutil SetKeyboardLayout keyboard_layout_ID
        Run ListKeyboardLayouts to get a list of supported keyboard layouts
      Wpeutil SetMuiLanguage language-name[;language-name]
        Specify multiple languages in priority order, separating them with a semicolon.
        For example: Wpeutil SetMuiLanguage de-DE;en-US
      Wpeutil SetUserLocale language-name[;language-name]
      Wpeutil Shutdown
      Wpeutil UpdateBootInfo
      Wpeutil WaitForNetwork   (Waits for the network card to be initialized.)
      Wpeutil WaitForRemovableStorage (block startup until removable devices, e.g. USB drives, are initialized.)

Wpeutil can only accept one command per line.
```

### Tools only in RE

#### BootRec

Repair or replace a partition boot sector.

Syntax  
```
BOOTREC /FIXMBR      Write a Master Boot Record (MBR) to the system partition.

BOOTREC /FIXBOOT     Write a new Boot Sector onto the system partition.

BOOTREC /SCANOS      Scan all disks for Windows installations and display entries
                     not currently in the BCD store.

BOOTREC /REBUILDBCD  Scan all disks for Windows installations and provide a choice of
                     which entries to add to the BCD store.

```
`/FixMbr` does not overwrite the existing partition table. Use this option when you must resolve MBR corruption issues, or when you have to remove nonstandard code from the MBR.

Use `/FixBoot` if The boot sector was damaged or replaced.

Examples
Fix the MBR and boot sector:
```
C:\> bootrec.exe /fixmbr
C:\> bootrec.exe /fixboot
C:\> bootrec.exe /rebuildbcd
```
Then Reboot.

Rebuild the BCD store

C:\> BOOTREC /REBUILDBCD

Troubleshoot a "Bootmgr Is Missing" error.
If rebuilding the BCD store doesn’t resolve the startup issue, you can export and delete the BCD store and then run this option again. By doing this, you make sure that the BCD store is completely rebuilt. To do this, type the following commands at the Windows RE command prompt:

```
bcdedit /export C:\BCD_Backup
c:
cd boot
attrib bcd -s -h -r
ren c:\boot\bcd bcd.old
bootrec /RebuildBcd
```

### Tools to manage RE

`REAgentC.exe` gives error if not run as admin

(https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/download-winpe--windows-pe)

### Tools to generate custom PE/RE

#### DaRT

#### Bart's

* EaseUS
* Macrium
* Hiren
* Medicat
* Veeam ?

