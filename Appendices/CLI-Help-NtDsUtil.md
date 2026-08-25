---
title: 'Ntdsutil: Active Directory | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/orphan-topics/ws.10/cc755915(v=ws.10)
TOCTitle: 'Ntdsutil: Active Directory'
ms:assetid: 91559a2b-b666-442c-bdd2-df4b7c46983c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc755915(v=WS.10)
ms:contentKeyID: 16809804
ms.date: 2009-10-08T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: a87afc2c-93f2-3e35-0b56-581fac94adef
document_version_independent_id: a87afc2c-93f2-3e35-0b56-581fac94adef
updated_at: 2022-01-21T07:12:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/migration-orphans-archive-pr?path=/previous-versions-orphan-archive/ws.10/cc755915(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/migration-orphans-archive-pr/commit/bf0a97cfeff5dda7d2c26c0d87870496d3970464?path=/previous-versions-orphan-archive/ws.10/cc755915(v=ws.10).md&_a=contents
git_commit_id: bf0a97cfeff5dda7d2c26c0d87870496d3970464
site_name: Docs
depot_name: MSDN.previous-versions-orphan-archive
asset_id: ws.10/cc755915(v=ws.10)
source_path: previous-versions-orphan-archive/ws.10/cc755915(v=ws.10).md
platformId: d09ad002-155d-a75b-f3bb-b5180bc2d2f1
---

# Ntdsutil: Active Directory | Microsoft Learn

Applies To: Windows Server 2003, Windows Server 2003 R2, Windows Server 2003 with SP1, Windows Server 2003 with SP2

## Ntdsutil

Ntdsutil.exe is a command-line tool that provides management facilities for Active Directory. Use Ntdsutil.exe to perform database maintenance of Active Directory, manage and control single master operations, and remove metadata left behind by domain controllers that were removed from the network without being properly uninstalled. This tool is intended for use by experienced administrators.

the command syntax,  sections:

- Authoritative restore
- Configurable settings
- Domain management
- Files
- LDAP policies
- Metadata cleanup
- Roles
- Security account management
- Semantic database analysis
- Set DSRM Password
- Group membership evaluation

#### Authoritative restore

Restores domain controllers to a specific point in time and marks objects in Active Directory as being authoritative with respect to their replication partners. In forests that have a functional level of Windows Server 2003 or Windows Server 2003 interim, this option also restores backlinks for links that were created after the functional level was raised. (For example, the member attributes of groups to which a restored user object belongs are updated.) On domain controllers that are running the version of Ntdsutil that is included in Windows Server 2003 Service Pack 1 (SP1), **authoritative restore** creates an LDAP Data Interchange Format (LDIF) file that can be used to restore backlinks for links that were created before the functional level was raised.

At the **authoritative restore:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**create ldif file(s) from***%s*|**restore database**|**restore database verinc***%d*|**restore object***%s*|**restore object verinc***%d*|**restore subtree***%s*|**restore subtree***%s***verinc***%d*}

##### Parameters

- **create ldif file(s) from *%s*** Available in the version of Ntdsutil that is included with Windows Server 2003 SP1. This option creates an LDIF file of link updates from the Ntdsutil-generated text file that is named in *%s*. This file can be used to update backlinks on objects in a domain other than the domain of the restored object. For example, this file can be used to restore group membership for a user where the group belongs to a different domain than the user.

- **restore database** Marks the entire Ntds.dit (both the domain and configuration directory partitions held by the domain controller) as authoritative. The schema cannot be authoritatively restored.

- **restore database verinc *%d*** Marks the entire Ntds.dit (both the domain and configuration directory partitions held by the domain controller) as authoritative and increments the version number by *%d* times the number of days since backup. Use this option only to authoritatively restore over a previous, incorrect, authoritative restore, such as an authoritative restore from a backup that contains the problem you want to restore.

- ***%d*** A numeric value that overrides the default value of 100,000. The version number of the object or database being authoritatively restored will be increased by this value times the number of days since backup.

- **restore object *%s*** Marks object *%s* as being authoritative. When you use the version of Ntdsutil that is included with Windows Server 2003 SP1, this option also generates a text file that contains the distinguished name of the restored object and an LDIF file that can be used to restore backlinks for objects that are being authoritatively restored (such as group memberships of users).

- **restore object *%s*verinc*%d*** Marks object *%s*as being authoritative and updates links as described in **restore object***%s*, and also increments the version number by *%d* times the number of days since backup. Use this option only to authoritatively restore over a previous, incorrect, authoritative restore, such as an authoritative restore from a backup that contains the problem that you want to restore.

- **restore subtree *%s*** Marks subtree *%s* (and all children of the subtree) as being authoritative. When you use the version of Ntdsutil that is included with Windows Server 2003 SP1, this option also generates a text file that contains the distinguished names of the restored objects and an LDIF file that can be used to restore backlinks for objects that are being authoritatively restored (such as group memberships of users).

- **restore subtree *%s*verinc*%d*** Marks subtree *%s* (and all children of the subtree) as being authoritative and updates links as described in **restore subtree***%s*, and also increments the version number by *%d* times the number of days since backup. Use this option only to authoritatively restore over a previous, incorrect, authoritative restore, such as an authoritative restore from a backup that contains the problem that you want to restore.

- ***%s*** An alphanumeric variable, either a distinguished name for a restored object or subtree, or a file name for a text file that is used to create an LDIF file.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- When you are restoring a domain controller by using backup and restore programs, such as Ntbackup or those from other providers, the default mode for the restore is nonauthoritative. This means that the restored server is brought up to date with its replicas through the normal replication mechanism. For example, if a domain controller is restored from a backup tape that is two weeks old, when you restart it, the normal replication mechanism brings it up to date with respect to its replication partners.
- You might need to perform an authoritative restore if an administrator inadvertently deletes an organizational unit containing a large number of users. If you restore the server from tape, the normal replication process would not restore the inadvertently deleted organizational unit. Authoritative restore allows you to mark the organizational unit as authoritative and force the replication process to restore it to all of the other domain controllers in the domain.

#### Configurable settings

Aids in modifying the TTL of dynamic data stored in Active Directory. At the **configurable setting:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**cancel changes**|**connections**|**list**|**set***%s***to***%s*|**show values**}

##### Parameters

- **cancel changes** Cancels the changes made, but not yet committed.

- **connections** Invokes the **server connections** submenu.

- **list** Lists the names of the supported configurable settings.

- **set *%s*to*%s*** Sets the configurable settings *%s1* to the value *%s2*.

- **show values** Displays values of configurable settings.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

#### Domain management

Allows administrators who are members of the Enterprise Administrators group to prepare cross-reference and server objects in the directory. At the **domain management:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**add nc replica***%s %s*|**connections**|**create nc***%s %s*|**remove nc replica***%s %s*|**list**|**list nc information***%s*|**list nc replicas***%s*|**precreate***%s %s*|**delete NC***%s*|**select operation target**|**set nc reference domain***%s %s*|**set nc reference domain***%s %s*|**set nc replicate notification delay***%s %d %d*}

##### Parameters

- **add nc replica *%s %s*** Adds the domain controller *%s2* to the replica set for the Non-Domain Naming Context *%s1*. If *%s2* is not specified, the domain controller that you are connected to is used as the default.

- **connections** Invokes the **Server connections** submenu.

- **create nc *%s %s*** Creates the Non-Domain Naming Context *%s1*, on the DC *%s2*. If *%s2* is not specified, then the currently connected domain controller is used. To not specify an argument enter (NULL).

- **remove nc replica *%s %s*** Removes the domain controller *%s2* from the replica set for the Non-Domain Naming Context *%s1*. If *%s2* is not specified, the currently connected to domain controller is used.

- **list** Lists all the naming contexts that exist in the enterprise, the schema and configuration naming contexts, as well as all domain naming contexts.

- **list nc information *%s*** Prints out the reference domain, and replication delays for the Non-Domain Naming Context.

- **list nc replicas *%s*** Prints the list of domain controllers in the replica set for the Non-Domain Naming Context *%s*. Remember that this is the list of domain controllers to eventually hold replicas of the Non-Domain Naming Contexts, and that these replicas may not necessarily be fully replicated yet.

- **precreate *%s %s*** Creates a cross-reference object for the domain *%s1* allowing a server named *%s2* to be promoted as the domain controller for that domain. The domain name must be specified by using a fully distinguished name, and the server must be named by using the fully qualified DNS name.

- **delete nc *%s*** Removes the Non-Domain Naming Context *%s*. Before removing an Non-Domain Naming Context all the replicas must be removed and their removal must replicate back to the domain naming operations master.

- **select operation target** Invokes the **Select operation target** submenu.

- **set nc reference domain *%s %s*** Sets the reference domain of the Non-Domain Naming Context *%s1* to *%s2*. The domain *%s2* should be specified in a domain's DNS name format. Example: widgets.microsoft.com.

- **set nc replicate notification delay *%s %d %d*** Sets the Non-Domain Naming Context %s's notification delays to %d1 and %d2 for the delay between notifying the first domain controller of changes and the delay of notifying subsequent domain controllers of changes respectively.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- ***%d*** A numeric variable, such as replication delay time periods.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

#### Files

Provides commands for managing the directory service data and log files. The data file is called Ntds.dit. At the **files:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**compact to***%s*|**header**|**info**|**integrity**|**move DB to***%s*|**move logs to***%s*|**recover**|**set path backup***%s*|**set path db***%s*|**set path logs***%s*|**set path working dir***%s*}

##### Parameters

- **compact to *%s* (where *%s* identifies an *empty target directory*)** Invokes Esentutl.exe to compact the existing data file and writes the compacted file to the specified directory. The directory can be remote, that is, mapped by means of the **net use** command or similar means. After compaction is complete, archive the old data file, and move the newly compacted file back to the original location of the data file. ESENT supports online compaction, but this compaction only rearranges pages within the data file and does not release space back to the file system. (The directory service invokes online compaction regularly.)

- **header** Writes the header of the Ntds.dit data file to the screen. This command can help support personnel analyze database problems.

- **info** Analyzes and reports the free space for the disks that are installed in the system, reads the registry, and then reports the sizes of the data and log files. (The directory service maintains the registry, which identifies the location of the data files, log files, and directory service working directory.)

- **integrity** Invokes Esentutl.exe to perform an integrity check on the data file, which can detect any kind of low-level database corruption. It reads every byte of your data file; thus it can take a long time to process large databases. Note that you should always run Recover before performing an integrity check.

- **move DB to *%s* (where *%s* identifies a target directory)** Moves the Ntds.dit data file to the new directory specified by *%s* and updates the registry so that, upon system restart, the directory service uses the new location.

- **move logs to *%s* (where *%s* identifies a target directory)** Moves the directory service log files to the new directory specified by *%s* and updates the registry so that, upon system restart, the directory service uses the new location.

- **recover** Invokes Esentutl.exe to perform a soft recovery of the database. Soft recovery scans the log files and ensures all committed transactions therein are also reflected in the data file. The Windows 2000 Backup program truncates the log files appropriately.Logs are used to ensure committed transactions are not lost if your system fails or if you have unexpected power loss. In essence, transaction data is written first to a log file and then to the data file. When you restart after failure, you can rerun the log to reproduce the transactions that were committed but hadn't made it to the data file.

- **set path backup *%s* (where *%s* identifies a target directory)** Sets the disk-to-disk backup target to the directory specified by *%s*. The directory service can be configured to perform an online disk-to-disk backup at scheduled intervals.

- **set path db *%s* (where *%s* identifies a target directory)** Updates the part of the registry that identifies the location and file name of the data file. Use this command only to rebuild a domain controller that has lost its data file and that is not being restored by means of normal restoration procedures.

- **set path logs *%s* (where *%s* identifies a target directory)** Updates the part of the registry that identifies the location of the log files. Use this command only if you are rebuilding a domain controller that has lost its log files and is not being restored by means of normal restoration procedures.

- **set path working dir *%s* (where *%s* identifies a target directory)** Sets the part of the registry that identifies the directory service's working directory to the directory specified by *%s*.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

**Caution**

- Incorrectly editing the registry may severely damage your system. Before making changes to the registry, you should back up any valued data on the computer.

##### Remarks

- Active Directory is implemented on top of an indexed sequential access method (ISAM) table manager. This is the same table manager used by Microsoft Exchange Server, the file replication service, the security configuration editor, the certificate server, Windows Internet Name Service (WINS), and other Windows components. The version of the database that Windows 2000 and Windows Server 2003, Standard Edition use is called extensible storage engine (ESENT).

    ESENT is a transacted database system that uses log files to support rollback semantics to ensure that transactions are committed to the database. Ideally, data and log files should be located on separate drives to improve performance and support recovery of the data if a disk fails.
- ESENT provides its own tool for certain database file management functions called Esentutl.exe, which is also installed in the *systemroot*\System32 folder. Several of the Ntdsutil file management commands invoke Esentutl, reducing the need to learn the tool's command-line arguments. In the cases where Ntdsutil invokes Esentutl, it brings up a separate window configured with a large history so that you can scroll back to see all of the Esentutl progress indicators.

    Active Directory opens its files in exclusive mode. This means the files cannot be managed while the system is operating as a domain controller.

    **To manage directory service files**

    1. Start the computer.
    2. When the **Starting Windows** progress bar appears, press **F8**.
    3. From the **Windows 2000 Advanced Options Menu**, select **Directory Services Restore Mode**.

    **Note**

    - Starting the computer in Directory Services Restore Mode causes your domain controller to temporarily operate as a stand-alone server. This causes some services to fail, especially those that are integrated with the directory service. When operating in this mode, the security accounts manager (SAM) uses a minimal set of user and group definitions stored in the registry. If your domain controller is not physically secure, you should set the administrative password for the Directory Services Restore Mode.

#### LDAP policies

Sets the LDAP administration limits for the Default-Query Policy object. At the **LDAP policies:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**cancel changes**|**commit changes**|**connections**|**list**|**set***%s***to***%s*|**show values**}

##### Parameters

- **cancel changes** Cancels any uncommitted modifications of the LDAP administration limits to the default query policy.

- **commit changes** Commits all modifications of the LDAP administration limits to the default query policy.

- **connections** Invokes the **Server connections** submenu.

- **list** Lists all supported LDAP administration limits for the domain controller.

- **set *%s1*to*%s2*** Sets the value of the LDAP administration limit *%s1* to the value *%s2*.

- **show values** Shows the current and proposed values for the LDAP administration limits.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- The following table lists and describes the LDAP administration limits, with default values noted in parentheses.

    | Value | Description |
    | --- | --- |
    | **InitRecvTimeout** | Initial receive time-out (120 seconds) |
    | **MaxConnections** | Maximum number of open connections (5000) |
    | **MaxConnIdleTime** | Maximum amount of time a connection can be idle (900 seconds) |
    | **MaxActiveQueries** | Maximum number of queries that can be active at one time (20) |
    | **MaxNotificationPerConnection** | Maximum number of notifications that a client can request for a given connection (5) |
    | **MaxPageSize** | Maximum page size supported for LDAP responses (1000 records) |
    | **MaxQueryDuration** | Maximum length of time the domain controller can execute a query (120 seconds) |
    | **MaxTempTableSize** | Maximum size of temporary storage allocated to execute queries (10,000 records) |
    | **MaxResultSetSize** | Maximum size of the LDAP Result Set (262144 bytes) |
    | **MaxPoolThreads** | Maximum number of threads created by the domain controller for query execution (4 per processor) |
    | **MaxDatagramRecv** | Maximum number of datagrams that can be processed by the domain controller simultaneously (1024) |
- To ensure that domain controllers can support service level guarantees, you need to specify operational limits for a number of Lightweight Directory Access Protocol (LDAP) operations. These limits prevent specific operations from adversely impacting the performance of the server and also make the server resilient to denial of service attacks.

    LDAP policies are implemented by using objects of the class queryPolicy. Query Policy objects can be created in the container Query Policies, which is a child of the Directory Service container in the configuration naming context. For example: CN=Query-Policies, CN=Directory Service, CN=Windows NT, CN=Services (configuration directory partition).

    A domain controller uses the following three mechanisms to apply LDAP policies:

    - A domain controller might refer to a specific LDAP policy. The nTDSASettings object includes an optional attribute queryPolicyObject, which contains the distinguished name of a Query Policy.
    - In the absence of a specific query policy being applied to a domain controller, the domain controller applies the Query Policy that has been assigned to the domain controller's site. The ntDSSiteSettings object includes an optional attribute queryPolicyObject, which contains the distinguished name of a Query Policy.
    - In the absence of a specific domain controller or site Query Policy, a domain controller uses the default query policy named Default-Query Policy.

    A Query Policy object includes the multivalued attributes LDAPIPDenyList and LDAPAdminLimits. Ntdsutil allows the administrator to set the LDAP administration limits and IP Deny list for the Default-Query Policy object.

#### Metadata cleanup

Cleans up metadata for failed domain controllers. When a failed domain controller stores the only copy of one or more domains or application directory partitions (also called "naming contexts"), metadata cleanup also cleans up metadata for selected domains or application directory partitions. When you use the version of Ntdsutil.exe that is included with Windows Server 2003 Service Pack 1 (SP1), metadata cleanup also removes File replication service (FRS) connections and attempts to transfer or seize any operations master roles that the retired domain controller holds.

At the **metadata cleanup:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**connections**|**remove selected domain**|**remove selected naming context**|**remove selected server|remove selected server***%s*|**remove selected server***%s1***on***%s2*|**select operation target**}

##### Parameters

**Note**

- When you use the version of Ntdsutil.exe that is included with Windows Server 2003 SP1, you can remove server metadata by using the **remove selected server***%s* or **remove selected server***%s***on***%2* commands without first using the **Server connections** and **Select operation target** submenus.

- **connections** Invokes the **Server connections** submenu.

- **remove selected domain** Removes the metadata associated with the domain selected in the **Select operation target** submenu.

- **remove selected naming context** Removes the metadata associated with the Naming Context selected in the **Select operation target** submenu.

- **remove selected server** Removes the metadata associated with the domain controller selected in the **Select operation target** submenu.

- **remove selected server *%s*** In the version of Ntdsutil.exe that is included with Windows Server 2003 SP1, removes directory and FRS metadata for the disabled server *%s* from the directory on localhost, and attempts to transfer or seize any operations master roles held by server *%s* to localhost.

- **remove selected server *%s1*on*%s2*** In the version of Ntdsutil.exe that ships with Windows Server 2003 SP1, connects to server *%s2*, removes directory and FRS metadata for server *%s1* from the directory on server *%s2*, and attempts to transfer or seize any operations master roles held by server *%s1* to server *%s2*.

- **select operation target** Invokes the **Select operation target** submenu.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- The directory service maintains various metadata for each domain and server known to the forest. Normally, domains and domain controllers are created by means of promotion using the Active Directory Installation Wizard and are removed by means of demotion using the same tool. You can invoke the Active Directory Installation Wizard by typing **dcpromo** at the command prompt.

    Promotion and demotion are designed to correctly clean up the appropriate metadata. In the directory, however, you might have domain controllers that were decommissioned incorrectly. In this case, their metadata is not cleaned up. For example, a domain controller has failed, and rather than attempting to restore it, you decide to retire the server. This leaves some information about the retired domain controller in the directory. The general model of operation is to connect to a server known to have a copy of the offending metadata, select an operation target, and then delete the metadata of the selected target. The version of Ntdsutil.exe that is included with Windows Server 2003 SP1 can automatically connect to a specified server and remove metadata for a specified target in the same step.

    **Caution**

    - Do not delete the metadata of existing domains and domain controllers.

#### Roles

Transfers and seizes operations master roles. At the **roles:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**connections**|**seize domain naming master**|**seize infrastructure master**|**seize PDC**|**seize RID master**|**seize schema master**|**select operation target**|**transfer domain naming master**|**transfer infrastructure master**|**transfer PDC**|**transfer RID master**|**transfer schema master**}

##### Parameters

- **connections** Invokes the **Server connections** submenu.

- **seize domain naming master** Forces the domain controller to which you are connected to claim ownership of the domain-naming operations master role without regard to the data associated with the role. Use only for recovery purposes.

- **seize infrastructure master** Forces the domain controller to which you are connected to claim ownership of the infrastructure operations master role without regard to the data associated with the role. Use only for recovery purposes.

- **seize PDC** Forces the domain controller to which you are connected to claim ownership of the PDC operations master role without regard to the data associated with the role. Use only for recovery purposes.

- **seize RID master** Forces the domain controller to which you are connected to claim ownership of the relative ID master role without regard to the data associated with the role. Use only for recovery purposes.

- **seize schema master** Forces the domain controller to which you are connected to claim ownership of the schema operations master role without regard to the data associated with the role. Use only for recovery purposes.

- **select operation target** Invokes the **Select operation target** submenu.

- **transfer domain naming master** Instructs the domain controller to which you are connected to obtain the domain-naming role by means of controlled transfer.

- **transfer infrastructure master** Instructs the domain controller to which you are connected to obtain the infrastructure operations master role by means of controlled transfer.

- **transfer PDC** Instructs the domain controller to which you are connected to obtain the PDC operations master by means of controlled transfer.

- **transfer RID master** Instructs the domain controller to which you are connected to obtain the relative ID master role by means of controlled transfer.

- **transfer schema master** Instructs the domain controller to which you are connected to obtain the schema operations master role by means of controlled transfer.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- Although Active Directory is based on a multimaster administration model, some operations support only a single master. For multimaster operations, conflict resolution ensures that after the system finishes replicating, all replicas agree on the value for a given property on a given object. However, some data, for which adequate conflict resolution is not possible, is key to the operation of the system as a whole. This data is controlled by individual domain controllers called operations masters. These domain controllers are referred to as holding a particular operations master role.

    Following are the five operations master roles, some are enterprise-wide and some are per domain:

    - **Schema Operations Master.** There is a single schema operations master role for the entire enterprise. This role allows the operations master server to accept schema updates. There are other restrictions on schema updates.
    - **Relative ID Master.** There is one relative ID master per domain. Each domain controller in a domain has the ability to create security principals. Each security principal is assigned a relative ID. Each domain controller is allocated a small set of relative IDs out of a domain-wide relative ID pool. The relative ID master role allows the domain controller to allocate new subpools out of the domain-wide relative ID pool.
    - **Domain-Naming Master.** There is a single domain-naming master role for the entire enterprise. The domain-naming master role allows the owner to define new cross-reference objects representing domains in the Partitions container.
    - **PDC Operations Master.** There is one primary domain controller (PDC) operations master role per domain. The owner of the PDC operations master role identifies which domain controller in a domain performs Windows NT 4.0 PDC activities in support of Windows NT 4.0 backup domain controllers and clients using earlier versions of Windows.
    - **Infrastructure Master.** There is one infrastructure master role per domain. The owner of this role ensures the referential integrity of objects with attributes that contain distinguished names of other objects that might exist in other domains. Because Active Directory allows objects to be moved or renamed, the infrastructure master periodically checks for object modifications and maintains the referential integrity of these objects.
- An operations master role can only be moved by administrative involvement; it is not moved automatically. Additionally, moving a role is controlled by standard access controls. Thus a corporation should tightly control the location and movement of operations master roles. For example, an organization with a strong IT presence might place the schema role on a server in the IT group and configure its access control list (ACL) so that it cannot be moved at all.

    Operations master roles require two forms of management: controlled transfer and seizure.

    Use controlled transfer when you want to move a role from one server to another, perhaps to track a policy change with respect to role location or in anticipation of a server being shut down, moved, or decommissioned.

    Seizure is required when a server that is holding a role fails and you do not intend to restore it. Even in the case of a server recovered from a backup, the server does not assume that it owns a role (even if the backup tape says so), because the server cannot determine if the role was legitimately transferred to another server in the time period between when the backup was made and the server failed and was recovered. The restored server assumes role ownership only if a quorum of existing servers is available during recovery and they all agree that the restored server is still the owner.

    The Roles submenu in Ntdsutil is used to perform controlled transfer and recovery of operations master roles. Controlled transfer is simple and safe. Because the source and destination servers are running, the system software guarantees that the operations master role token and its associated data is transferred atomically. Operations master role seizure is equally simple but not as safe. You simply tell a particular domain controller that it is now the owner of a particular role.

    **Caution**

    - Do not make a server a role owner by means of seizure commands if the real role holder exists on the network. Doing this could create irreconcilable conflicts for key system data. If an operations master role owner is temporarily unavailable, do not make another domain controller the role owner. This could result in a situation where two computers function as the role owner, which might cause irreconcilable conflicts for key system data.

#### Security account management

Manages security identifiers (SIDs). At the **security account management:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**check duplicate SID**|**cleanup duplicate SID**|**connect to server***%s*|**log file***%s*}

##### Parameters

- **check duplicate SID** Checks the domain for any objects that have duplicate security identifiers.

- **cleanup duplicate SID** Deletes all objects that have duplicate security identifiers and logs these entries into the log file.

- **connect to server *%s*** Connects to server, NetBIOS name or DNS host name.

- **log file *%s*** Sets the log file to *%s*. If a log file is not explicitly set, the log file defaults to Dupsid.log.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- Each security account (users, groups, and computers) is identified by a unique security identifier (SID). Use a SID to uniquely identify a security account and to perform access checks against resources, such as files, file directories, printers, Exchange mailboxes, Microsoft SQL server databases, objects stored in Active Directory, or any data that is protected by the Windows Server 2003, Standard Edition security model.

    A SID is made up of header information and a set of relative identifiers that identify the domain and the security account. Within a domain, each domain controller is capable of creating accounts and issuing each account a unique security identifier. Each domain controller maintains a pool of relative IDs that is used in the creation of security identifiers. When 80 percent of the relative ID pool is consumed, the domain controller requests a new pool of relative identifiers from the relative ID operations master. This ensures that the same pool of relative IDs is never allocated to different domain controllers and prevents the allocation of duplicate security identifiers. However, because it is possible (but rare) for a duplicate relative ID pool to be allocated, you need to identify those accounts that have been issued duplicate security identifiers so that you prevent undesirable application of security.

    One cause of duplicate relative ID pools is when the administrator seizes the relative ID master role while the original relative ID master is operational but temporarily disconnected from the network. In normal practice, after one replication cycle, the relative ID master role is assumed by just one domain controller, but it is possible that before the role ownership is resolved, two different domain controllers might each request a new relative ID pool and be allocated the same relative ID pool.

#### Semantic database analysis

Analyzes data with respect to Active Directory semantics. At the **semantic database analysis:** prompt, type any of the parameters listed under **Syntax**.

##### Syntax

{**get***%d*|**go**|**verbose***%s*}

##### Parameters

- **get *%d*** Retrieves record number %d from the Ntds.dit.

- **go** Starts the semantic analysis of the Ntds.dit. A report is generated and written to a file named Dsdit.dmp.n, in the current directory, where n is an integer incremented each time that you carry out the command.

- **verbose *%s*** Toggles verbose mode on or off.

- ***%d*** A numeric variable, such as replication delay time periods.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- Unlike the file management commands described earlier, which test the integrity of the database with respect to the ESENT database semantics, the semantic analysis analyzes the data with respect to Active Directory semantics. It generates reports on the number of records present, including deleted and phantom records.

    **Note**

    - End users should not use this command except when Microsoft requests them to use it as an aid to fault diagnosis.

#### Set DSRM Password

Resets the directory services restore mode (DSRM) password on a domain controller. At the **Reset DSRM Administrator Password:** prompt, type any of the following parameters listed under **Syntax**.

##### Syntax

**Reset Password on server***%s*

##### Parameters

- **Reset Password on server *%s*** Prompts for a new DSRM password for a domain controller. Use NULL as the domain controller name to reset the DSRM password on the current server. After entering this parameter, the **Please type password for DS Restore Mode Administrator Account:** prompt appears. At this prompt, type the desired new DSRM password.

- ***%s*** An alphanumeric variable, such as a domain or domain controller name.

- **quit** Takes you back to the previous menu or exits the utility.

- **? or help** Displays help at the command prompt.

##### Remarks

- The DSRM password on a domain controller is initially set when the Active Directory Installation Wizard (Dcpromo) is run on a server to promote it to a domain controller.
- If the domain controller is in directory services restore mode, you cannot reset the DSRM password on a domain controller using ntdsutil.

#### Group membership evaluation

Windows Server 2003 and Windows 2000 Server environments that contain complex group structures can encounter problems with an access token limitation during authentication. This problem can result in the inability of a user to log on or access resources.

A version of Ntdsutil is available that contains the **group membership evaluation** option, which you can use to generate a report. By analyzing the results of the report, you can identify the source of the problem.

The version of Ntdsutil that includes the **group membership evaluation** option is available for download on the Microsoft Web site. To download the tool, and for detailed information about the access token limitation issue and how to use the **group membership evaluation** option in Ntdsutil, see [Addressing Problems Due to Access Token Limitation](https://go.microsoft.com/fwlink/?linkid=62237) on the Microsoft Web site (https://go.microsoft.com/fwlink/?LinkId=62237).

#### Remarks

- By default, Ntdsutil.exe is installed in the *systemroot*\System32 folder. For more information about Ntdsutil.exe, see [Using Ntdsutil](cc772919%28v=ws.10%29).
- If the variable has spaces in it, enclose it in parentheses, instead of quotation marks, as follows:

    **connect to server (*xxx yyy*)**

## Formatting legend

| Format | Meaning |
| --- | --- |
| *Italic* | Information that the user must supply |
| **Bold** | Elements that the user must type exactly as shown |
| Ellipsis (...) | Parameter that can be repeated several times in a command line |
| Between brackets ([]) | Optional items |
| Between braces ({}); choices separated by pipe (|). Example: {even|odd} | Set of choices from which the user must choose only one |
| `Courier font` | Code or program output |
