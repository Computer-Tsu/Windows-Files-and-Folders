Packet Monitor




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

---
layout: Conceptual
title: Packet Monitoring Extension in Windows Admin Center | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/networking/technologies/pktmon/pktmon-wac-extension
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: networking
ms.update-cycle: 1095-days
description: Describes how to operate and consume Packet Monitor (Pktmon) through Windows Admin Center to capture and display network traffic.
ms.topic: how-to
author: robinharwood
ms.author: roharwoo
ms.date: 2021-10-27T00:00:00.0000000Z
ms.custom: sfi-image-nochange
locale: en-us
document_id: 4b54d37e-cf8d-0b69-3915-bab6d04f6fc7
document_version_independent_id: e040b12b-6955-7fa7-cffe-9b9cf6f51e6a
updated_at: 2025-08-05T17:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/networking/technologies/pktmon/pktmon-wac-extension.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/98227177156f8b2b7c56caf3a737f7fd437b0aba/WindowsServerDocs/networking/technologies/pktmon/pktmon-wac-extension.md
git_commit_id: 98227177156f8b2b7c56caf3a737f7fd437b0aba
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: ../../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 1121
asset_id: networking/technologies/pktmon/pktmon-wac-extension
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/networking/technologies/pktmon/pktmon-wac-extension.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 7cf91bd8-c989-56c5-2312-f6e28d06d408
---

# Packet Monitoring Extension in Windows Admin Center | Microsoft Learn

The Packet Monitoring extension allows you to operate and consume Packet Monitor through Windows Admin Center. The extension helps you diagnose your network by capturing and displaying network traffic through the networking stack in a log that is easy to follow and manipulate.

## What is Packet Monitor (Pktmon)?

Packet Monitor (Pktmon) is an in-box, cross-component network diagnostics tool for Windows. It can be used for packet capture, packet drop detection, packet filtering and counting. The tool is especially helpful in virtualization scenarios, like container networking and SDN, because it provides visibility within the networking stack.

## What is Windows Admin Center?

Windows Admin Center is a locally-deployed, browser-based management tool that lets you manage your Windows Servers with no Azure or cloud dependency. Windows Admin Center gives you full control over all aspects of your server infrastructure and is particularly useful for managing servers on private networks that are not connected to the Internet. Windows Admin Center is the modern evolution of "in-box" management tools, like Server Manager and MMC.

## Before you start

- To use the tool, the target server needs to be running Windows Server 2019, version 1903 or later.
- [Install Windows Admin Center](../../../manage/windows-admin-center/deploy/install).
- Add a server to Windows Admin Center:
    1. Click **+ Add** under **All Connections**.
    2. Choose to add a Server Connection.
    3. Type the name of the server and, if prompted, the credentials to use.
    4. Click **Submit** to finish.

The server will be added to your connection list on the **Overview** page.

## Getting started

To get to the tool, navigate to the server that you created in the previous step, then go to the "Packet monitoring" extension.

## Applying filters

It's highly recommended to apply filters before starting any packet capture, because troubleshooting connectivity to a particular destination is easier when focusing on a single stream of packets. On the other hand, capturing all the network traffic can make the output too noisy to analyze. Accordingly, the extension guides you to the filters pane first before starting the capture. You can skip this step by clicking **Next** to start capturing without filters. The filters pane guides you to add filters in 3 steps.

1. Filtering by networking stack components

    If you want to capture traffic that passes through only specific component(s), the first step of the filters pane shows the networking stack layout so you can select the component(s) to filter by. This also is a great place to analyze and understand the layout of your machine's networking stack.

    [![Example of filtering by networking stack components](media/filtering-by-networking-stack-components.png)](media/filtering-by-networking-stack-components.png#lightbox)
2. Filtering by packet parameters

    For the second step, the pane allows you to filter packets by their parameters. For a packet to be reported, it must match all conditions specified in at least one filter; up to 8 filters are supported at once. For each filter, you can specify packet parameters like MAC Addresses, IP Addresses, Ports, Ethertype, Transport Protocol, VLAN ID.

    - When two MACs, IPs, or ports are specified, the tool will not distinguish between source or destination; it will capture packets that have both values, whether as a destination or source. However, display filters can make that distinction; see the Display filters section below.
    - To further filter TCP packets, an optional list of TCP flags to match can be provided. Supported flags are FIN, SYN, RST, PSH, ACK, URG, ECE, and CWR.
    - If the **encapsulation** box is checked, the tool applies the filter to encapsulated inner packets, in addition to the outer packet. Supported encapsulation methods are VXLAN, GRE, NVGRE, and IP-in-IP. Custom VXLAN port is optional, and defaults to 4789.

    [![Example of filtering by packet parameters](media/filtering-by-packet-parameters.png)](media/filtering-by-packet-parameters.png#lightbox)
3. Filtering by packet flow status

    Packet Monitor will capture flowing and dropped packets by default. To capture only on dropped packets, select **Dropped Packets**.

    [![Example of filtering by packet flow status](media/filtering-by-packet-flow-status.png)](media/filtering-by-packet-flow-status.png#lightbox)

    Afterwards, a summary of all the selected filter conditions are displayed for review. You will be able to retrieve that view after starting the capture through the **Capture Conditions** button.

    [![How to capture only dropped packets](media/filters-review.png)](media/filters-review.png#lightbox)

## Capture log

The results are displayed in a table that shows the main parameters of the captured packets: Timestamp, Sources IP Address, Source Port, Destination IP Address, Destination Port, Ethertype, Protocol, TCP Flags, whether the packet was dropped, and the drop reason.

- The timestamp for each of these packets is also a hyperlink that will redirect you to a different page where you can find more information about the selected packet. See the Details Page section below.
- All dropped packets have a “True” value in the **Dropped** tab, a drop reason, and are displayed in red text to make them easier to pinpoint.
- All the tabs can be sorted ascending and descending.
- You can search for a value in any column in the log using the search bar.
- You can restart the capture with same chosen filters using the **Restart** button.

[![Example of capture log results table](media/capture-log-result.png)](media/capture-log-result.png#lightbox)

## Details page

This page presents a snapshot of the packet as it flows by each component of the local networking stack. This view shows you the packet flow path and allows you to investigate how the packets change as they get processed by each component they pass by.

- The packet snapshots are grouped by each adapter/switch stack; i.e. packet snapshots captured by an adapter/switch, its filter drivers, and its protocol drivers will be grouped under the name of the adapter/switch. This will make it easier to follow the packet’s flow from one adapter to the other.
- When a snapshot is selected, more details about this specific snapshot are shown, including the raw packet headers.
- All dropped packets have a “True” value in the **Dropped** tab, a drop reason, and are displayed in red text to make them easier to pinpoint.

[![Example of Details Page showing packet snapshots](media/details-page.png)](media/details-page.png#lightbox)

## Display filters

The display filters allow you to filter your log after capturing the packets. For each filter, you can specify packet parameters like MAC Addresses, IP Addresses, Ports, Ethertype, and Transport Protocol. Unlike capture filters:

- Display filters can distinguish between the source and the destination of IP Addresses, MAC Addresses, and Ports.
- Display filters can be deleted and edited after applying them to change the view of the log.
- Display filters are reversed in the saved logs.

[![Display filters screen](media/display-filters.png)](media/display-filters.png#lightbox)

## Save feature

The save button allows you to save the log on your local machine, your remote machine, or both. Display filters will be reversed in the saved log.

- If the log is saved on your local machine, you will be able to save it in various formats:
    - Etl format which can be analyzed using Microsoft Network Monitor. Note: Check this page for more information.
    - Text format which can be analyzed using any text editor like TextAnalysisTool.NET.
    - Pcapng format which can be analyzed using tools like Wireshark.
    - Most of the Packet Monitor metadata will be lost during this conversion. [Check this page](pktmon-pcapng-support) for more information.

[![Saving a local copy of the capture](media/packet-monitoring-save-feature.png)](media/packet-monitoring-save-feature.png#lightbox)

## Open feature

The open feature will allow you to reopen any of the five last saved logs to analyze through the tool.

[![Opening a recent log](media/open.png)](media/open.png#lightbox)

-----

