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

