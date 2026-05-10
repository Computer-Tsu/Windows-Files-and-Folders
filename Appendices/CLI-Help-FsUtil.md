# fsutil

Performs tasks related to FAT and NTFS file systems, such as managing reparse points, handling sparse files, or dismounting a volume. When used without parameters, `fsutil` displays a list of supported subcommands.

> 
> You must log on as an administrator or a member of the Administrators group to use `fsutil`. Only advanced users with a thorough understanding of Windows operating systems should use this powerful command.

## Parameters

| Subcommand | Description |
| --- | --- |
| [fsutil 8dot3name](fsutil-8dot3name) | Queries or changes the settings for short name behavior on the system, for example, generates 8.3 character-length file names. Removes short names for all files within a directory. Scans a directory and identifies registry keys that might be impacted if short names were stripped from the files in the directory. |
| [fsutil clfs](fsutil-clfs) | Creates or corrects authentication codes for Common Log File System (CLFS) logfiles. |
| [fsutil devdrv](fsutil-devdrv) | Manages dev drive, which is a volume tuned for performance of developer scenarios. Dev drive also lets an administrator of the device control the file system minifilters that are attached to the volume. |
| [fsutil dirty](fsutil-dirty) | Queries whether the volume's dirty bit is set or sets a volume's dirty bit. When a volume's dirty bit is set, **autochk** automatically checks the volume for errors the next time the computer is restarted. |
| [fsutil file](fsutil-file) | Finds a file by user name (if Disk Quotas are enabled), queries allocated ranges for a file, sets a file's short name, sets a file's valid data length, sets zero data for a file, creates a new file of a specified size, finds a file ID if given the name, or finds a file link name for a specified file ID. |
| [fsutil fsinfo](fsutil-fsinfo) | Lists all drives and queries the drive type, volume information, NTFS-specific volume information, or file system statistics. |
| [fsutil hardlink](fsutil-hardlink) | Lists hard links for a file, or creates a hard link (a directory entry for a file). Every file can be considered to have at least one hard link. On NTFS volumes, each file can have multiple hard links, so a single file can appear in many directories (or even in the same directory, with different names). Because all of the links reference the same file, programs can open any of the links and modify the file. A file is deleted from the file system only after all links to it are deleted. After you create a hard link, programs can use it like any other file name. |
| [fsutil objectid](fsutil-objectid) | Manages object identifiers, which are used by the Windows operating system to track objects such as files and directories. |
| [fsutil quota](fsutil-quota) | Manages disk quotas on NTFS volumes to provide more precise control of network-based storage. Disk quotas are implemented on a per-volume basis and enable both hard- and soft-storage limits to be implemented on a per-user basis. |
| [fsutil repair](fsutil-repair) | Queries or sets the self-healing state of the volume. Self-healing NTFS attempts to correct corruptions of the NTFS file system online without requiring `chkdsk.exe` to be run. Includes initiating on-disk verification and waiting for repair completion. |
| [fsutil reparsepoint](fsutil-reparsepoint) | Queries or deletes reparse points (NTFS file system objects that have a definable attribute containing user-controlled data). Reparse points are used to extend functionality in the input/output (I/O) subsystem. They're used for directory junction points and volume mount points. They're also used by file system filter drivers to mark certain files as special to that driver. |
| [fsutil resource](fsutil-resource) | Creates a Secondary Transactional Resource Manager, starts or stops a Transactional Resource Manager, displays information about a Transactional Resource Manager, or modifies its behavior. |
| [fsutil sparse](fsutil-sparse) | Manages sparse files. A sparse file is a file with one or more regions of unallocated data in it. A program sees these unallocated regions as containing bytes with the value zero, but no disk space is used to represent these zeros. All meaningful or nonzero data is allocated, whereas all non-meaningful data (large strings of data composed of zeros) isn't allocated. When a sparse file is read, allocated data is returned as stored, and unallocated data is returned as zeros (by default in accordance with the C2 security requirement specification). Sparse file support allows data to be deallocated from anywhere in the file. |
| [fsutil tiering](fsutil-tiering) | Enables management of storage tier functions, such as setting and disabling flags and listing of tiers. |
| [fsutil transaction](fsutil-transaction) | Commits a specified transaction, rolls back a specified transaction, or displays info about the transaction. |
| [fsutil usn](fsutil-usn) | Manages the update sequence number (USN) change journal, which provides a persistent log of all changes made to files on the volume. |
| [fsutil volume](fsutil-volume) | Manages a volume. Dismounts a volume, queries to see how much free space is available on a disk, or finds a file that is using a specified cluster. |
| [fsutil wim](fsutil-wim) | Provides functions to discover and manage WIM-backed files. |

-----

*Win10 differences with online documentation*

> clfs
> behavior
> bypassio
> dax
> storagereserve
> trace

```
C:\Windows\System32>dir fsutil.exe

 Directory of C:\Windows\System32

03/11/2024  11:19 PM           267,744 fsutil.exe
               1 File(s)        267,744 bytes

C:\Windows\System32>fsutil.exe
---- Commands Supported ----

8dot3name         8dot3name management
behavior          Control file system behavior
bypassIo          BypassIo management
dax               Dax volume management
devdrv            Developer volume management
dirty             Manage volume dirty bit
file              File specific commands
fsInfo            File system information
hardlink          Hardlink management
objectID          Object ID management
quota             Quota management
repair            Self healing management
reparsePoint      Reparse point management
storageReserve    Storage Reserve management
resource          Transactional Resource Manager management
sparse            Sparse file control
tiering           Storage tiering property management
trace             File system trace management
transaction       Transaction management
usn               USN management
volume            Volume management
wim               Transparent wim hosting management

C:\Windows\System32>fsutil.exe 8dot3name
---- 8DOT3NAME Commands Supported ----

query   Query the current setting for the shortname behavior on the system
scan    Scan for impacted registry entries
set     Change the setting that controls the shortname behavior on the system
strip   Remove the shortnames for all files within a directory

C:\Windows\System32>fsutil.exe behavior
---- BEHAVIOR Commands Supported ----

query           Query the file system behavior parameters
set             Change the file system behavior parameters

C:\Windows\System32>fsutil.exe bypassIo
---- BYPASSIO Commands Supported ----

State           Returns the BypassIo state for the given file/directory

C:\Windows\System32>fsutil.exe bypassIo State
Usage: fsutil bypassIo state </v> <file path>

   /v   Verbose mode - display the name of the storage driver

   Eg: fsutil bypassIo state c:\test\testfile.txt
       fsutil bypassIo state /v d:

C:\Windows\System32>fsutil.exe dax
---- DAX Commands Supported ----

queryFileAlignment        Query file alignment on dax volume

C:\Windows\System32>fsutil.exe dax queryFileAlignment
Usage   : fsutil dax queryFileAlignment <filename> [options]
Options : q=<query flag>        - Query flag, see value options below: (Default is both)
            value: large        - Query for large page alignment.
                   huge         - Query for huge page alignment.
                   both         - Query for both large and huge page alignment.
            ** Note: huge page alignment query is limited to 64-bit architectures.
          n=<number of ranges>  - Number of output ranges. Default=all ranges.
          s=<file offset>       - Starting file offset of the range. Default=0.
          l=<length in bytes>   - Range length in bytes. Default=MAXLONGLONG-StartOffset.

   Eg : fsutil dax queryFileAlignment C:\Temp\sample.txt
      : fsutil dax queryFileAlignment C:\Temp\sample.txt q=large
      : fsutil dax queryFileAlignment C:\Temp\sample.txt q=huge n=10
      : fsutil dax queryFileAlignment C:\Temp\sample.txt q=both s=0x100 l=0x10000
      : fsutil dax queryFileAlignment C:\Temp\sample.txt q=both n=10 s=0x100 l=0x10000

C:\Windows\System32>fsutil.exe devdrv

Dev drive or a developer volume is a volume that is tuned for performance of
developer scenarios.  This also lets an administrator of the device control
the file system filters that are attached to the volume.

---- DEVDRV Commands Supported ----

query                Query developer volume information
enable               Enable developer volume support on this machine
disable              Disable developer volume support on this machine
trust                Trust the given developer volume
untrust              Untrust the given developer volume
setFiltersAllowed    Set the list of allowed filters for developer volume
clearFiltersAllowed  Clear the list of allowed filters for developer volume

Please use "fsutil devdrv <command> /?" for more information.

C:\Windows\System32>fsutil.exe dirty
---- DIRTY Commands Supported ----

query           Query the dirty bit
set             Set the dirty bit

C:\Windows\System32>fsutil.exe file
---- FILE Commands Supported ----

createNew                Creates a new file of a specified size
findBySID                Find a file by security identifier
layout                   Query all the information available about the file
optimizeMetadata         Optimize metadata for a file
queryAllocRanges         Query the allocated ranges for a file
queryCaseSensitiveInfo   Query the case sensitive information for a directory
queryEA                  Query the extended attributes (EA) information for a file
queryExtents             Query the extents for a file
queryExtentsAndRefCounts Query the extents and their corresponding refcounts for a file
queryFileID              Queries the file ID of the specified file
queryFileNameById        Displays a random link name for the file ID
queryOptimizeMetadata    Query the optimize metadata state for a file
queryValidData           Queries the valid data length for a file
setCaseSensitiveInfo     Set the case sensitive information for a directory
setShortName             Set the short name for a file
setValidData             Set the valid data length for a file
setZeroData              Set the zero data for a file
setEOF                   Sets the end of file for an existing file
setStrictlySequential    Sets ReFS SMR file as strictly sequential

C:\Windows\System32>fsutil.exe fsinfo
---- FSINFO Commands Supported ----

drives          List all drives
driveType       Query drive type for a drive
ntfsInfo        Query NTFS specific volume information
refsInfo        Query REFS specific volume information
sectorInfo      Query sector information
statistics      Query file system statistics
volumeInfo      Query volume information

C:\Windows\System32>fsutil.exe hardlink
---- HARDLINK Commands Supported ----

create          Create a hardlink
list            Enumerate hardlinks on a file

C:\Windows\System32>fsutil.exe objectID
---- OBJECTID Commands Supported ----

create          Create the object identifier
delete          Delete the object identifier
query           Query the object identifier
set             Change the object identifier

C:\Windows\System32>fsutil.exe quota
---- QUOTA Commands Supported ----

disable         Disable quota tracking and enforcement
enforce         Enable quota enforcement
modify          Set disk quota for a user
query           Query disk quotas
track           Enable quota tracking
violations      Display quota violations

C:\Windows\System32>fsutil.exe repair
---- REPAIR Commands Supported ----

enumerate      Enumerate the entries of a volume's corruption log
initiate       Initiate the repair of a file
query          Query the self healing state of the volume
set            Set the self healing state of the volume
state          Query the corruption state of the volume(s)
wait           Wait for repair(s) to complete

C:\Windows\System32>fsutil.exe reparsePoint
---- REPARSEPOINT Commands Supported ----

delete          Delete a reparse point
query           Query a reparse point

C:\Windows\System32>fsutil.exe resource
---- RESOURCE Commands Supported ----

create          Create a Secondary Transactional Resource Manager
info            Display information relating to a Transactional Resource Manager
setAutoReset    Set whether a default Transactional Resource Manager will clean its transactional metadata on next mount
setAvailable    Set a Transactional Resource Manager to prefer availability over consistency
setConsistent   Set a Transactional Resource Manager to prefer consistency over availability
setLog          Change characteristics of a running Transactional Resource Manager
start           Start a Transactional Resource Manager
stop            Stop a Transactional Resource Manager

C:\Windows\System32>fsutil.exe sparse
---- SPARSE Commands Supported ----

queryFlag       Query sparse
queryRange      Query range
setFlag         Set sparse
setRange        Set sparse range

C:\Windows\System32>fsutil.exe storageReserve
---- STORAGERESERVE Commands Supported ----

query          Query storage reserve area(s) of a volume
repair         Repair storage reserve area(s) of a volume
findByID       Find files by storage reserve ID

C:\Windows\System32>fsutil.exe tiering
---- TIERING Commands Supported ----

clearFlags      Disable tiering behavior flags of a volume
queryFlags      Display the tiering behavior flags of a volume
regionList      List the regions of a volume and their respective storage tiers
setFlags        Enable tiering behavior flags of a volume
tierList        List the storage tiers associated with a volume

C:\Windows\System32>fsutil.exe trace
---- TRACE Commands Supported ----

decode           Decode NTFS trace information
query            Query the state of NTFS trace session
start            Start a NTFS trace session
stop             Stop a NTFS trace session

C:\Windows\System32>fsutil.exe transaction
---- TRANSACTION Commands Supported ----

commit          Commit a specified transaction
fileinfo        Display transaction information for a specific file
list            Display currently running transactions
query           Display information on a specified transaction
rollback        Rollback a specified transaction

C:\Windows\System32>fsutil.exe usn
---- USN Commands Supported ----

createJournal           Create a USN journal
deleteJournal           Delete a USN journal
enableRangeTracking     Enable write range tracking for a volume
enumData                Enumerate USN data
queryJournal            Query the USN data for a volume
readJournal             Reads the USN records in the USN journal
readData                Read the USN data for a file

C:\Windows\System32>fsutil.exe volume
---- VOLUME Commands Supported ----

allocationReport      Allocated clusters report
diskFree              Query the free space of a volume
dismount              Dismount a volume
findShrinkBlocker     Find files that are blocking volume shrink
fileLayout            Query all the information available about the file(s)
flush                 Flush a volume
list                  List volumes
queryCluster          Query which file is using a particular cluster
queryLabel            Query the label for a volume
queryNumaInfo         Queries the NUMA node for the given volume
setLabel              Set the label for a volume
smrGC                 Control SMR Garbage Collection
smrInfo               Query SMR information
tpInfo                Query thin provisioning info for the given volume

C:\Windows\System32>fsutil.exe wim
---- WIM Commands Supported ----

enumFiles           Enumerate WIM backed files
enumWims            Enumerate backing WIM files
removeWim           Remove a WIM from backing files
queryFile           Query the origin of a specific file


C:\Windows\System32>
```
