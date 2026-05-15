
Packet Monitor (Pktmon) is an in-box, cross-component network diagnostics tool for Windows. It can be used for advanced packet capture and event collection, drop detection, filtering, and counting. Pktmon is especially helpful in virtualization scenarios such as container networking and SDN, because it provides visibility within the networking stack.

`pktmon { filter | list | start | stop | status | unload | counters | reset | etl2txt | etl2pcap | hex2pkt | help } [options]`

|  Command  |  Description  |
|  -----  |  -----  |
| pktmon filter | Manage packet filters. |
| pktmon list | List packet processing components. |
| pktmon start | Start packet capture and event collection. |
| pktmon stop | Stop data collection. |
| pktmon status | Query current status. |
| pktmon unload | Unload PktMon driver. |
| pktmon counters | Display current packet counters. |
| pktmon reset | Reset packet counters to zero. |
| pktmon etl2txt | Convert log file to text format. |
| pktmon etl2pcap | Convert log file to pcapng format. |
| pktmon hex2pkt | Decode packet in hexadecimal format. |
| pktmon help | Show help text for specific command. |


### Related links
- [Packet Monitor overview](https://learn.microsoft.com/en-us/windows-server/networking/technologies/pktmon/pktmon)
- [Pktmon support for Microsoft Network Monitor (Netmon)](https://learn.microsoft.com/en-us/windows-server/networking/technologies/pktmon/pktmon-netmon-support)

```
C:\>pktmon /?
pktmon <command> [OPTIONS | help]
    Advanced packet capture and event collection.

Commands
    filter     Manage packet filters.
    list       List packet processing components.

    start      Start packet capture and event collection.
    stop       Stop data collection.
    status     Query current status.
    unload     Unload PktMon driver.

    counters   Display current packet counters.
    reset      Reset packet counters to zero.

    etl2txt    Convert log file to text format.
    etl2pcap   Convert log file to pcapng format.
    hex2pkt    Decode packet in hexadecimal format.

    help       Show help text for specific command.
               Example: pktmon start help


C:\>pktmon list help
pktmon list [--all] [--include-hidden] [--json]
    List networking components that can be monitored.

-a, --all
    Show all component types. Only network adapters are
    displayed by default.

-i, --include-hidden
    Show components that are hidden by default.

--json
    Output in JSON format. Implies -i and -a.


C:\>pktmon filter help
pktmon filter <command> [OPTIONS | help]

Commands
    add       Add a filter to control which packets are reported.
    list      Display active packet filters.
    remove    Removes all packet filters.

    help      Show help text for specific command.
              Example: pktmon filter add help


C:\>pktmon start help
pktmon start [--capture [--counters-only] [--comp <selector>] [--type <type>]
                        [--pkt-size <bytes>] [--flags <mask>]]
             [--trace --provider <name> [--keywords <k>] [--level <n>] ...]
             [--file-name <name>] [--file-size <size>] [--log-mode <mode>]
    Start packet capture and event collection.

Packet Capture
    -c, --capture
        Enable packet capture and packet counters.

        -o, --counters-only
            Collect packet counters only. No packet logging.

        --comp { all | nics | id1 id2 ... }
            Select components to capture packets on. Can be ALL components,
            NICs only, or a list of component Ids. Default is ALL.

        --type { all | flow | drop }
            Select which packets to capture. Default is ALL.

        --pkt-size <bytes>
            Number of bytes to log from each packet. To always log the entire
            packet set this to 0. Default is 128 bytes.

        --flags <mask>
            Hexadecimal bitmask that controls information logged during packet
            capture. Default is 0x012.

            0x001 - Internal Packet Monitor errors.
            0x002 - Information about components, counters and filters.
            0x004 - NET_BUFFER_LIST group source and destination information.
            0x008 - Select packet metadata from NDIS_NET_BUFFER_LIST_INFO.
            0x010 - Raw packet, truncated to the size from --pkt-size.

Event Providers
    -t, --trace
        Enable event collection.

        -p, --provider <name>
            Event provider name or GUID. For multiple providers, use this
            parameter more than once.

        -k, --keywords <k>
            Hexadecimal bitmask that controls which events are logged
            for the corresponding provider. Default is 0xFFFFFFFF.

        -l, --level <n>
            Logging level for the corresponding provider.
            Default is 4 (info level).

Logging Parameters
    -f, --file-name <name>
        Log file name. Default is PktMon.etl.

    -s, --file-size <size>
        Maximum log file size in megabytes. Default is 512 MB.

    -m, --log-mode { circular | multi-file | memory | real-time }
        Logging mode. Default is circular.

        circular    New events overwrite the oldest ones when the log is full.

        multi-file  No limit on number of captured events, but a new log file
                    is created each time the log is full.

        memory      Like circular, but the entire log is stored in memory.
                    It is written to a file when pktmon is stopped.

        real-time   Display events and packets on screen at real time. No log
                    file is created. Press Ctrl+C to stop monitoring.

Example 1: Packet capture
    pktmon start --capture

Example 2: Packet counters only
    pktmon start --capture --counters-only

Example 3: Event logging
    pktmon start --trace -p Microsoft-Windows-TCPIP -p Microsoft-Windows-NDIS

Example 4: Packet capture with event logging
    pktmon start --capture --trace -p Microsoft-Windows-TCPIP -k 0xFF -l 4



C:\>pktmon status help
pktmon status [--buffer-info]
    Query current Packet Monitor status.

-b, --buffer-info
    Display ETW buffer information.


C:\>pktmon stop help
pktmon stop
    Stop data collection.


C:\>pktmon unload help
pktmon unload
    Stop the PktMon driver service and unload PktMon.sys. Effectively equivalent
    to 'sc.exe stop PktMon'. Measurement (if active) will immediately stop, and
    any state will be deleted (counters, filters, etc.).


C:\>pktmon counters help
pktmon counters [--type { all | flow | drop }] [--include-hidden] [--zero]
                [--drop-reason] [--live] [--refresh-rate <n>] [--json]
    Show packet counters from monitored components.

-t, --type { all | flow | drop }
    Select what type of counters to show. Default is all.

-i, --include-hidden
    Show counters from components that are hidden by default.

-z, --zero
    Show counters that are zero in both directions.

-r, --drop-reason
    Show the most recent drop reason for each drop counter.

--live
    Automatically refresh the counters. Press Ctrl+C to stop.

--refresh-rate <n>
   Number of times to refresh the counters per second, from 1 to 30.
   Default is 10.

--json
    Output in JSON format. Implies -i and -r.


C:\>pktmon reset help
pktmon reset
    Reset all packet counters to zero.


C:\>pktmon etl2txt help
pktmon etl2txt <file> [--out <name>] [--stats-only] [--timestamp-only] [--metadata]
                      [--tmfpath <path>] [--brief] [--verbose <n>] [--hex]
                      [--no-ethernet] [--vxlan <port>]
    Convert ETL log file to text format.

<file>
    ETL file to convert.

-o, --out <name>
    Name of the formatted text file.

-s, --stats-only
    Display log file statistical information.

-t, --timestamp-only
    Use timestamp only prefix for events and packets.

-m, --metadata
    Print event metadata, such as logging level and keywords.

-p, --tmfpath <path>
    Path to TMF files for decoding WPP traces.
    Multiple paths should be separated by semicolon.
    All WPP traces are skipped when this option is not specified.

Network packet formatting options

    -b, --brief
        Use abbreviated packet format.

    -v, --verbose <n>
        Verbosity level from 1 to 3.

    -x, --hex
        Include hexadecimal format.

    -e, --no-ethernet
        Don't print ethernet header.

    -l, --vxlan <port>
        Custom VXLAN port.


C:\>pktmon etl2pcap help
pktmon etl2pcap <file> [--out <name>] [--drop-only] [--component-id <id>]
    Convert pktmon log file to pcapng format.
    Dropped packets are not included by default.

<file>
    ETL file to convert.

-o, --out <name>
    Name of the formatted pcapng file.

-d, --drop-only
    Convert dropped packets only.

-c, --component-id <id>
    Filter packets by a specific component ID.


C:\>pktmon hex2pkt help
pktmon hex2pkt [--type { Ethernet | IP | HTTP }]
    Decode packet in hexadecimal format.

-t, --type { Ethernet | IP | HTTP }
    Packet type to decode. Default is Ethernet.
```

-----

---
layout: Conceptual
title: Pktmon command formatting | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/networking/technologies/pktmon/pktmon-syntax
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: networking
ms.update-cycle: 1095-days
description: Provides an overview of Pktmon command formatting with a quick start guide and provides guidance on usage.
ms.topic: how-to
author: robinharwood
ms.author: roharwoo
ms.date: 2021-10-27T00:00:00.0000000Z
locale: en-us
document_id: 0fb8988c-aa09-bf6b-3eab-5e872faf2fc6
document_version_independent_id: eeb7f936-c102-3cdd-8dd8-01da871d6a6c
updated_at: 2025-05-01T18:26:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/networking/technologies/pktmon/pktmon-syntax.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/8fdee610c66db3c1f2322c374a449b078dc3e0ff/WindowsServerDocs/networking/technologies/pktmon/pktmon-syntax.md
git_commit_id: 8fdee610c66db3c1f2322c374a449b078dc3e0ff
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: ../../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 1916
asset_id: networking/technologies/pktmon/pktmon-syntax
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/networking/technologies/pktmon/pktmon-syntax.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 8f839e04-617c-a175-eb88-aff0b2946d80
---

# Pktmon command formatting | Microsoft Learn

Packet Monitor (Pktmon) is an in-box, cross-component network diagnostics tool for Windows. It can be used for packet capture, packet drop detection, packet filtering and counting. The tool is especially helpful in virtualization scenarios, like container networking and SDN, because it provides visibility within the networking stack. Packet Monitor is available in-box via pktmon.exe command on Windows 10 and Windows Server 2019 (Version 1809 and later). You can use this topic to learn how to understand pktmon syntax, command formatting, and output. For a complete list of commands, see [pktmon syntax](../../../administration/windows-commands/pktmon).

## Quick start

Use the following steps to get started in generic scenarios:

1. Identify the type of packets needed for the capture, such as specific IP addresses, ports, or protocols associated with the packet.
2. Check the syntax to apply capture filters, and apply the filters for the packets identified in the previous step.

    ```PowerShell
    C:\Test> pktmon filter add help
    C:\Test> pktmon filter add <filters>
    ```
3. Start the capture and enable packet logging.

    ```PowerShell
    C:\Test> pktmon start -c
    ```
4. Reproduce the issue being diagnosed. Query counters to confirm the presence of expected traffic, and to get a high-level view of how the traffic flowed in the machine.

    ```PowerShell
    C:\Test> pktmon counters
    ```
5. Stop the capture and retrieve the logs in txt format for analysis.

    ```PowerShell
    C:\Test> pktmon stop
    C:\Test> pktmon etl2txt <etl file>
    ```

See Analyze Packet Monitor output for instructions on analyzing txt output.

## Capture filters

It's highly recommended to apply filters before starting any packet capture, because troubleshooting connectivity to a particular destination is easier when you focus on a single stream of packets. Capturing *all* the networking traffic can make the output too noisy to analyze. For a packet to be reported, it must match all conditions specified in at least one filter. Up to 32 filters are supported at once.

For example, the following set of filters will capture any ICMP traffic from or to the IP address 10.0.0.10 as well as any traffic on port 53.

```PowerShell
C:\Test> pktmon filter add -i 10.0.0.10 -t icmp
C:\Test> pktmon filter add -p 53
```

### Filtering capability

- Packet Monitor supports filtering by MAC addresses, IP addresses, ports, EtherType, transport protocol, and VLAN ID.
- Packet Monitor will not distinguish between source or destination when it comes to MAC address, IP address, or port filters.
- To further filter TCP packets, an optional list of TCP flags to match can be provided. Supported flags are FIN, SYN, RST, PSH, ACK, URG, ECE, and CWR.

    - For example, the following filter will capture all the SYN packets sent or received by the IP address 10.0.0.10:

```PowerShell
C:\Test> pktmon filter add -i 10.0.0.10 -t tcp syn
```

- Packet Monitor can apply a filter to encapsulated inner packets, in addition to the outer packet if the **[-e]** flag was added to any filter. Supported encapsulation methods are VXLAN, GRE, NVGRE, and IP-in-IP. Custom VXLAN port is optional, and defaults to 4789.

For more information, see [pktmon filter syntax](../../../administration/windows-commands/pktmon-filter).

## Packets and general events capture

Packet Monitor can capture packets through the **[-c]** parameter with the start command. This will enable packet capture and logging as well as packet counters. To enable packet counters only without logging the packet, add the **[-o]** parameter to the start command. For more information about packet counters, see the Packet counters section below.

You can select components to monitor through the **[--comp]** parameter. It can be NICs only or a list of component IDs, and it defaults to all components. You can also filter by packet propagation status (dropped or flowing packets) by using the **[--type]** parameter.

Along with capturing packets, Packet Monitor allows the capture of general events such as ETW and WPP events by declaring the **[-t]** parameter and specifying the providers through the **[-p]** parameter. Use "pktmon stop" to stop all data collection.

For example, the following command will capture packets of only the network adapters:

```PowerShell
C:\Test> pktmon start -c --comp nics
```

The following command will capture only the dropped packets that pass through components 4 and 5, and log them:

```PowerShell
C:\Test> pktmon start -c --comp 4,5 --type drop
```

This command will capture packets and log events from the provider "Microsoft-Windows-TCPIP":

```PowerShell
C:\Test> pktmon start --capture --trace -p Microsoft-Windows-TCPIP
```

### Packet logging capability

- Packet Monitor supports multiple logging modes:

    - Circular: New packets overwrite the oldest ones when the maximum file size is reached. This is the default logging mode.
    - Multi-file: A new log file is created when the maximum file size is reached. Log files are sequentially numbered: PktMon1.etl, PktMon2.etl, etc. Apply this logging mode to keep all the log, but be wary of storage utilization. Note: use the file creation timestamp of each log file as an indication to a specific time frame in the capture.
    - Real-time: Packets are displayed on screen at real time. No log file is created. Use Ctrl+C to stop monitoring.
    - Memory: Events are written to a circular memory buffer. Buffer size is specified through the **[-s]** parameter. Buffer contents are written to a log file after stopping the capture. Use this logging mode for very noisy scenarios to capture a huge amount of traffic in very short amount of time in the memory buffer. Using any other logging modes, some traffic might get lost.
- Specify how much of the packet to log through the **[-p]** parameter. Log the whole packet of every packet no matter its size by setting that parameter to 0. The default is 128 bytes which should include the headers of most packets.
- Specify the size of the log file through the **[-s]** parameter. This will be the maximum size of the file in a circular logging mode before Packet Monitor starts overwriting the older packets with the newer ones. This will also be the maximum size of each file in the multi-file logging mode before Packet Monitor creates a new file to log the next packets. You can also use this parameter to set the buffer size for the memory logging mode.

For more information, see [pktmon start syntax](../../../administration/windows-commands/pktmon-start).

## Packet analysis and formatting

Packet Monitor generates log files in ETL format. There are multiple ways to format the ETL file for analysis:

- Convert the log to text format (the default option), and analyze it with text editor tool like TextAnalysisTool.NET. Packet data will be displayed in TCPDump format. Follow the guide below to learn how to analyze the output in the text file.
- Convert the log to pcapng format to analyze it using [Wireshark](pktmon-pcapng-support)\*
- Open the ETL file with [Network Monitor](pktmon-netmon-support)\*

Note

\*Use the hyperlinks above to learn how to parse and analyze Packet Monitor logs in **Wireshark** and **Network Monitor**.

For more information, see [pktmon format syntax](../../../administration/windows-commands/pktmon-format).

### Analyze Packet Monitor output

Packet Monitor captures a snapshot of the packet by each component of the networking stack. Accordingly, there will be multiple snapshots of each packet (represented in the image below by the lines the blue box). Each of these packet snapshots is represented by a couple of lines (red and green boxes). There is at least one line that includes some data about the packet instance starting with the timestamp. Right after, there is at least one line (bolded in the image below) to show the parsed raw packet in text format (without a timestamp); it could be multiple lines if the packet is encapsulated, like the packet in the green box.

![Example of Packet Monitor's txt log output](media/pktmon-log-example.png)

For correlating all snapshots of the same packets, monitor the PktGroupId and PktNumber values (highlighted in yellow); all snapshots of the same packet should have these 2 values in common. The Appearance value (highlighted in blue) acts as a counter for each subsequent snapshot of the same packet. For example, the first snapshot of the packet (where the packet first appeared in the networking stack) has the value 1 for appearance, the next snapshot has the value 2, and so on.

Each packet snapshot has a component ID (underlined in the image above) denoting the component associated with the snapshot. To resolve the component name, and parameters, search for this component ID in the components list at the bottom of the log file. A portion of the components table is shown in the image below highlighting "Component 1" in yellow (this was the component where the last snapshot above was captured). Components with 2 edges will report 2 snapshots at each edge (like the snapshots with the Appearance 3 and Appearance 4 for example in the image above).

At the bottom of each log file, the filters list is presented as shown in the image below (highlighted in blue). Each filter displays the parameter(s) specified (Protocol ICMP in the example below), and zeros for the rest of the parameters.

![Example of Packet Monitor's txt log output components](media/pktmon-log-example-components.png)

For dropped packets, the word "drop" appears before any of the lines representing the snapshot where the packet got dropped. Each dropped packet also provides a dropReason value. This dropReason parameter provides a short description of the packet drop reason; for example, MTU Mismatch, Filtered VLAN, etc.

![Example of a dropped packet log](media/dropped-packet-log-example.png)

## Packet counters

Packet Monitor counters provide a high level view of the networking traffic throughout the networking stack without the need to analyze a log, which can be an expensive process. Examine traffic patterns by querying packet counters with **pktmon counters** after starting the Packet Monitor capture. Reset counters to zero using **pktmon reset** or stop monitoring all together using **pktmon stop**.

- Counters are arranged by binding stacks with network adapters on the top and protocols on the bottom.
- Tx/Rx: Counters are separated into two columns for Send (Tx) and Receive (Rx) directions.
- Edges: Components report packet propagation when a packet is crossing component boundary (edge). Each component may have one or more edges. Miniport drivers typically have single upper edge, protocols have single lower edge, and filter drivers have upper and lower edges.
- Drops: packet drop counters are being reported in the same table.

In the following example, a new capture was started, then **pktmon counters** command was used to query the counters before the capture was stopped. The counters show a single packet making it out of the networking stack, starting from the protocol layer all the way to the physical network adapter, and its response coming back in the other direction. If the ping or the response was missing, it's easy to detect this through the counters.

![Example of a packet counter with perfect flow](media/pktmon-counters-with-perfect-flow.png)

In the next example, drops are reported under the "Counter" column. Retrieve the Last Drop Reason for each component by requesting counters data in JSON format using **pktmon counters --json** or analyze the output log to get more detailed information.

![Example of a packet counter with a dropped packet](media/pktmon-counters-drop-example.png)

As shown through these examples, the counters could provide a lot of information through a diagram that can be analyzed by just a quick look.

For more information, see [pktmon counters syntax](../../../administration/windows-commands/pktmon-counters).

## Networking stack layout

Examine the networking stack layout through the command **pktmon list**.

![Example of the networking stack layout](media/pktmon-networking-stack-example.png)

The command shows networking components (drivers) arranged by adapters bindings.

A typical binding consists of:

- A single network interface card (NIC)
- A few (possibly zero) filter drivers
- One or more protocol drivers (TCP/IP or others)

Each component is uniquely identified by a Packet Monitor component ID, which are used for targeting individual components for monitoring.

Note

IDs are not persistent and may change across reboots and as Packet Monitor's driver restarts.

Some IDs that appear in Packet Monitor's output may not appear in the component list. This is due to aggregation of some components into a single ID to make selecting and displaying them easier. To find the original IDs for these components, use **pktmon list --json** and look for the SecondaryId property in the output.

For more information, see [pktmon list syntax](../../../administration/windows-commands/pktmon-list).

-----

