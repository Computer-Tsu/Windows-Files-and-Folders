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
- https://aka.ms/winget-command-source
- https://aka.ms/winget-settings
- https://aka.ms/winget-command-configure

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

### Source

```
C:\>winget source -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Manage sources with the sub-commands. A source provides the data for you to discover and install packages. Only add a new source if you trust it as a secure location.

usage: winget source [<command>] [<options>]

The following sub-commands are available:
  add     Add a new source
  list    List current sources
  update  Update current sources
  remove  Remove current sources
  edit    Edit properties of a source
  reset   Reset sources
  export  Export current sources

For more details on a specific command, pass it the help argument. [-?]

The following options are available:
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-source
```

### Settings

```
C:\>winget settings -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Open settings in the default json text editor. If no editor is configured, opens settings in notepad. For available settings see https://aka.ms/winget-settings This command can also be used to set administrator settings by providing the --enable or --disable arguments

usage: winget settings [<command>] [<options>]

The following command aliases are available:
  config

The following sub-commands are available:
  export  Export settings
  set     Sets the value of an admin setting.
  reset   Resets an admin setting to its default value.

For more details on a specific command, pass it the help argument. [-?]

The following options are available:
  --enable                    Enables the specific administrator setting
  --disable                   Disables the specific administrator setting
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-settings
```

### Configure

```
C:\>winget configure -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Ensures that the system matches the desired state as described by the provided configuration. May download/execute processors in order to achieve the desired state. The configuration and the processors should be checked to ensure that they are trustworthy before applying them.

usage: winget configure [<command>] [[-f] <file>] [[--module-path] <module-path>] [<options>]

The following command aliases are available:
  configuration
  dsc

The following sub-commands are available:
  show      Shows details of a configuration
  list      Shows configuration history
  test      Checks the system against a desired state
  validate  Validates a configuration file
  export    Exports configuration resources to a configuration file.

For more details on a specific command, pass it the help argument. [-?]

The following arguments are available:
  -f,--file                          The path to the configuration file
  --module-path                      Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

The following options are available:
  --processor-path                   Specify the path to the configuration processor
  -h,--history                       Select items from history
  --accept-configuration-agreements  Accepts the configuration warning, preventing an interactive prompt
  --suppress-initial-details         Suppress showing initial configuration details when possible
  --enable                           Enable extended features. Requires store access.
  --disable                          Disable extended features. Requires store access.
  -?,--help                          Shows help about the selected command
  --wait                             Prompts the user to press any key before exiting
  --logs,--open-logs                 Open the default logs location
  --verbose,--verbose-logs           Enables verbose logging for winget
  --nowarn,--ignore-warnings         Suppresses warning outputs
  --disable-interactivity            Disable interactive prompts
  --proxy                            Set a proxy to use for this execution
  --no-proxy                         Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure
```

### MCP

Use the Windows Package Manager MCP Server for package management with AI agents

```
C:\>winget mcp -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

MCP (Model Context Protocol) information for the Windows Package Manager.

usage: winget mcp [<options>]

The following options are available:
  --enable                    Enable extended features. Requires store access.
  --disable                   Disable extended features. Requires store access.
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-mcp
```

-----

`winget source reset`

-----

---
layout: Conceptual
title: configure Command | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows/package-manager/winget/configure
ms.service: dev-environment
recommendations: true
ROBOTS: INDEX, FOLLOW
author: GrantMeStrength
ms.author: jken
Search.Product: eADQiWindows 10XVcnh
uhfHeaderId: MSDocsHeader-Windows-DevTools
breadcrumb_path: /windows/breadcrumbs/toc.json
feedback_product_url: https://github.com/microsoft/winget-cli/issues
feedback_system: OpenSource
ms.subservice: package-manager
ms.update-cycle: 365-days
description: Uses a winget configuration file to begin setting up your Windows machine to a desired development environment state.
ms.date: 2025-12-11T00:00:00.0000000Z
ms.topic: overview
locale: en-us
document_id: f84aa6f1-0f80-ea4a-dc09-3ffeee355acc
document_version_independent_id: f84aa6f1-0f80-ea4a-dc09-3ffeee355acc
updated_at: 2026-05-20T05:03:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windows-dev-docs-pr/blob/live/hub/package-manager/winget/configure.md
gitcommit: https://github.com/MicrosoftDocs/windows-dev-docs-pr/blob/00fc4a365ecd5a51478d98a6f034bc3571e6d736/hub/package-manager/winget/configure.md
git_commit_id: 00fc4a365ecd5a51478d98a6f034bc3571e6d736
site_name: Docs
depot_name: MSDN.windows-uwp-hub
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.windows-uwp-hub/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 556
asset_id: package-manager/winget/configure
moniker_range_name: 
monikers: []
item_type: Content
source_path: hub/package-manager/winget/configure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: db4d2a6b-af43-9944-ab2b-9021a0f17ccd
---

# configure Command | Microsoft Learn

The **configure** command of the [winget](./) tool uses a [WinGet Configuration file](../configuration/) to begin setting up your Windows machine to a desired development environment state. A configuration file can specify a collection of packages to install alongside other system settings, making it the most complete approach for reproducible environment setup.

Tip

For simpler scenarios, you can install multiple packages in a single command (`winget install A B C`), or use [**winget export**](export) and [**winget import**](import) to save and restore a package list.

Warning

Do not run a WinGet Configuration file without first reviewing the contents of the file and verifying the credibility of the related resources. See [How to check the trustworthiness of a WinGet Configuration file](../configuration/check).

## Prerequisites

- Windows 10 version 1809 (build 17763) or later, or Windows 11.
- WinGet version [v1.6.2631 or later](https://github.com/microsoft/winget-cli/releases).

## Aliases

The following aliases are available for this command:

- `configuration`
- `dsc`

## Usage

`winget configure -f <C:/Users/<username>/winget-configs/config-file-name.dsc.winget>`

Once you have identified the WinGet configuration file that you are interested in using, confirmed the safety and trustworthiness of that file, and downloaded the file to your local machine, you can use the `winget configure` command to initiate the set up of your configuration.

[![Screenshot listing winget configure command options.](images/configure.png)](images/configure.png#lightbox)

## Arguments and options

The following arguments are available:

| Argument | Description |
| --- | --- |
| -f,--file | The path to the winget configuration file. |
| --module-path | Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules. |
| --processor-path | Specifies the path to the configuration processor. |
| -h,--history | Select items from history. |
| --accept-configuration-agreements | Accepts the configuration warning, preventing an interactive prompt. |
| --suppress-initial-details | Suppress showing initial configuration details when possible. |
| --enable | Enable configuration components. Requires store access. |
| --disable | Disable configuration components. Requires store access. |
| -?,--help | Shows help about the selected command. |
| --wait | Prompts the user to press any key before exiting. |
| --logs,--open-logs | Open the default logs location. |
| --verbose,--verbose-logs | Enables verbose logging for winget. |
| --nowarn,--ignore-warnings | Suppresses warning outputs. |
| --disable-interactivity | Disable interactive prompts. |
| --proxy | Set a proxy to use for this execution. |
| --no-proxy | Disable the use of proxy for this execution. |

## configure subcommands

The `winget configure` command includes a number of subcommands, including:

- **`winget configure show`**: Displays the details of a configuration file. Usage: `winget configure show -f <file>`. Running the command: `winget configuration show configuration.dsc.yaml` will display the details of the configuration in the current working directory.
- **`winget configure list`**: Shows the high level details for configurations that have been applied to the system. This data can then be used with other `configure` commands to get more details. Usage: `winget configure list [<options>]`
- **`winget configure test`**: Checks the system against the desired state, displaying whether the current system state conforms with the desired state defined in the associated configuration file. Usage: `winget configure test -f <file>`.
- **`winget configure validate`**: Validates a configuration file. Usage: `winget configure validate [-f] <file> [<options>]`.
- **`winget configure export`**: Exports configuration resources to a configuration file. When used with `--all`, exports all package configurations. When used with `--package-id`, exports a WinGetPackage resource of the given package identifier. When used with `--module` and `--resource`, exports the settings of the specified resource. If the output configuration file already exists, appends the exported configuration resources. Usage: `winget configure export -o <output file> [<options>]`

-----

---
layout: Conceptual
title: WinGet Configuration | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows/package-manager/configuration/
ms.service: dev-environment
recommendations: true
ROBOTS: INDEX, FOLLOW
author: GrantMeStrength
ms.author: jken
Search.Product: eADQiWindows 10XVcnh
uhfHeaderId: MSDocsHeader-Windows-DevTools
breadcrumb_path: /windows/breadcrumbs/toc.json
feedback_product_url: https://github.com/microsoft/winget-cli/issues
feedback_system: OpenSource
ms.subservice: package-manager
ms.update-cycle: 365-days
description: WinGet Configuration uses the winget configure command, PowerShell, and a YAML-formatted configuration file listing all of the software versions, packages, tools, and settings required to achieve the set up the desired state of the development environment on your Windows machine. Minimizing manual project setup and onboarding to a single command that is reliable and repeatable.
ms.date: 2024-11-21T00:00:00.0000000Z
ms.topic: overview
ms.custom: sfi-image-nochange
locale: en-us
document_id: e0e0aecd-b61c-26ae-9bfb-24606f41e9da
document_version_independent_id: e0e0aecd-b61c-26ae-9bfb-24606f41e9da
updated_at: 2025-07-24T05:04:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windows-dev-docs-pr/blob/live/hub/package-manager/configuration/index.md
gitcommit: https://github.com/MicrosoftDocs/windows-dev-docs-pr/blob/7a07985ea18078b5fed1373d60141438c484d8d1/hub/package-manager/configuration/index.md
git_commit_id: 7a07985ea18078b5fed1373d60141438c484d8d1
site_name: Docs
depot_name: MSDN.windows-uwp-hub
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.windows-uwp-hub/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 1032
asset_id: package-manager/configuration/index
moniker_range_name: 
monikers: []
item_type: Content
source_path: hub/package-manager/configuration/index.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: f32d42c5-cdf7-37f8-61ec-3e996f399dfc
---

# WinGet Configuration | Microsoft Learn

Using a WinGet Configuration file, you can consolidate manual machine setup and project onboarding to a single command that is reliable and repeatable. To achieve this, WinGet utilizes:

- A YAML-formatted WinGet Configuration file that lists all of the software versions, packages, tools, dependencies, and settings required to set up the desired state of the development environment on your Windows machine.
- [PowerShell Desired State Configuration (DSC)](/en-us/powershell/dsc/overview) to automate the configuration of your Windows operating system.
- The Windows Package Manager [`winget configure` command](../winget/configure) to initiate the configuration process.

## Benefits for machine setup and project onboarding

The benefits of using a WinGet Configuration file include:

- **Unattended setup**: Enter the `winget configure` command and let Windows Package Manager and PowerShell DSC automate the installation and set up of all the requirements needed to get the desired development environment configured on your Windows machine.
- **Reliable and repeatable**: Remove the worry over finding the right versions of software, packages, tools, frameworks, and configuring the correct machine settings for your development environment when onboarding to a new team or project because they are pre-defined in the WinGet Configuration file using a YAML format (with a JSON schema).
- **Supports Open Source collaboration**: WinGet Configuration files can be hosted in a GitHub repository where issues or contributions can be filed or can be kept private in a secure storage location (like OneDrive) and shared via private email or other secured channels.

Warning

WinGet Configuration files and any associated PowerShell DSC Resources should be checked to ensure that they are trustworthy before applying them.

## Use a WinGet Configuration file to configure your machine

To set up your machine using a WinGet Configuration file, download the configuration file and double-click to invoke the configuration. Alternatively, use [winget configure](../winget/configure) in the command line. To use the `winget configure` command, you must be running WinGet version [v1.6.2631 or later](https://github.com/microsoft/winget-cli/releases).

## WinGet Configuration FAQs

Find answers to some of the most frequently asked questions about WinGet Configuration.

### How do WinGet Configuration files work?

WinGet Configuration files are written in YAML and define what is installed on the device to make up your development environment, as well as the configuration state for your machine and installed applications.

Rather than an imperative sequence of steps to be followed, a WinGet Configuration file is declarative, defining the desired machine configuration state result. By using Windows Package Manager and PowerShell DSC Resources, the declarative WinGet Configuration file can install, configure, and apply settings to your environment resulting in a ready-to-code state.

WinGet will parse the configuration file to ensure it's valid, then download all associated PowerShell modules (containing the DSC resources) required to achieve your desired state. Once these resources have been download and you've [checked the trustworthiness of the WinGet Configuration file](check), agreeing that you've verified the safety of the file, WinGet will begin testing all required [assertions](create#assertions-section) and applying the desired state.

The sequence in which the WinGet Configuration file resources are ordered is inconsequential. Some install and configuration processes may even run in parallel. The assertions directly correspond with the `dependsOn` field defined in each [Resource](create#resources-section). If the resource includes a dependency on an assertion, the assertion will be checked first. If the assertion fails, the dependent resource will also fail. However, the configuration file will continue to run, accomplishing as many tasks as possible, even if some of the assertions or resource dependencies fail, bringing your machine as far along in the set up process as possible before completing. Once the configuration has completed, it is your responsibility to check for any failures.

For example, after running the WinGet Configuration file, you may see a result like:

```powershell
Assert:: OsVersion
The configuration unit could not be found.
Apply :: DeveloperMode
  This configuration unity was not run because an assert failed or was false.
Apply :: WinGetPackage [vsPackage]
  This configuration unity was not run because an assert failed or was false.
```

In this example, the assertion checking for the required version of the Operating System failed, so the DeveloperMode and WinGetPackage resources that included a dependency on that assertion for the operating system version also failed. However, any other installation and configuration tasks listed in the configuration file would continue to move forward.

A benefit to the declarative (non-sequential) nature of WinGet configuration files is that the position of new resources being added to the file does not matter. This is especially helpful for long configuration files as you can just add additional resources to the bottom of the file. As long as you have properly defined the assertions and dependencies, you do not need to be concerned with the sequence, or which set up steps occur first, second, etc.

![Screenshot of a PowerShell terminal running a WinGet Configuration file with the OSVersion assertion and dependent resources failing.](../../images/winget-configuration-results.png)

### How do I use a WinGet Configuration file?

To run a WinGet Configuration file, you can simply double-click to run the file in file explorer. Alternatively, you can use the [`winget configure` command](../winget/configure).

### How do I author a WinGet Configuration?

To create a WinGet Configuration file, follow the guidance in the [How to author a WinGet Configuration file](create) doc.

### How can I assure that a WinGet Configuration file is trustworthy?

We recommend ALWAYS validating the integrity of a WinGet Configuration file before running it by reviewing it's contents and testing the configuration in an isolated environment. See [How to check the trustworthiness of a WinGet Configuration file](check).

### Where can I find sample WinGet Configuration files?

You can find sample WinGet Configuration files in the WinGet DSC repository: https://aka.ms/dsc.yaml.

### Where can I find examples of PowerShell modules containing DSC resources?

The [PowerShell Gallery](https://www.powershellgallery.com/packages) hosts hundreds of PowerShell Modules containing Desired State Configuration (DSC) resources. You can filter search results by applying the “DSC Resource” filter under “Categories”.

![Desired State Configuration PowerShell module search results from the PowerShell Gallery](../../images/winget-config-powershellgallery-dsc-examples.png)

### Can I set up a policy to block the use of WinGet Configuration files in my organization?

Yes. [Group Policy Objects](/en-us/microsoft-365/compliance/device-onboarding-gp)**EnableWindowsPackageManagerConfiguration** and **EnableWindowsPackageManagerConfigurationExplanation** can be utilized for disabling WinGet Configuration feature in your organization.

## Troubleshooting WinGet Configurations

The most common reason for a WinGet Configuration to fail is due to a PowerShell DSC resource requiring administrative access to apply the desired state. Not all DSC resources surface explicit reasons for failure.

More common troubleshooting issues will be added soon. In the meantime, check the related issues filed in the [WinGet CLI repo on GitHub](https://github.com/microsoft/winget-cli/issues?q=is%3Aissue+is%3Aopen+label%3Acommand-configure).

-----

```
C:\>winget configure -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Ensures that the system matches the desired state as described by the provided configuration. May download/execute processors in order to achieve the desired state. The configuration and the processors should be checked to ensure that they are trustworthy before applying them.

usage: winget configure [<command>] [[-f] <file>] [[--module-path] <module-path>] [<options>]

The following command aliases are available:
  configuration
  dsc

The following sub-commands are available:
  show      Shows details of a configuration
  list      Shows configuration history
  test      Checks the system against a desired state
  validate  Validates a configuration file
  export    Exports configuration resources to a configuration file.

For more details on a specific command, pass it the help argument. [-?]

The following arguments are available:
  -f,--file                          The path to the configuration file
  --module-path                      Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

The following options are available:
  --processor-path                   Specify the path to the configuration processor
  -h,--history                       Select items from history
  --accept-configuration-agreements  Accepts the configuration warning, preventing an interactive prompt
  --suppress-initial-details         Suppress showing initial configuration details when possible
  --enable                           Enable extended features. Requires store access.
  --disable                          Disable extended features. Requires store access.
  -?,--help                          Shows help about the selected command
  --wait                             Prompts the user to press any key before exiting
  --logs,--open-logs                 Open the default logs location
  --verbose,--verbose-logs           Enables verbose logging for winget
  --nowarn,--ignore-warnings         Suppresses warning outputs
  --disable-interactivity            Disable interactive prompts
  --proxy                            Set a proxy to use for this execution
  --no-proxy                         Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure

C:\>winget mcp -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

MCP (Model Context Protocol) information for the Windows Package Manager.

usage: winget mcp [<options>]

The following options are available:
  --enable                    Enable extended features. Requires store access.
  --disable                   Disable extended features. Requires store access.
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-mcp

C:\>winget mcp --enable -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

MCP (Model Context Protocol) information for the Windows Package Manager.

usage: winget mcp [<options>]

The following options are available:
  --enable                    Enable extended features. Requires store access.
  --disable                   Disable extended features. Requires store access.
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-mcp

C:\>winget dsc show -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Shows details of the provided configuration. By default, will not modify the system, but some options will cause files to be downloaded and/or loaded.

usage: winget configure show [[-f] <file>] [[--module-path] <module-path>] [<options>]

The following command aliases are available:
  view

The following arguments are available:
  -f,--file                   The path to the configuration file
  --module-path               Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

The following options are available:
  --processor-path            Specify the path to the configuration processor
  -h,--history                Select items from history
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure#show

C:\>winget dsc list -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Shows the high level details for configurations that have been applied to the system. This data can then be used with `configure` commands to get more details.

usage: winget configure list [<options>]

The following command aliases are available:
  ls

The following options are available:
  -h,--history                Select items from history
  -o,--output                 File where the result is to be written
  --remove                    Remove the item from history
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure#list

C:\>winget dsc test -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Checks that the system matches the desired state as described by the provided configuration. May download/execute processors in order to test the desired state. The configuration and the processors should be checked to ensure that they are trustworthy before executing them.

usage: winget configure test [[-f] <file>] [[--module-path] <module-path>] [<options>]

The following arguments are available:
  -f,--file                          The path to the configuration file
  --module-path                      Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

The following options are available:
  --processor-path                   Specify the path to the configuration processor
  -h,--history                       Select items from history
  --suppress-initial-details         Suppress showing initial configuration details when possible
  --accept-configuration-agreements  Accepts the configuration warning, preventing an interactive prompt
  -?,--help                          Shows help about the selected command
  --wait                             Prompts the user to press any key before exiting
  --logs,--open-logs                 Open the default logs location
  --verbose,--verbose-logs           Enables verbose logging for winget
  --nowarn,--ignore-warnings         Suppresses warning outputs
  --disable-interactivity            Disable interactive prompts
  --proxy                            Set a proxy to use for this execution
  --no-proxy                         Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure#test

C:\>winget dsc validate -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Validates a configuration file for correctness.

usage: winget configure validate [-f] <file> [[--module-path] <module-path>] [<options>]

The following arguments are available:
  -f,--file                   The path to the configuration file
  --module-path               Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules

The following options are available:
  --processor-path            Specify the path to the configuration processor
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure#validate

C:\>winget dsc export -?
Windows Package Manager v1.28.240
Copyright (c) Microsoft Corporation. All rights reserved.

Exports configuration resources to a configuration file. When used with --all, exports all package configurations. When used with --packageId, exports a WinGetPackage resource of the given package id. When used with --module and --resource, gets the settings of the resource and exports it to the configuration file. If the output configuration file already exists, appends the exported configuration resources.

usage: winget configure export [<options>]

The following options are available:
  -o,--output                 File where the result is to be written
  --package-id                The package identifier to export.
  --module                    The module of the resource to export.
  --resource                  The configuration resource to export.
  --module-path               Specifies the location on the local computer to store modules. Default %LOCALAPPDATA%\Microsoft\WinGet\Configuration\Modules
  --processor-path            Specify the path to the configuration processor
  -s,--source                 Export packages from the specified source
  --include-versions          Include package versions in export file
  -r,--recurse,--all          Exports all package configurations.
  --accept-source-agreements  Accept all source agreements during source operations
  -?,--help                   Shows help about the selected command
  --wait                      Prompts the user to press any key before exiting
  --logs,--open-logs          Open the default logs location
  --verbose,--verbose-logs    Enables verbose logging for winget
  --nowarn,--ignore-warnings  Suppresses warning outputs
  --disable-interactivity     Disable interactive prompts
  --proxy                     Set a proxy to use for this execution
  --no-proxy                  Disable the use of proxy for this execution

More help can be found at: https://aka.ms/winget-command-configure#export

C:\>
```

Help at https://github.com/microsoft/winget-dsc/tree/main/samples
