

# nslookup

Displays information that you can use to diagnose Domain Name System (DNS) infrastructure. Before using this tool, you should be familiar with how DNS works. The nslookup command-line tool is available only if you have installed the TCP/IP protocol.

## Syntax

```
nslookup [exit | finger | help | ls | lserver | root | server | set | view] [options]
```

### Parameters

| Parameter | Description |
| --- | --- |
| [nslookup exit](nslookup-exit-command) | Exits the nslookup command-line tool. |
| [nslookup finger](nslookup-finger-command) | Connects with the finger server on the current computer. |
| [nslookup help](nslookup-help) | Displays a short summary of subcommands. |
| [nslookup ls](nslookup-ls) | Lists information for a DNS domain. |
| [nslookup lserver](nslookup-lserver) | Changes the default server to the specified DNS domain. |
| [nslookup root](nslookup-root) | Changes the default server to the server for the root of the DNS domain name space. |
| [nslookup server](nslookup-server) | Changes the default server to the specified DNS domain. |
| [nslookup set](nslookup-set) | Changes configuration settings that affect how lookups function. |
| [nslookup set all](nslookup-set-all) | Prints the current values of the configuration settings. |
| [nslookup set class](nslookup-set-class) | Changes the query class. The class specifies the protocol group of the information. |
| [nslookup set d2](nslookup-set-d2) | Turns exhaustive Debugging mode on or off. All fields of every packet are printed. |
| [nslookup set debug](nslookup-set-debug) | Turns Debugging mode on or off. |
| [nslookup set domain](nslookup-set-domain) | Changes the default DNS domain name to the name specified. |
| [nslookup set port](nslookup-set-port) | Changes the default TCP/UDP DNS name server port to the value specified. |
| [nslookup set querytype](nslookup-set-querytype) | Changes the resource record type for the query. |
| [nslookup set recurse](nslookup-set-recurse) | Tells the DNS name server to query other servers if it doesn't have the information. |
| [nslookup set retry](nslookup-set-retry) | Sets the number of retries. |
| [nslookup set root](nslookup-set-root) | Changes the name of the root server used for queries. |
| [nslookup set search](nslookup-set-search) | Appends the DNS domain names in the DNS domain search list to the request until an answer is received. This applies when the set and the lookup request contain at least one period, but do not end with a trailing period. |
| [nslookup set srchlist](nslookup-set-srchlist) | Changes the default DNS domain name and search list. |
| [nslookup set timeout](nslookup-set-timeout) | Changes the initial number of seconds to wait for a reply to a request. |
| [nslookup set type](nslookup-set-type) | Changes the resource record type for the query. |
| [nslookup set vc](nslookup-set-vc) | Specifies to use or not use a virtual circuit when sending requests to the server. |
| [nslookup view](nslookup-view) | Sorts and lists the output of the previous **ls** subcommand or commands. |

### Remarks

- The nslookup command-line tool has two modes: interactive and noninteractive.

    - If you need to look up only a single piece of data, or you're using nslookup in scripts, command lines, or PowerShell, use the noninteractive mode. In noninteractive mode, also called command mode, the first command line parameter is the name or IP address of the computer that you want to look up. The second parameter is the name or IP address of a DNS name server. If you omit the second argument, nslookup uses the default DNS name server.
    - If you need to look up more than one piece of data or set several configurations, you can use interactive mode. To enter interactive mode, type a hyphen (-) instead of the first parameter in the nslookup command line. Enter the name or IP address of a DNS name server for the second parameter. If you omit the second argument, nslookup uses the default DNS name server. You can also invoke interactive mode by simply entering `nslookup` at the command prompt, and then entering names or IP addresses to search for in the interactive command line.
- Once you enter `nslookup -` or `nslookup` alone, the command prompt changes to the interactive prompt `>`. While in interactive mode, you can:

    - Enter names or IP addresses, `set` variables, and other options on separate lines.
    - Interrupt interactive commands at any time by pressing CTRL+B.
    - Exit, by entering `exit`.
    - Treat a built-in command as a computer name by preceding it with the escape character (`\`). An unrecognized command is interpreted as a computer name.
- If the computer to find is an IP address and the query is for an **A** or **PTR** resource record type, the name of the computer is returned.
- If the computer to find is a name and doesn't have a trailing period, the default DNS domain name is appended to the name. This behavior depends on the state of the following **set** subcommands: **domain**, **srchlist**, **defname**, and **search**.
- If the lookup request fails, the command-line tool provides one of the following error messages:

    | Error message | Description |
    | --- | --- |
    | timed out | The server didn't respond to a request after a certain amount of time and a certain number of retries. You can set the time-out period with the [nslookup set timeout](nslookup-set-timeout) command. You can set the number of retries with the [nslookup set retry](nslookup-set-retry) command. |
    | No response from server | No DNS name server is running on the server computer. |
    | No records | The DNS name server doesn't have resource records of the current query type for the computer, although the computer name is valid. The query type is specified with the [nslookup set querytype](nslookup-set-querytype) command. |
    | Nonexistent domain | The computer or DNS domain name doesn't exist. |
    | Connection refused or Network is unreachable | The connection to the DNS name server or finger server couldn't be made. This error commonly occurs with the **ls** and **finger** requests. |
    | Server failure | The DNS name server found an internal inconsistency in its database and couldn't return a valid answer. |
    | Refused | The DNS name server refused to service the request. |
    | format error | The DNS name server found that the request packet wasn't in the proper format. It may indicate an error in **nslookup**. |

## Examples

In nslookup noninteractive mode, you specify parameters and options in the Windows command line or script. In interactive mode, you specify arguments and options on separate lines at the interactive command prompt.

### Noninteractive mode

In nslookup noninteractive mode, the first parameter is the computer to find, and the second parameter is the DNS name server to use. If you don't specify a second parameter, nslookup uses the default DNS name server. The following examples use `nslookup` in noninteractive mode.

- The following example looks up the IP addresses for the domain name `mydomain.com` on the DNS name server at `1.1.1.1`:

    ```cmd
    nslookup mydomain.com 1.1.1.1
    ```
- The following example looks up the domain name for the IP address `4.4.4.4` on the default DNS name server:

    ```cmd
    nslookup 4.4.4.4
    ```
- To specify options, you can use `nslookup -<option>`. For example, the following command turns on the nslookup `debug` option to get more information about packets sent.

    ```cmd
    nslookup -debug mydomain.com
    ```
- To return certain types of records or information, use the `-type=<resourcerecordtype>` option. For example, the following command returns only IPv6 record types:

    ```cmd
    nslookup -type=AAAA mydomain.com
    ```
- You can combine options and resource record type queries in command lines. The following example enables debug output, retrieves both IPv6 and IPv4 addresses, doesn't attempt to use the search domain, uses recursive lookup, and uses the 1.1.1.1 DNS lookup server:

    ```cmd
    nslookup -debug -type=A+AAAA -nosearch -recurse mydomain.com 1.1.1.1
    ```

### Interactive mode

To use interactive mode, enter `-` instead of the first parameter of a nslookup command line, or simply enter `nslookup`. The command prompt then changes to the interactive prompt `>`. The following examples show interactive mode commands.

- The following command places nslookup in interactive mode and sets `1.1.1.1` as the default DNS lookup server:

    ```cmd
    nslookup - 1.1.1.1
    ```
- The following command at the interactive prompt returns nslookup option and parameter settings for the current server:

    ```cmd
    set all
    ```
- The following command at the interactive prompt returns the IP addresses for `mydomain.com`:

    ```cmd
    mydomain.com
    ```
- The following command at the interactive prompt changes the default DNS name server to `4.4.4.4`:

    ```cmd
    server 4.4.4.4
    ```
- The following command at the interactive prompt sets the query resource record type to `HINFO`:

    ```cmd
    set type=HINFO
    ```
- The following command at the interactive prompt exits interactive mode and returns to the Windows command prompt:

    ```cmd
    exit
    ```

-----

# nslookup exit | Microsoft Learn

Exits the nslookup command-line tool.

## Syntax

```
nslookup /exit
```

### Parameters

| Parameter | Description |
| --- | --- |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

-----

# nslookup set all

Outputs the current configuration setting values, including the default server and computer (the host).

## Syntax

```
set all
```

### Parameters

| Parameter | Description |
| --- | --- |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

```
Set options:
  nodebug
  defname
  search
  recurse
  nod2
  novc
  noignoretc
  port=53
  type=A+AAAA
  class=IN
  timeout=2
  retry=1
  root=A.ROOT-SERVERS.NET.
  domain=lan
  MSxfr
  IXFRversion=1
  srchlist=lan

>
```

-----

# nslookup help

Displays the subcommand help text.

## Syntax

```
help
```

```
?
```

### Parameters

| Parameter | Description |
| --- | --- |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

-----

```
> help
Commands:   (identifiers are shown in uppercase, [] means optional)
NAME            - print info about the host/domain NAME using default server
NAME1 NAME2     - as above, but use NAME2 as server
help or ?       - print info on common commands
set OPTION      - set an option
    all                 - print options, current server and host
    [no]debug           - print debugging information
    [no]d2              - print exhaustive debugging information
    [no]defname         - append domain name to each query
    [no]recurse         - ask for recursive answer to query
    [no]search          - use domain search list
    [no]vc              - always use a virtual circuit
    domain=NAME         - set default domain name to NAME
    srchlist=N1[/N2/.../N6] - set domain to N1 and search list to N1,N2, etc.
    root=NAME           - set root server to NAME
    retry=X             - set number of retries to X
    timeout=X           - set initial time-out interval to X seconds
    type=X              - set query type (ex. A,AAAA,A+AAAA,ANY,CNAME,MX,NS,PTR,SOA,SRV)
    querytype=X         - same as type
    class=X             - set query class (ex. IN (Internet), ANY)
    [no]msxfr           - use MS fast zone transfer
    ixfrver=X           - current version to use in IXFR transfer request
server NAME     - set default server to NAME, using current default server
lserver NAME    - set default server to NAME, using initial server
root            - set current default server to the root
ls [opt] DOMAIN [> FILE] - list addresses in DOMAIN (optional: output to FILE)
    -a          -  list canonical names and aliases
    -d          -  list all records
    -t TYPE     -  list records of the given RFC record type (ex. A,CNAME,MX,NS,PTR etc.)
view FILE           - sort an 'ls' output file and view it with pg
exit            - exit the program

>
```

-----

# nslookup server | Microsoft Learn

Changes the default server to the specified Domain Name System (DNS) domain.

This command uses the current default server to look up the information about the specified DNS domain. If you want to lookup information using the initial server, use the [nslookup lserver](nslookup-lserver) command.

## Syntax

```
server <DNSdomain>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<DNSdomain>` | Specifies the DNS domain for the default server. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup lserver](nslookup-lserver)

-----

# nslookup ls | Microsoft Learn

Lists DNS domain information.

## Syntax

```
ls [<option>] <DNSdomain> [{[>] <filename>|[>>] <filename>}]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<option>` | The valid options include:<br>- **-t:** Lists all records of the specified type. For more information, see [nslookup set querytype](nslookup-set-querytype).<br>- **-a:** Lists aliases of computers in the DNS domain. This parameter is the same as **-t CNAME**<br>- **-d:** Lists all records for the DNS domain. This parameter is the same as **-t ANY**<br>- **-h:** Lists CPU and operating system information for the DNS domain. This parameter is the same as **-t HINFO**<br>- **-s:** Lists well-known services of computers in the DNS domain. This parameter is the same as **-t WKS**. |
| `<DNSdomain>` | Specifies the DNS domain for which you want information. |
| `<filename>` | Specifies a file name to use for the saved output. You can use the greater than (`>`) and double greater than (`>>`) characters to redirect the output in the usual manner. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

#### Remarks

- The default output of this command includes computer names and their associated IP addresses.
- If your output is directed to a file, hash marks are added for every 50 records received from the server.

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set querytype](nslookup-set-querytype)

-----

# nslookup finger

Connects with the [finger server]() on the current device.

## Syntax

```
finger [<username>] [{[>] <filename> | [>>] <filename>}]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<username>` | Specifies the name of the user to look up. |
| `<filename>` | Specifies a file name in which to save the output. You can use the greater than (`>`) and double greater than (`>>`) characters to redirect the output in the usual manner. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [finger](wikipedia article)

-----

# nslookup lserver | Microsoft Learn

Changes the initial server to the specified Domain Name System (DNS) domain.

This command uses the initial server to look up the information about the specified DSN domain. If you want to lookup information using the current default server, use the [nslookup server](nslookup-server) command.

## Syntax

```
lserver <DNSdomain>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<DNSdomain>` | Specifies the DNS domain for the initial server. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup server](nslookup-server)

-----

# nslookup root | Microsoft Learn

Changes the default server to the server for the root of the Domain Name System (DNS) domain name space. Currently, the ns.nic.ddn.mil name server is used. You can change the name of the root server using the [nslookup set root](nslookup-set-root) command.

Note

This command is the same as `lserver ns.nic.ddn.mil`.

## Syntax

```
root
```

### Parameters

| Parameter | Description |
| --- | --- |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set root](nslookup-set-root)
- root servers list

-----

# nslookup view

Sorts and lists the output of the previous **ls** commands or subcommands.

## Syntax

```
view <filename>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<filename>` | Specifies the name of the file containing output from the previous **ls** commands or subcommands. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup ls](nslookup-ls)

-----
-----

# nslookup set | Microsoft Learn

Changes configuration settings that affect how lookups function.

## Syntax

```
set all [class | d2 | debug | domain | port | querytype | recurse | retry | root | search | srchlist | timeout | type | vc] [options]
```

### Parameters

| Parameter | Description |
| --- | --- |
| [nslookup set all](nslookup-set-all) | Lists all current settings. |
| [nslookup set class](nslookup-set-class) | Changes the query class, which specifies the protocol group of the information. |
| [nslookup set d2](nslookup-set-d2) | Turns the verbose debugging mode on or off. |
| [nslookup set debug](nslookup-set-debug) | Turns off debugging mode completely. |
| [nslookup set domain](nslookup-set-domain) | Changes the default Domain Name System (DNS) domain name to the specified name. |
| [nslookup set port](nslookup-set-port) | Changes the default TCP/UDP Domain Name System (DNS) name server port to the specified value. |
| [nslookup set querytype](nslookup-set-querytype) | Changes the resource record type for the query. |
| [nslookup set recurse](nslookup-set-recurse) | Tells the Domain Name System (DNS) name server to query other servers if it doesn't find any information. |
| [nslookup set retry](nslookup-set-retry) | Sets the number of retries. |
| [nslookup set root](nslookup-set-root) | Changes the name of the root server used for queries. |
| [nslookup set search](nslookup-set-search) | Appends the Domain Name System (DNS) domain names in the DNS domain search list to the request until an answer is received. |
| [nslookup set srchlist](nslookup-set-srchlist) | Changes the default Domain Name System (DNS) domain name and search list. |
| [nslookup set timeout](nslookup-set-timeout) | Changes the initial number of seconds to wait for a reply to a lookup request. |
| [nslookup set type](nslookup-set-type) | Changes the resource record type for the query. |
| [nslookup set vc](nslookup-set-vc) | Specifies whether to use a virtual circuit when sending requests to the server. |

-----

---
layout: Conceptual
title: nslookup set class | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-class
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set class command, which changes the query class.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 2808d0cb-b9b7-3250-8669-bfbf7ab08363
document_version_independent_id: 089ce72c-1340-6cfb-cd34-4f35325edbea
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-class.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-class.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 75
asset_id: administration/windows-commands/nslookup-set-class
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-class.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 405db201-1e98-d486-f611-ae9bd8206bfd
---

# nslookup set class | Microsoft Learn

Changes the query class. The class specifies the protocol group of the information.

## Syntax

```
set class=<class>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<class>` | The valid values include:<br>- **IN:** Specifies the Internet class. This is the default value.<br>- **CHAOS:** Specifies the Chaos class.<br>- **HESIOD:** Specifies the MIT Athena Hesiod class.<br>- **ANY:** Specifies to use any of the previously listed values. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set d2 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-d2
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set d2 command, which turns the verbose debugging mode on or off.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 140973eb-4b2f-22de-2510-8e18bf122d37
document_version_independent_id: 1adf79e4-22c0-7623-4d88-869959ead301
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-d2.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-d2.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 59
asset_id: administration/windows-commands/nslookup-set-d2
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-d2.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 518f6052-838a-4935-e2ed-f3d068486ffc
---

# nslookup set d2 | Microsoft Learn

Turns the verbose debugging mode on or off. All fields of every packet are printed.

## Syntax

```
set [no]d2
```

### Parameters

| Parameter | Description |
| --- | --- |
| nod2 | Turns off the verbose debugging mode. This is the default value. |
| d2 | Turns on the verbose debugging mode. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set debug | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-debug
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set debug command, which turns debugging mode on and off.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: ca981abd-66f9-5c19-80d7-61a5213c0ae6
document_version_independent_id: 6f9b8c18-86af-f5c1-c3d0-a6ddf3c3bfd3
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-debug.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-debug.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 67
asset_id: administration/windows-commands/nslookup-set-debug
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-debug.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 1d7d3cab-e98c-371c-78d8-58cc2a3ee0bd
---

# nslookup set debug | Microsoft Learn

Turns debugging mode on or off.

## Syntax

```
set [no]debug
```

### Parameters

| Parameter | Description |
| --- | --- |
| nodebug | Turns off debugging mode. This is the default value. |
| debug | Turns on debugging mode. By turning debugging mode on, you can view more information about the packet sent to the server and the resulting answer. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set domain | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-domain
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set domain command, which changes the default Domain Name System (DNS) domain name to the specified name.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: df87ebc9-e238-8898-9b4f-2c3eab0cf71c
document_version_independent_id: 9f4f3dde-3d53-526a-3095-402601d1c4c5
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-domain.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-domain.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 148
asset_id: administration/windows-commands/nslookup-set-domain
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-domain.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 8d1d7f22-b9bd-7a8f-3c39-f98b578f2b87
---

# nslookup set domain | Microsoft Learn

Changes the default Domain Name System (DNS) domain name to the specified name.

## Syntax

```
set domain=<domainname>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<domainname>` | Specifies a new name for the default DNS domain name. The default value is the name of the host. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

#### Remarks

- The default DNS domain name is appended to a lookup request depending on the state of the **defname** and **search** options.
- The DNS domain search list contains the parents of the default DNS domain if it has at least two components in its name. For example, if the default DNS domain is mfg.widgets.com, the search list is named both mfg.widgets.com and widgets.com.
- Use the [nslookup set srchlist](nslookup-set-srchlist) command to specify a different list and the [nslookup set all](nslookup-set-all) command to display the list.

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set srchlist](nslookup-set-srchlist)
- [nslookup set all](nslookup-set-all)

-----

---
layout: Conceptual
title: nslookup set port | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-port
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set port command, which changes the default TCP/UDP Domain Name System (DNS) name server port to the specified value.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 18860a13-6725-5946-78a8-22d4dee1dcc8
document_version_independent_id: f164705d-64ac-4e1b-eef9-f94c56da0789
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-port.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-port.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 58
asset_id: administration/windows-commands/nslookup-set-port
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-port.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 1a009fe5-ce08-7a1c-6723-f557f8821b37
---

# nslookup set port | Microsoft Learn

Changes the default TCP/UDP Domain Name System (DNS) name server port to the specified value.

## Syntax

```
set port=<port>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<port>` | Specifies the new value for the default TCP/UDP DNS name server port. The default port is **53**. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set querytype | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-querytype
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set querytype command, which changes the resource record type for the query.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 66c02bef-26d7-1e6d-ed3d-2a692e1d5592
document_version_independent_id: 08ee1cc8-07c7-ea85-0062-a32e249d97ab
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-querytype.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-querytype.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 210
asset_id: administration/windows-commands/nslookup-set-querytype
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-querytype.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: f2661adf-b9f2-288b-a9c9-44e07111be49
---

# nslookup set querytype | Microsoft Learn

Changes the resource record type for the query. For information about resource record types, see [Request for Comment (Rfc) 1035](https://tools.ietf.org/html/rfc1035).

Note

This command is the same as the [nslookup set type](nslookup-set-type) command.

## Syntax

```
set querytype=<resourcerecordtype>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<resourcerecordtype>` | Specifies a DNS resource record type. The default resource record type is **A**, but you can use any of the following values:<br>- **A:** Specifies a computer's IP address.<br>- **ANY:** Specifies a computer's IP address.<br>- **CNAME:** Specifies a canonical name for an alias.<br>- **GID** Specifies a group identifier of a group name.<br>- **HINFO:** Specifies a computer's CPU and type of operating system.<br>- **MB:** Specifies a mailbox domain name.<br>- **MG:** Specifies a mail group member.<br>- **MINFO:** Specifies mailbox or mail list information.<br>- **MR:** Specifies the mail rename domain name.<br>- **MX:** Specifies the mail exchanger.<br>- **NS:** Specifies a DNS name server for the named zone.<br>- **PTR:** Specifies a computer name if the query is an IP address; otherwise, specifies the pointer to other information.<br>- **SOA:** Specifies the start-of-authority for a DNS zone.<br>- **TXT:** Specifies the text information.<br>- **UID:** Specifies the user identifier.<br>- **UINFO:** Specifies the user information.<br>- **WKS:** Describes a well-known service. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set type](nslookup-set-type)

-----

---
layout: Conceptual
title: nslookup set recurse | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-recurse
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set recurse command, which tells the Domain Name System (DNS) name server to query other servers if it can't find the information on the specified server.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: ca35cfc7-407d-725e-3656-e64919084b17
document_version_independent_id: 3b8a3c2e-5b57-cbf3-cccb-685eca5dc55d
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-recurse.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-recurse.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 98
asset_id: administration/windows-commands/nslookup-set-recurse
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-recurse.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: f2199019-1f55-5fd2-5eeb-9be18ffa0476
---

# nslookup set recurse | Microsoft Learn

Tells the Domain Name System (DNS) name server to query other servers if it can't find the information on the specified server.

## Syntax

```
set [no]recurse
```

### Parameters

| Parameter | Description |
| --- | --- |
| norecurse | Stops the Domain Name System (DNS) name server from querying other servers if it can't find the information on the specified server. |
| recurse | Tells the Domain Name System (DNS) name server to query other servers if it can't find the information on the specified server. This is the default value. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set retry | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-retry
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set retry command, which sets the number of tries to get information from a specified server.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: baa693b9-b517-7041-ff8b-cd4bcc269425
document_version_independent_id: 95f41462-7284-1752-af6a-b31d5b072e3c
updated_at: 2025-10-30T17:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-retry.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/b6156289953085ec5fa6e401fb5c02ce0a31ebac/WindowsServerDocs/administration/windows-commands/nslookup-set-retry.md
git_commit_id: b6156289953085ec5fa6e401fb5c02ce0a31ebac
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 82
asset_id: administration/windows-commands/nslookup-set-retry
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-retry.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 217947f5-9493-494c-6264-de797e71c4e6
---

# nslookup set retry | Microsoft Learn

This command sets the number of times a request is resent to a server for information, before giving up.

Note

To change the length of time before the request times out, use the [nslookup set timeout](nslookup-set-timeout) command.

## Syntax

```
set retry=<number>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<number>` | Specifies the new value for the number of retries. The default number of retries is **1**. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set timeout](nslookup-set-timeout)

-----

---
layout: Conceptual
title: nslookup set root | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-root
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set root command, which changes the name of the root server that's used for queries.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 629cc99a-4529-8fff-9c21-b3e26b31027c
document_version_independent_id: a76ec88d-be84-f0e9-21bf-c8d7e2d0b9de
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-root.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-root.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 59
asset_id: administration/windows-commands/nslookup-set-root
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-root.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 67434680-11b4-c860-d12e-e5f6beec9aa0
---

# nslookup set root | Microsoft Learn

Changes the name of the root server used for queries.

Note

This command supports the [nslookup root](nslookup-root) command.

## Syntax

```
set root=<rootserver>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<rootserver>` | Specifies the new name for the root server. The default value is **ns.nic.ddn.mil**. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup root](nslookup-root)

-----

---
layout: Conceptual
title: nslookup set search | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-search
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set search command, which appends the Domain Name System (DNS) domain names in the DNS domain search list to the request until an answer is received.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: fa7358c4-131a-6b46-c4f0-0317aa8d8d49
document_version_independent_id: f768be28-bcc5-642c-14c2-0071ba04238c
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-search.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-search.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 116
asset_id: administration/windows-commands/nslookup-set-search
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-search.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 9717e48b-0ca3-9898-765d-a2799ef20044
---

# nslookup set search | Microsoft Learn

Appends the Domain Name System (DNS) domain names in the DNS domain search list to the request until an answer is received. This applies when the set and the lookup request contain at least one period, but do not end with a trailing period.

## Syntax

```
set [no]search
```

### Parameters

| Parameter | Description |
| --- | --- |
| nosearch | Stops appending the Domain Name System (DNS) domain names in the DNS domain search list for the request. |
| search | Appends the Domain Name System (DNS) domain names in the DNS domain search list for the request until an answer is received. This is the default value. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

-----

---
layout: Conceptual
title: nslookup set srchlist | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-srchlist
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set srchlist command, which changes the default Domain Name System (DNS) domain name and search list.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 1271ad1c-99da-d014-83f4-990ecea80db7
document_version_independent_id: 047b5878-431e-b19b-82d8-cdbcecc7982f
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-srchlist.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-srchlist.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 124
asset_id: administration/windows-commands/nslookup-set-srchlist
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-srchlist.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: aea137f8-7a4f-7d65-4672-1dfe9e2b13c4
---

# nslookup set srchlist | Microsoft Learn

Changes the default Domain Name System (DNS) domain name and search list. This command overrides the default DNS domain name and search list of the [nslookup set domain](nslookup-set-domain) command.

## Syntax

```
set srchlist=<domainname>[/...]
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<domainname>` | Specifies new names for the default DNS domain and search list. The default domain name value is based on the host name. You can specify a maximum of six names separated by slashes (/). |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

#### Remarks

- Use the [nslookup set all](nslookup-set-all) command to display the list.

### Examples

To set the DNS domain to *mfg.widgets.com* and the search list to the three names:

```
set srchlist=mfg.widgets.com/mrp2.widgets.com/widgets.com
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set domain](nslookup-set-domain)
- [nslookup set all](nslookup-set-all)

-----

---
layout: Conceptual
title: nslookup set timeout | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-timeout
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set timeout command, which changes the initial number of seconds to wait for a reply to a lookup request.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: c16b7395-b08e-1cdd-1c17-c502e96bc0f5
document_version_independent_id: b1f4227c-b27e-27c7-35f2-774d0b387ed2
updated_at: 2025-10-30T17:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-timeout.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/fe2f1648ea01ca74e57b6fa97fc166835dcd5206/WindowsServerDocs/administration/windows-commands/nslookup-set-timeout.md
git_commit_id: fe2f1648ea01ca74e57b6fa97fc166835dcd5206
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 94
asset_id: administration/windows-commands/nslookup-set-timeout
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-timeout.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 6e5339f7-8ff0-0439-2f0c-e6769e68f1ad
---

# nslookup set timeout | Microsoft Learn

Changes the number of seconds to wait for a reply to a lookup request. Use the [nslookup set retry](nslookup-set-retry) command to determine the number of times to try to send the request.

## Syntax

```
set timeout=<number>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<number>` | Specifies the number of seconds to wait for a reply. The default number of seconds to wait is **2**. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

### Examples

To set the timeout for getting a response to 5 seconds:

```
set timeout=5
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set retry](nslookup-set-retry)

-----

---
layout: Conceptual
title: nslookup set type | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-type
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set type command, which changes the resource record type for the query.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: c3a37213-4994-3137-aeff-67b92f05b321
document_version_independent_id: 59b93afc-5deb-23d6-48e2-ac82d7089b82
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-type.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-type.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 210
asset_id: administration/windows-commands/nslookup-set-type
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-type.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 5f11cc12-0e5a-977b-cea7-25c19dfa7d44
---

# nslookup set type | Microsoft Learn

Changes the resource record type for the query. For information about resource record types, see [Request for Comment (Rfc) 1035](https://tools.ietf.org/html/rfc1035).

Note

This command is the same as the [nslookup set querytype](nslookup-set-querytype) command.

## Syntax

```
set type=<resourcerecordtype>
```

### Parameters

| Parameter | Description |
| --- | --- |
| `<resourcerecordtype>` | Specifies a DNS resource record type. The default resource record type is **A**, but you can use any of the following values:<br>- **A:** Specifies a computer's IP address.<br>- **ANY:** Specifies a computer's IP address.<br>- **CNAME:** Specifies a canonical name for an alias.<br>- **GID** Specifies a group identifier of a group name.<br>- **HINFO:** Specifies a computer's CPU and type of operating system.<br>- **MB:** Specifies a mailbox domain name.<br>- **MG:** Specifies a mail group member.<br>- **MINFO:** Specifies mailbox or mail list information.<br>- **MR:** Specifies the mail rename domain name.<br>- **MX:** Specifies the mail exchanger.<br>- **NS:** Specifies a DNS name server for the named zone.<br>- **PTR:** Specifies a computer name if the query is an IP address; otherwise, specifies the pointer to other information.<br>- **SOA:** Specifies the start-of-authority for a DNS zone.<br>- **TXT:** Specifies the text information.<br>- **UID:** Specifies the user identifier.<br>- **UINFO:** Specifies the user information.<br>- **WKS:** Describes a well-known service. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [nslookup set type](nslookup-set-querytype)

-----

---
layout: Conceptual
title: nslookup set vc | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup-set-vc
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for the nslookup set vc command, which specifies whether to use a virtual circuit when sending requests to the server.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 31a8db1d-87c1-f5ee-b560-ed3750a413c2
document_version_independent_id: e80ea173-9312-fc97-1a3d-9242967d713a
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/nslookup-set-vc.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/nslookup-set-vc.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 71
asset_id: administration/windows-commands/nslookup-set-vc
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/nslookup-set-vc.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: a840b098-4e56-4563-f28f-229d38db3fc4
---

# nslookup set vc | Microsoft Learn

Specifies whether to use a virtual circuit when sending requests to the server.

## Syntax

```
set [no]vc
```

### Parameters

| Parameter | Description |
| --- | --- |
| novc | Specifies to never use a virtual circuit when sending requests to the server. This is the default value. |
| vc | Specifies to always use a virtual circuit when sending requests to the server. |
| /? | Displays help at the command prompt. |
| /help | Displays help at the command prompt. |

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)

