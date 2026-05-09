> *Error run without admin elevation*
```
This command can only be executed from an elevated command prompt.

REAGENTC.EXE: Operation failed: 5

REAGENTC.EXE: An error has occurred.
```

```
C:\Windows\System32>dir ReAgentc.exe

 Directory of C:\Windows\System32

03/11/2024  11:17 PM            69,632 ReAgentc.exe
               1 File(s)         69,632 bytes
               0 Dir(s)   2,589,110,272 bytes free
```
> C:\Windows\System32>ReAgentc.exe /?
```
Configures the Windows Recovery Environment (Windows RE) and system reset.

REAGENTC.EXE <command> <arguments>

The following commands can be specified:

  /info             - Displays Windows RE and system reset configuration
                      information.
  /setreimage       - Sets the location of the custom Windows RE image.
  /enable           - Enables Windows RE.
  /disable          - Disables Windows RE.
  /boottore         - Configures the system to start Windows RE next time the
                      system starts up.
  /setbootshelllink - Adds an entry to the Reset and Restore page in the boot
                      menu.

For more information about these commands and their arguments, type
REAGENTC.EXE <command> /?.

  Examples:
    REAGENTC.EXE /setreimage /?
    REAGENTC.EXE /disable /?

REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /info /?
```
Displays Windows Recovery Environment (Windows RE) configuration information.

REAGENTC.EXE /info [/target <dir_name>] [/logpath <file_path>]

  /target <dir_name>    - Specifies the Windows installation. If this argument
                          is not specified, the running operating system is
                          used.
  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /info
    REAGENTC.EXE /info /target C:\Windows /logpath C:\Temp\Reagent.log

REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /setreimage /?
```
Sets the location of the custom Windows Recovery Environment (Windows RE) image.

REAGENTC.EXE /setreimage /path <dir_name> [/target <dir_name>] [/logpath <file_path>]

  /path <dir_name>      - Specifies the directory that contains the custom
                          Windows RE image (winre.wim).
  /target <dir_name>    - Specifies the Windows installation. If this argument
                          is not specified, the running operating system is
                          used.
  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /setreimage /path r:\Recovery\WindowsRE /logpath C:\Temp\Reagent.log
    REAGENTC.EXE /setreimage /path r:\Recovery\WindowsRE /target C:\Windows

REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /enable /?
```
Enables the local copy of the Windows Recovery Environment (Windows RE).

This command can be used from the running operating system without additional
parameters, or from the Windows Preinstallation Environment (Windows PE) using
the optional /osguid parameter.

REAGENTC.EXE /enable [/osguid <bcd_guid>] [/logpath <file_path>]

  /osguid <bcd_guid>    - Specifies the Boot Configuration Data (BCD) identifier of the
                          target Windows installation. The identifier can be determined
                          by running "bcdedit -enum -v".

  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /enable /logpath C:\Temp\Reagent.log
    REAGENTC.EXE /enable /osguid {00000000-0000-0000-0000-000000000000}


REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /disable /?
```
Disables the local copy of the Windows Recovery Environment (Windows RE). This
command can only be used from the running operating system.

Warning: Windows RE can help resolve startup problems; disabling it is not
recommended.

REAGENTC.EXE /disable [/logpath <file_path>]
  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /disable /logpath C:\Temp\Reagent.log

REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /boottore /?
```
Configure the system to start the Windows Recovery Environment (Windows RE)
next time the system starts up. This command can only be used from the running
operating system.

REAGENTC.EXE /boottore [/logpath <file_path>]
  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /boottore /logpath C:\Temp\Reagent.log
REAGENTC.EXE: Operation Successful.
```

> C:\Windows\System32>ReAgentc.exe /setbootshelllink /?
```
Add an entry to the Reset and Restore page in the boot menu.

REAGENTC.EXE /setbootshelllink /configfile <xml_name> [/target <dir_name>] [/logpath <file_path>]

  /configfile <xml_name>  - Specifies the path to the XML configuration file
                          for the boot menu entry.
  /target <dir_name>      - Specifies the Windows installation. If this
                          argument is not specified, the running operating
                          system is used.
  /logpath <file_path>  - Specifies the path of log file. If this argument is
                          not specified, the default path is Windows\Logs\
                          Reagent\Reagent.log.

  Example:
    REAGENTC.EXE /setbootshelllink /configfile d:\linkdesc.xml /logpath C:\Temp\Reagent.log
    REAGENTC.EXE /setbootshelllink /configfile d:\linkdesc.xml /target C:\Windows

REAGENTC.EXE: Operation Successful.
```
