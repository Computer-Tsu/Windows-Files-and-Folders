**SNMP**

On Windows 2000, to collect disk information in perfmon, must also install … then run command...?

`diskperf -yv`

Most services have nothing to configure beyond the Startup type and Log on account. SNMP can edit Contact, Location, Traps, Security, Services (Physical, Applications, Datalink and subnetwork, Internet, and End-to-End)

**SNMP Registry Keys**

**SNMP Agent Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

SNMP management systems can request the contact person, system location, and network services for this computer by sending an SNMP request.

**SNMP Agent controls**

**Contact**: Provides a location for you to type the name of the person who administers this computer.

**Location**: Provides a location for you to type the physical location of the computer (for example, the building and office number).

**Service**: There are five service-based options from which to choose. SNMP agents provide information about the SNMP host to the SNMP management system:

* **Physical**: Specifies whether this computer manages physical devices, such as a hard disk.
* **Applications**: Specifies whether this computer uses any applications that send data using TCP/IP.
* **Datalink and subnetwork**: Specifies whether this computer manages a bridge.
* **Internet**: Specifies whether this computer is an IP gateway (router).
* **End-to-end**: Specifies whether this computer is an IP host.

**SNMP Security Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

SNMP provides security by using community names and SNMP authentication traps. An SNMP trap is an event notification message sent by the SNMP Trap service running on an SNMP host. The SNMP trap is sent to other SNMP hosts or to an SNMP management system, which are known as trap destinations.

You can restrict SNMP communications for the SNMP agent, allowing it to communicate with only a specific list of communities.

**SNMP Security controls**

**Send authentication trap**: Specifies whether to send an SNMP trap message to all trap destinations if this SNMP host receives an SNMP request from an SNMP host or community that is not listed on the **Security** tab. Authentication is the process of verifying that a host name or address is valid. When the SNMP agent receives a request that does not contain a known community name or that is not sent from a member of the acceptable hosts list, the SNMP agent sends an authentication trap message to one or more trap destinations, indicating the failure of authentication. This check box is selected by default.

**Accepted community names**: Lists the community names whose member SNMP hosts are authenticated to send SNMP requests to this computer. A community name acts as a password that is shared by one or more SNMP hosts.

Accepted community names are used to authenticate incoming messages only. To check outgoing messages, add the SNMP host as a trap destination on the **Traps** tab.

The SNMP Trap service requires at least one community name. **Public** is the default community name that is accepted in all SNMP implementations. You can add multiple community names, and delete or change the default community name. If an SNMP request is received from a community that is not on this list, the request will generate an authentication trap.

**Caution**

If you remove all the community names including the default name **Public**, SNMP will not respond to any community names presented.

* **Add**: Adds a community name and associated permissions to the list of communities that can send SNMP requests to this SNMP host. Use the following permission levels to specify how this SNMP host processes SNMP requests from a selected community:
  * **None**: Prevents this host from processing any SNMP requests.
  * **Notify**: Allows this host to send only SNMP traps to the community.
  * **Read Only**: Prevents this host from processing SNMP SET requests. SNMP managed objects have default values specified by the agent. Some applications may request to modify these values with the SNMP SET command.
  * **Read Write**: Allows this host to process SNMP SET requests.
  * **Read Create**: Allows this host to create new entries in the SNMP tables.
* **Edit**: Provides a dialog box to edit the selected community name and its permissions.
* **Remove**: Removes the selected community name from the list.

**Accept SNMP packets from any host**: Specifies that all SNMP packets from all SNMP hosts belonging to any community listed in **Accepted community names** are processed. No SNMP packets are rejected on the basis of the host name or IP address of the source host or the list of acceptable hosts. This check box is selected by default.

**Accept SNMP packets from these hosts**: Lists the SNMP hosts and SNMP management systems that can send SNMP requests to this SNMP host. This setting provides a higher level of security than use of a community name, which can contain a large group of hosts. You can add the names of any SNMP host or SNMP management system that belong to any community listed in **Accepted community names**. Only SNMP packets received from the hosts in this list are accepted. All other SNMP messages are rejected, and then authentication traps are sent.

* **Add**: Adds a specific SNMP host name or SNMP management system to the list of acceptable sources.
* **Edit**: Provides a dialog box to edit computer name or IP address of the selected SNMP host.
* **Remove**: Removes the selected SNMP host or SNMP management system from the list.

**SNMP Traps Tab**

Simple Network Management Protocol (SNMP) is a network protocol used to manage TCP/IP networks. In Windows, the SNMP service -- also known as the SNMP agent -- is used to provide status information about an SNMP host on a TCP/IP network.

An SNMP trap is an event notification message sent by the SNMP Trap service running on an SNMP host. The SNMP trap is sent to other SNMP hosts or to an SNMP management system, which are known as trap destinations.

If SNMP traps are required, one or more community names must be specified. Trap destinations can be specified as host names or IP addresses.

**SNMP Trap controls**

**Community name**: Provides a location for you to type or select a community name that you want used by the trap destinations. A community name acts as a password that is shared by one or more SNMP hosts. The SNMP agent can only send SNMP trap messages to SNMP hosts that use a known community name. Community names listed on the **Traps** tab are used only to authenticate outgoing SNMP trap messages. To authenticate all incoming SNMP trap messages, configure this SNMP host on the **Security** tab.

**Add to list**: Adds a typed community name to the **Community name** list.

**Remove from list**: Removes the selected community name from the **Community name** list.

**Trap destinations**: Lists trap destinations, which are SNMP management systems that receive SNMP trap messages from any SNMP host in the selected community.

**Add**: Adds an SNMP management system to the list of trap destinations for the selected community.
**Edit**: Provides a dialog box to edit the host name or IP address of the selected trap destination.
**Remove**: Removes the selected SNMP management system from the list of trap destinations for the selected community.

**Additional references**

For more information about SNMP, see[ ](http://technet.microsoft.com/en-us/library/cc755189.aspx?LinkId=66006)[Simple Network Management Protocol](http://technet.microsoft.com/en-us/library/cc742081.aspx?LinkId=66006) in TCP/IP Fundamentals for Windows in the Microsoft TechNet Technical Library at http://go.microsoft.com/fwlink/?LinkId=66006.

**Note:** *These links to help documents (`.chm`) may not be compatible in current Windows and the content is surely no longer included.*
```
mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/80366ac5-42bd-42e9-8169-83696087e091.htm
mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/e2c0fd7c-286c-4b02-a33b-8ed1780a681c.htm
mk:@MSITStore:C:\Windows\help\mui\0409\snmp.chm::/html/68219299-c666-4737-ae36-3de0b3dd76cb.htm
```

**MIB (management information base)**

compile with mibcc.exe

[http://support.microsoft.com/kb/131776](http://support.microsoft.com/kb/131776)

```
C:\Windows\System32\
accserv.mib
authserv.mib
dhcp.mib
ftp.mib
hostmib.mib
[http.mib](http.mib)
inetsrv.mib
ipforwd.mib
lmmib2.mib
mcastmib.mib
mib_ii.mib
msft.mib
msipbtp.mib
msiprip2.mib
rfc2571.mib
smi.mib
wins.mib
```

| **File Name** | **Description** | **OID** |
| ------------- | --------------- | ------- |
| accserv.mib   |                 |         |
| authserv.mib  |                 |         |
| dhcp.mib      |                 |         |
| ftp.mib       |                 |         |
| hostmib.mib   |                 |         |
| http.mib      |                 |         |
| inetsrv.mib   |                 |         |
| ipforwd.mib   |                 |         |
| lmmib2.mib    |                 |         |
| mcastmib.mib  |                 |         |
| mib\_ii.mib   |                 |         |
| msft.mib      |                 |         |
| msipbtp.mib   |                 |         |
| msiprip2.mib  |                 |         |
| rfc2571.mib   |                 |         |
| smi.mib       |                 |         |
| wins.mib      |                 |         |

[http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4a168955-4982-44d5-8a18-e252d37a3557.mspx?mfr=true](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4a168955-4982-44d5-8a18-e252d37a3557.mspx?mfr=true)

**OID to detect the state of a windows service**

address of object identifier you can monitor Windows Services

No know OID for detecting hardware or hardware changes, use WMI. Script can pull list and then compare later for any changes. No known event trigger for hardware changes?


