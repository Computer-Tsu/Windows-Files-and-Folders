
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

