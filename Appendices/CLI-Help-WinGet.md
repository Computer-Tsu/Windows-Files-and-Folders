# WinGet

Winget is linked as a reparse point:
```
C:\>dir %localappdata%\Microsoft\WindowsApps\winget.exe /AL
 Volume in drive C is Win11

 Directory of C:\Users\mem\AppData\Local\Microsoft\WindowsApps

05/22/2026  09:06 AM                 0 winget.exe
               1 File(s)              0 bytes
```

## Command Line Switches

commands, options, and package names are case-insensitive<br>
*winget uses the double hyphen like Unix/Linux*

Common options: `winget add `
--accept-package-agreements 
--accept-source-agreements 
--e 
--scope machine, --scope user

`winget update --all`

```
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

The winget command line utility enables installing applications and other packages from the command line.

usage: winget  [<command>] [<options>]

The following commands are available:
  install    Installs the given package
  show       Shows information about a package
  source     Manage sources of packages
  search     Find and show basic info of packages
  list       Display installed packages
  upgrade    Shows and performs available upgrades
  uninstall  Uninstalls the given package
  hash       Helper to hash installer files
  validate   Validates a manifest file
  settings   Open settings or set administrator settings
  features   Shows the status of experimental features
  export     Exports a list of the installed packages
  import     Installs all the packages in a file
  pin        Manage package pins
  configure  Configures the system into a desired state
  download   Downloads the installer from a given package
  repair     Repairs the selected package
  dscv3      DSC v3 resource commands
  mcp        MCP information

For more details on a specific command, pass it the help argument. [-?]

The following options are available:
  -v,--version                Display the version of the tool
  --info                      Display general info of the tool
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-help
```
aliases:
- Install, Add
- Upgrade, Update
- Show (no alias for View)
- List, ls
- Search, Find
- Show, View
- Ininstall, Remove, rm

## Documentation

- https://aka.ms/winget-command-help
- https://aka.ms/winget-command-install
- https://aka.ms/winget-command-list
- https://aka.ms/winget-command-search
- https://aka.ms/winget-command-show
- https://aka.ms/winget-command-upgrade
- https://aka.ms/winget-command-uninstall

### Info

```
C:\Users\mem>winget --info
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Windows: Windows.Desktop v10.0.22621.3155
System Architecture: X64
Package: Microsoft.DesktopAppInstaller v1.28.240.0

Winget Directories
-------------------------------------------------------------------------------------------------------------------------------
Logs                               %LOCALAPPDATA%\Packages\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe\LocalState\DiagOutputDir
User Settings                      %LOCALAPPDATA%\Packages\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe\LocalState\settings.json
Portable Links Directory (User)    %LOCALAPPDATA%\Microsoft\WinGet\Links
Portable Links Directory (Machine) C:\Program Files\WinGet\Links
Portable Package Root (User)       %LOCALAPPDATA%\Microsoft\WinGet\Packages
Portable Package Root              C:\Program Files\WinGet\Packages
Portable Package Root (x86)        C:\Program Files (x86)\WinGet\Packages
Installer Downloads                %USERPROFILE%\Downloads
Configuration Modules              %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

Links
---------------------------------------------------------------------------
Privacy Statement   https://aka.ms/winget-privacy
License Agreement   https://aka.ms/winget-license
Third Party Notices https://aka.ms/winget-3rdPartyNotice
Homepage            https://aka.ms/winget
Windows Store Terms https://www.microsoft.com/en-us/storedocs/terms-of-sale

Admin Setting                             State
--------------------------------------------------
LocalManifestFiles                        Disabled
BypassCertificatePinningForMicrosoftStore Disabled
InstallerHashOverride                     Disabled
LocalArchiveMalwareScanOverride           Disabled
ProxyCommandLineOptions                   Disabled
DefaultProxy                              Disabled
```

### Install

```
winget install -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Installs the selected package, either found by searching a configured source or directly from a manifest. By default, the query must case-insensitively match the id, name, or moniker of the package. Other fields can be used by passing their appropriate option. By default, install command will check package installed status and try to perform an upgrade if applicable. Override with --force to perform a direct install.

usage: winget install [[-q] <query>...] [<options>]

The following command aliases are available:
  add

The following arguments are available:
  -q,--query                           The query used to search for a package

The following options are available:
  -m,--manifest                        The path to the manifest of the package
  --id                                 Filter results by id
  --name                               Filter results by name
  --moniker                            Filter results by moniker
  -v,--version                         Use the specified version; default is the latest version
  -s,--source                          Find package using the specified source
  --scope                              Select install scope (user or machine)
  -a,--architecture                    Select the architecture
  --installer-type                     Select the installer type
  -e,--exact                           Find package using exact match
  -i,--interactive                     Request interactive installation; user input may be needed
  -h,--silent                          Request silent installation
  --locale                             Locale to use (BCP47 format)
  -o,--log                             Log location (if supported)
  --custom                             Arguments to be passed on to the installer in addition to the defaults
  --override                           Override arguments to be passed on to the installer
  -l,--location                        Location to install to (if supported)
  --ignore-security-hash               Ignore the installer hash check failure
  --allow-reboot                       Allows a reboot if applicable
  --skip-dependencies                  Skips processing package dependencies and Windows features
  --ignore-local-archive-malware-scan  Ignore the malware scan performed as part of installing an archive type package from local manifest
  --dependency-source                  Find package dependencies using the specified source
  --accept-package-agreements          Accept all license agreements for packages
  --no-upgrade                         Skips upgrade if an installed version already exists
  --header                             Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode                Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account             Specify the account to be used for authentication
  --accept-source-agreements           Accept all source agreements during source operations
  -r,--rename                          The value to rename the executable file (portable)
  --uninstall-previous                 Uninstall the previous version of the package during upgrade
  --force                              Direct run the command and continue with non security related issues
  -?,--help                            Shows help about the selected command
  --wait                               Prompts the user to press any key before exiting
  --logs,--open-logs                   Open the default logs location
  --verbose,--verbose-logs             Enables verbose logging for winget
  --nowarn,--ignore-warnings           Suppresses warning outputs
  --disable-interactivity              Disable interactive prompts
  --proxy                              Set a proxy to use for this execution
  --no-proxy                           Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-install
```

### List

```
C:\>winget list -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

The list command displays the packages installed on the system, as well as whether an upgrade is available. Additional options can be provided to filter the output, much like the search command.

usage: winget list [[-q] <query>] [<options>]

The following command aliases are available:
  ls

The following arguments are available:
  -q,--query                      The query used to search for a package

The following options are available:
  --id                            Filter results by id
  --name                          Filter results by name
  --moniker                       Filter results by moniker
  -s,--source                     Find package using the specified source
  --tag                           Filter results by tag
  --cmd,--command                 Filter results by command
  -n,--count                      Show no more than specified number of results (between 1 and 1000)
  -e,--exact                      Find package using exact match
  --scope                         Select installed package scope filter (user or machine)
  --header                        Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode           Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account        Specify the account to be used for authentication
  --accept-source-agreements      Accept all source agreements during source operations
  --upgrade-available             Lists only packages which have an upgrade available
  -u,--unknown,--include-unknown  List packages even if their current version cannot be determined. Can only be used with the --upgrade-available argument
  --pinned,--include-pinned       List packages even if they have a pin that prevents upgrade. Can only be used with the --upgrade-available argument
  --details                       Show detailed information about packages
  -?,--help                       Shows help about the selected command
  --wait                          Prompts the user to press any key before exiting
  --logs,--open-logs              Open the default logs location
  --verbose,--verbose-logs        Enables verbose logging for winget
  --nowarn,--ignore-warnings      Suppresses warning outputs
  --disable-interactivity         Disable interactive prompts
  --proxy                         Set a proxy to use for this execution
  --no-proxy                      Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-list
```

### Search

```
C:\>winget search -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Searches for packages from configured sources.

usage: winget search [[-q] <query>] [<options>]

The following command aliases are available:
  find

The following arguments are available:
  -q,--query                  The query used to search for a package

The following options are available:
  --id                        Filter results by id
  --name                      Filter results by name
  --moniker                   Filter results by moniker
  --tag                       Filter results by tag
  --cmd,--command             Filter results by command
  -s,--source                 Find package using the specified source
  -n,--count                  Show no more than specified number of results (between 1 and 1000)
  -e,--exact                  Find package using exact match
  --header                    Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode       Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account    Specify the account to be used for authentication
  --accept-source-agreements  Accept all source agreements during source operations
  --versions                  Show available versions of the package
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-search
```

### Show

```
C:\>winget show -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Shows information on a specific package. By default, the query must case-insensitively match the id, name, or moniker of the package. Other fields can be used by passing their appropriate option.

usage: winget show [[-q] <query>] [<options>]

The following command aliases are available:
  view

The following arguments are available:
  -q,--query                  The query used to search for a package

The following options are available:
  -m,--manifest               The path to the manifest of the package
  --id                        Filter results by id
  --name                      Filter results by name
  --moniker                   Filter results by moniker
  -v,--version                Use the specified version; default is the latest version
  -s,--source                 Find package using the specified source
  -e,--exact                  Find package using exact match
  --scope                     Select install scope (user or machine)
  -a,--architecture           Select the architecture
  --installer-type            Select the installer type
  --locale                    Locale to use (BCP47 format)
  --versions                  Show available versions of the package
  --header                    Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode       Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account    Specify the account to be used for authentication
  --accept-source-agreements  Accept all source agreements during source operations
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-show
```

### Upgrade

```
C:\>winget upgrade -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Upgrades the selected package, either found by searching the installed packages list or directly from a manifest. By default, the query must case-insensitively match the id, name, or moniker of the package. Other fields can be used by passing their appropriate option. When no arguments are given, shows the packages with upgrades available

usage: winget upgrade [[-q] <query>...] [<options>]

The following command aliases are available:
  update

The following arguments are available:
  -q,--query                           The query used to search for a package

The following options are available:
  -m,--manifest                        The path to the manifest of the package
  --id                                 Filter results by id
  --name                               Filter results by name
  --moniker                            Filter results by moniker
  -v,--version                         Use the specified version; default is the latest version
  -s,--source                          Find package using the specified source
  -e,--exact                           Find package using exact match
  -i,--interactive                     Request interactive installation; user input may be needed
  -h,--silent                          Request silent installation
  --purge                              Deletes all files and directories in the package directory (portable)
  -o,--log                             Log location (if supported)
  --custom                             Arguments to be passed on to the installer in addition to the defaults
  --override                           Override arguments to be passed on to the installer
  -l,--location                        Location to install to (if supported)
  --scope                              Select installed package scope filter (user or machine)
  -a,--architecture                    Select the architecture
  --installer-type                     Select the installer type
  --locale                             Locale to use (BCP47 format)
  --ignore-security-hash               Ignore the installer hash check failure
  --allow-reboot                       Allows a reboot if applicable
  --skip-dependencies                  Skips processing package dependencies and Windows features
  --ignore-local-archive-malware-scan  Ignore the malware scan performed as part of installing an archive type package from local manifest
  --accept-package-agreements          Accept all license agreements for packages
  --accept-source-agreements           Accept all source agreements during source operations
  --header                             Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode                Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account             Specify the account to be used for authentication
  -r,--recurse,--all                   Upgrade all installed packages to latest if available
  -u,--unknown,--include-unknown       Upgrade packages even if their current version cannot be determined
  --pinned,--include-pinned            Upgrade packages even if they have a non-blocking pin
  --uninstall-previous                 Uninstall the previous version of the package during upgrade
  --force                              Direct run the command and continue with non security related issues
  -?,--help                            Shows help about the selected command
  --wait                               Prompts the user to press any key before exiting
  --logs,--open-logs                   Open the default logs location
  --verbose,--verbose-logs             Enables verbose logging for winget
  --nowarn,--ignore-warnings           Suppresses warning outputs
  --disable-interactivity              Disable interactive prompts
  --proxy                              Set a proxy to use for this execution
  --no-proxy                           Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-upgrade
```

### Uninstall

```
C:\>winget uninstall -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Uninstalls the selected package, either found by searching the installed packages list or directly from a manifest. By default, the query must case-insensitively match the id, name, or moniker of the package. Other fields can be used by passing their appropriate option.

usage: winget uninstall [[-q] <query>...] [<options>]

The following command aliases are available:
  remove
  rm

The following arguments are available:
  -q,--query                  The query used to search for a package

The following options are available:
  -m,--manifest               The path to the manifest of the package
  --id                        Filter results by id
  --name                      Filter results by name
  --moniker                   Filter results by moniker
  --product-code              Filters using the product code
  -v,--version                The version to act upon
  --all,--all-versions        Uninstall all versions
  -s,--source                 Find package using the specified source
  -e,--exact                  Find package using exact match
  --scope                     Select installed package scope filter (user or machine)
  -i,--interactive            Request interactive installation; user input may be needed
  -h,--silent                 Request silent installation
  --force                     Direct run the command and continue with non security related issues
  --purge                     Deletes all files and directories in the package directory (portable)
  --preserve                  Retains all files and directories created by the package (portable)
  -o,--log                    Log location (if supported)
  --header                    Optional Windows-Package-Manager REST source HTTP header
  --authentication-mode       Specify authentication window preference (silent, silentPreferred, or interactive)
  --authentication-account    Specify the account to be used for authentication
  --accept-source-agreements  Accept all source agreements during source operations
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-uninstall
```

