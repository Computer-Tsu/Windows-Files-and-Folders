## bitsadmin examples


---
layout: Conceptual
title: bitsadmin examples | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/bitsadmin-examples
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Examples showing how to use the bitsadmin tool to perform the most common tasks.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2018-05-31T00:00:00.0000000Z
locale: en-us
document_id: 02aa3815-68e8-f163-38ce-0f17673b08fc
document_version_independent_id: df054fce-6a8b-62df-c9cd-ca040da5c18b
updated_at: 2026-02-16T18:34:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/bitsadmin-examples.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/1dde3f071fa8b65476a0f278d15ed67c19b07896/WindowsServerDocs/administration/windows-commands/bitsadmin-examples.md
git_commit_id: 1dde3f071fa8b65476a0f278d15ed67c19b07896
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 664
asset_id: administration/windows-commands/bitsadmin-examples
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/bitsadmin-examples.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
platformId: 28edfa33-57ee-334b-eae8-74fcdc1caabf
---

# bitsadmin examples | Microsoft Learn

The following examples show how to use the `bitsadmin` tool to perform the most common tasks.

## Transfer a file

To create a job, add files, activate the job in the transfer queue, and to complete the job:

`bitsadmin /transfer myDownloadJob /download /priority normal https://downloadsrv/10mb.zip c:\\10mb.zip`

BITSAdmin continues to show progress information in the MS-DOS window until the transfer completes or an error occurs.

## Create a download job

To create a download job named *myDownloadJob*:

```
bitsadmin /create myDownloadJob
```

BITSAdmin returns a GUID that uniquely identifies the job. Use the GUID or job name in subsequent calls. The following text is sample output.

### Sample output

`created job {C775D194-090F-431F-B5FB-8334D00D1CB6}`

## Add files to the download job

To add a file to the job:

```
bitsadmin /addfile myDownloadJob https://downloadsrv/10mb.zip c:\\10mb.zip
```

Repeat this call for each file you want to add. If multiple jobs use *myDownloadJob* as their name, you must use the job's GUID to uniquely identify it for completion.

## Activate the download job

After you create a new job, BITS automatically suspends the job. To activate the job in the transfer queue:

```
bitsadmin /resume myDownloadJob
```

If multiple jobs use *myDownloadJob* as their name, you must use the job's GUID to uniquely identify it for completion.

## Determine the progress of the download job

The **/info** switch returns the state of the job and the number of files and bytes transferred. When the state is shown as `TRANSFERRED`, it means that BITS has successfully transferred all files in the job. You can also add the **/verbose** argument to get complete details of the job, and **/list** or **/monitor** to get all the jobs in the transfer queue.

To return the state of the job:

```
bitsadmin /info myDownloadJob /verbose
```

If multiple jobs use *myDownloadJob* as their name, you must use the job's GUID to uniquely identify it for completion.

## Complete the download job

To complete the job after the state changes to `TRANSFERRED`:

```
bitsadmin /complete myDownloadJob
```

You must run the `/complete` switch before the files in the job become available. If multiple jobs use *myDownloadJob* as their name, you must use the job's GUID to uniquely identify it for completion.

## Monitor jobs in the transfer queue using the /list switch

To return the state of the job and the number of files and bytes transferred for all jobs in the transfer queue:

```
bitsadmin /list
```

### Sample output

```
{6AF46E48-41D3-453F-B7AF-A694BBC823F7} job1 SUSPENDED 0 / 0 0 / 0
{482FCAF0-74BF-469B-8929-5CCD028C9499} job2 TRANSIENT_ERROR 0 / 1 0 / UNKNOWN

Listed 2 job(s).
```

## Monitor jobs in the transfer queue using the /monitor switch

To return the state of the job and the number of files and bytes transferred for all jobs in the transfer queue, refreshing the data every 5 seconds:

```
bitsadmin /monitor
```

Note

To stop the refresh, press CTRL+C.

### Sample output

```
MONITORING BACKGROUND COPY MANAGER(5 second refresh)
{6AF46E48-41D3-453F-B7AF-A694BBC823F7} job1 SUSPENDED 0 / 0 0 / 0
{482FCAF0-74BF-469B-8929-5CCD028C9499} job2 TRANSIENT_ERROR 0 / 1 0 / UNKNOWN
{0B138008-304B-4264-B021-FD04455588FF} job3 TRANSFERRED 1 / 1 100379370 / 100379370
```

## Monitor jobs in the transfer queue using the /info switch

To return the state of the job and the number of files and bytes transferred:

```
bitsadmin /info
```

### Sample output

```
GUID: {482FCAF0-74BF-469B-8929-5CCD028C9499} DISPLAY: myDownloadJob
TYPE: DOWNLOAD STATE: TRANSIENT_ERROR OWNER: domain\user
PRIORITY: NORMAL FILES: 0 / 1 BYTES: 0 / UNKNOWN
CREATION TIME: 12/17/2002 1:21:17 PM MODIFICATION TIME: 12/17/2002 1:21:30 PM
COMPLETION TIME: UNKNOWN
NOTIFY INTERFACE: UNREGISTERED NOTIFICATION FLAGS: 3
RETRY DELAY: 600 NO PROGRESS TIMEOUT: 1209600 ERROR COUNT: 0
PROXY USAGE: PRECONFIG PROXY LIST: NULL PROXY BYPASS LIST: NULL
ERROR FILE:    https://downloadsrv/10mb.zip -> c:\10mb.zip
ERROR CODE:    0x80072ee7 - The server name or address could not be resolved
ERROR CONTEXT: 0x00000005 - The error occurred while the remote file was being
processed.
DESCRIPTION:
JOB FILES:
0 / UNKNOWN WORKING https://downloadsrv/10mb.zip -> c:\10mb.zip
NOTIFICATION COMMAND LINE: none
```

## Delete jobs from the transfer queue

To remove all jobs from the transfer queue, use the /reset switch:

```
bitsadmin /reset
```

### Sample output

```
{DC61A20C-44AB-4768-B175-8000D02545B9} canceled.
{BB6E91F3-6EDA-4BB4-9E01-5C5CBB5411F8} canceled.
2 out of 2 jobs canceled.
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key)
- [bitsadmin command](bitsadmin)


https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/bitsadmin-examples
> The switch `/examples` referenced online documentation gives error on Windows 10

*BitsAdmin was marked for deprecation but so far continues to work. Microsoft says to use the PowerShell commands instead.*

-----

`BitsAdmin`
- AddFile
- AddFileSet
- Cache
  - Cache and Delete
  - Cache and DeleteUrl
  - Cache and GetExpirationTime
  - Cache and Getlimit
  - Cache and Help
  - Cache and Info
  - Cache and List
  - Cache and SetExpirationTime
  - Cache and SetLimit
  - Cache and Clear
- Cancel
- Complete
- Create
- Examples
- GetaclFlags
- GetBytesTotal
- GetBytesTransferred
- GetClientCertificate
- GetCompletionTime
- GetCreationTime
- GetCustomHeaders
- GetDescription
- GetDisplayname
- GetError
- GetErrorCount
- GetFilesTotal
- GetFilesTransferred
- GetHelperTokenFlags
- GetHelperTokensID
- GetHttpMethod
- GetMaxDownloadTime
- GetMinRetryDelay
- GetModificationTime
- GetNoProgressTimeout
- GetNotifyCmdline
- GetNotifyFlags
- GetNotifyInterface
- GetOwner
- GetPeerCachingFlags
- GetPriority
- GetProxyBypassList
- GetProxyList
- GetProxyusage
- GetReplyData
- GetReplyFilename
- GetReplyProgress
- GetSecurityFlags
- GetState
- GetTemporaryName
- GetType
- GetValidationState
- Help
- Info
- Info
- List
- ListFiles
- MakeCustomHeadersWriteOnly
- monitor
- nowrap
- PeerCaching
  - and GetConfigurationFlags
  - and Help
  - and SetConfigurationFlags
- Peers
  - Peers and clear
  - Peers and discover
  - Peers and Help
  - Peers and List
- RawReturn
- RemoveClientCertificate
- RemoveCredentials
- ReplaceRemotePrefix
- Reset
- Resume
- SetACLFlag
- SetClientCertificateByID
- SetClientCertificateByName
- Setcredentials
- SetCustomheaders
- SetDescription
- SetDisplayname
- SetHelperToken
- SetHelperTokenFlags
- SetHttpMethod
- SetMaxdownloadTime
- SetminretryDelay
- SetnoProgressTimeout
- SetNotifyCmdline
- SetNotifyFlags
- SetPeerCachingFlags
- SetPriority
- SetProxySettings
- SetReplyFilename
- SetsecurityFlags
- SetvalidationState
- suspend
- takeownership
- Transfer
- util
  - util and EnableAnalyticChannel
  - util and GetIEProxy
  - util and Help
  - util and RepairService
  - util and SetIEProxy
  - util and Version
- Wrap

-----

```
BITSADMIN version 3.0
BITS administration utility.
(C) Copyright Microsoft Corp.

USAGE: BITSADMIN [/RAWRETURN] [/WRAP | /NOWRAP] command
The following commands are available:

/HELP           Prints this help
/?              Prints this help
/UTIL /?        Prints the list of utilities commands
/PEERCACHING /?   Prints the list of commands to manage Peercaching
/CACHE /?       Prints the list of cache management commands
/PEERS /?       Prints the list of peer management commands

/LIST    [/ALLUSERS] [/VERBOSE]     List the jobs
/MONITOR [/ALLUSERS] [/REFRESH sec] Monitors the copy manager
/RESET   [/ALLUSERS]                Deletes all jobs in the manager

/TRANSFER <job name> [type] [/PRIORITY priority] [/ACLFLAGS flags] [/DYNAMIC]
          remote_url local_name
    Transfers one of more files.
    [type] may be /DOWNLOAD or /UPLOAD; default is download
    Multiple URL/file pairs may be specified.
    Unlike most commands, <job name> may only be a name and not a GUID.
    /DYNAMIC configures the job with BITS_JOB_PROPERTY_DYNAMIC_CONTENT, which relaxes the server-side requirements.

/CREATE [type] <job name>               Creates a job
    [type] may be /DOWNLOAD, /UPLOAD, or /UPLOAD-REPLY; default is download
    Unlike most commands, <job name> may only be a name and not a GUID.

/INFO <job> [/VERBOSE]                   Displays information about the job
/ADDFILE <job> <remote_url> <local_name> Adds a file to the job
/ADDFILESET <job> <textfile>             Adds multiple files to the job
   Each line of <textfile> lists a file's remote name and local name, separated
   by spaces.  A line beginning with '#' is treated as a comment.
   Once the file set is read into memory, the contents are added to the job.

/ADDFILEWITHRANGES  <job> <remote_url> <local_name range_list>
   Like /ADDFILE, but BITS will read only selected byte ranges of the URL.
   range_list is a comma-delimited series of offset and length pairs.
   For example,

       0:100,2000:100,5000:eof

   instructs BITS to read 100 bytes starting at offset zero, 100 bytes starting
   at offset 2000, and the remainder of the URL starting at offset 5000.

/REPLACEREMOTEPREFIX <job> <old_prefix> <new_prefix>
    All files whose URL begins with <old_prefix> are changed to use <new_prefix>

Note that BITS currently supports HTTP/HTTPS downloads and uploads.
It also supports UNC paths and file:// paths as URLS

/LISTFILES <job>                     Lists the files in the job
/SUSPEND <job>                       Suspends the job
/RESUME <job>                        Resumes the job
/CANCEL <job>                        Cancels the job
/COMPLETE <job>                      Completes the job

/GETTYPE <job>                       Retrieves the job type
/GETACLFLAGS <job>                   Retrieves the ACL propagation flags

/SETACLFLAGS <job> <ACL_flags>       Sets the ACL propagation flags for the job
  O - OWNER       G - GROUP
  D - DACL        S - SACL

  Examples:
      bitsadmin /setaclflags MyJob OGDS
      bitsadmin /setaclflags MyJob OGD

/GETBYTESTOTAL <job>                 Retrieves the size of the job
/GETBYTESTRANSFERRED <job>           Retrieves the number of bytes transferred
/GETFILESTOTAL <job>                 Retrieves the number of files in the job
/GETFILESTRANSFERRED <job>           Retrieves the number of files transferred
/GETCREATIONTIME <job>               Retrieves the job creation time
/GETMODIFICATIONTIME <job>           Retrieves the job modification time
/GETCOMPLETIONTIME <job>             Retrieves the job completion time
/GETSTATE <job>                      Retrieves the job state
/GETERROR <job>                      Retrieves detailed error information
/GETOWNER <job>                      Retrieves the job owner
/GETDISPLAYNAME <job>                Retrieves the job display name
/SETDISPLAYNAME <job> <display_name> Sets the job display name
/GETDESCRIPTION <job>                Retrieves the job description
/SETDESCRIPTION <job> <description>  Sets the job description
/GETPRIORITY    <job>                Retrieves the job priority
/SETPRIORITY    <job> <priority>     Sets the job priority
   Priority usage choices:
      FOREGROUND
      HIGH
      NORMAL
      LOW
/GETNOTIFYFLAGS <job>                 Retrieves the notify flags
/SETNOTIFYFLAGS <job> <notify_flags>  Sets the notify flags
    For more help on this option, please refer to the MSDN help page for SetNotifyFlags/GETNOTIFYINTERFACE <job>             Determines if notify interface is registered
/GETMINRETRYDELAY <job>               Retrieves the retry delay in seconds
/SETMINRETRYDELAY <job> <retry_delay> Sets the retry delay in seconds
/GETNOPROGRESSTIMEOUT <job>           Retrieves the no progress timeout in seconds
/SETNOPROGRESSTIMEOUT <job> <timeout> Sets the no progress timeout in seconds
/GETMAXDOWNLOADTIME <job>             Retrieves the download timeout in seconds
/SETMAXDOWNLOADTIME <job> <timeout>   Sets the download timeout in seconds
/GETERRORCOUNT <job>                  Retrieves an error count for the job

/SETPROXYSETTINGS <job> <usage>      Sets the proxy usage
   usage choices:
    PRECONFIG   - Use the owner's default Internet settings.
    AUTODETECT  - Force autodetection of proxy.
    NO_PROXY    - Do not use a proxy server.
    OVERRIDE    - Use an explicit proxy list and bypass list.
                  Must be followed by a proxy list and a proxy bypass list.
                  NULL or "" may be used for an empty proxy bypass list.
  Examples:
      bitsadmin /setproxysettings MyJob PRECONFIG
      bitsadmin /setproxysettings MyJob AUTODETECT
      bitsadmin /setproxysettings MyJob NO_PROXY
      bitsadmin /setproxysettings MyJob OVERRIDE proxy1:80 "<local>"
      bitsadmin /setproxysettings MyJob OVERRIDE proxy1,proxy2,proxy3 NULL

/GETPROXYUSAGE <job>                 Retrieves the proxy usage setting
/GETPROXYLIST <job>                  Retrieves the proxy list
/GETPROXYBYPASSLIST <job>            Retrieves the proxy bypass list

/TAKEOWNERSHIP <job>                 Take ownership of the job

/SETNOTIFYCMDLINE <job> <program_name> [program_parameters]
    Sets a program to execute for notification, and optionally parameters.
    The program name and parameters can be NULL.
    IMPORTANT: if parameters are non-NULL, then the program name should be the
               first parameter.

  Examples:
    bitsadmin /SetNotifyCmdLine MyJob c:\winnt\system32\notepad.exe  NULL
    bitsadmin /SetNotifyCmdLine MyJob c:\callback.exe "c:\callback.exe parm1 parm2"
    bitsadmin /SetNotifyCmdLine MyJob NULL NULL

/GETNOTIFYCMDLINE <job>              Returns the job's notification command line

/SETCREDENTIALS <job> <target> <scheme> <username> <password>
  Adds credentials to a job.
  <target> may be either SERVER or PROXY
  <scheme> may be BASIC, DIGEST, NTLM, NEGOTIATE, or PASSPORT.

/REMOVECREDENTIALS <job> <target> <scheme>
  Removes credentials from a job.
/GETCUSTOMHEADERS <job>                           Gets the Custom HTTP Headers
/SETCUSTOMHEADERS <job> <header1> <header2> <...> Sets the Custom HTTP Headers
/MAKECUSTOMHEADERSWRITEONLY <job>                 Make a job's Custom HTTP Headers write-only (cannot be undone).

/GETHTTPMETHOD <job>                           Gets the HTTP verb to use.
/SETHTTPMETHOD <job> <HTTPMethod>              Sets the HTTP verb to use.

/GETCLIENTCERTIFICATE <job>                       Gets the job's Client Certificate Information
/SETCLIENTCERTIFICATEBYID <job> <store_location> <store_name> <hexa-decimal_cert_id>
  Sets a client authentication certificate to a job.
  <store_location> may be
        1(CURRENT_USER), 2(LOCAL_MACHINE), 3(CURRENT_SERVICE),
        4(SERVICES), 5(USERS), 6(CURRENT_USER_GROUP_POLICY),
        7(LOCAL_MACHINE_GROUP_POLICY) or 8(LOCAL_MACHINE_ENTERPRISE).

/SETCLIENTCERTIFICATEBYNAME <job> <store_location> <store_name> <subject_name>
  Sets a client authentication certificate to a job.
  <store_location> may be
        1(CURRENT_USER), 2(LOCAL_MACHINE), 3(CURRENT_SERVICE),
        4(SERVICES), 5(USERS), 6(CURRENT_USER_GROUP_POLICY),
        7(LOCAL_MACHINE_GROUP_POLICY) or 8(LOCAL_MACHINE_ENTERPRISE).

/REMOVECLIENTCERTIFICATE <job>                Removes the Client Certificate Information from the job

/SETSECURITYFLAGS <job> <value>
   Sets the HTTP security flags for URL redirection and checks performed on the server certificate during the transfer.
   The value is an unsigned integer with the following interpretation for the bits in the binary representation.
     Enable CRL Check                                 : Set the least significant bit
     Ignore invalid common name in server certificate : Set the 2nd bit from right
     Ignore invalid date in  server certificate       : Set the 3rd bit from right
     Ignore invalid certificate authority in server
       certificate                                    : Set the 4th bit from right
     Ignore invalid usage of certificate              : Set the 5th bit from right
     Redirection policy                               : Controlled by the 9th-11th bits from right
         0,0,0  - Redirects will be automatically allowed.
         0,0,1  - Remote name in the IBackgroundCopyFile interface will be updated if a redirect occurs.
         0,1,0  - BITS will fail the job if a redirect occurs.

     Allow redirection from HTTPS to HTTP             : Set the 12th bit from right

/GETSECURITYFLAGS <job>
   Reports the HTTP security flags for URL redirection and checks performed on the server certificate during the transfer.

/SETVALIDATIONSTATE  <job>  <file-index> <true|false>
      <file-index> starts from 0
    Sets the content-validation state of the given file within the job.

/GETVALIDATIONSTATE  <job>  <file-index>
      <file-index> starts from 0
    Reports the content-validation state of the given file within the job.

/GETTEMPORARYNAME  <job>  <file-index>
      <file-index> starts from 0
    Reports the temporary filename of the given file within the job.

The following options control peercaching of a particular job:

/SETPEERCACHINGFLAGS  <job> <value>
    Sets the flags for the job's peercaching behavior.
    The value is an unsigned integer with the following interpretation for the bits in the binary representation.
        Allow the job's data to be downloaded from a peer : Set the least significant bit
        Allow the job's data to be served to peers        : Set the 2nd bit from right

/GETPEERCACHINGFLAGS  <job>
    Reports the flags for the job's peercaching behavior.

The following options are valid for UPLOAD-REPLY jobs only:

/GETREPLYFILENAME <job>        Gets the path of the file containing the server reply
/SETREPLYFILENAME <job> <path> Sets the path of the file containing the server reply
/GETREPLYPROGRESS <job>        Gets the size and progress of the server reply
/GETREPLYDATA     <job>        Dumps the server's reply data in hex format

/SETHELPERTOKEN <job>          Sets the current command prompt's primary token as a job's helper token
/GETHELPERTOKENSID <job>       Reports the user account SID of a job's helper token, if one is set

/SETHELPERTOKENFLAGS <job> <flags>
    Sets the helper token usage flags for a job. Possible values are:
        1 - The helper token is used when accessing the local filesystem.
        2 - The helper token is used when accessing the network.
        3 - The helper token is used when accessing both the local filesystem and the network.

/GETHELPERTOKENFLAGS <job>
    Reports a job's helper token usage flags.

/GETPEERSTATS <job> <file-index>
    <file-index> starts from 0
    Reports statistics about the amount of data downloaded from peers and origin servers for a specific file within a job.

The following options can be placed before the command:
/RAWRETURN                     Return data more suitable for parsing
/WRAP                          Wrap output around console (default)
/NOWRAP                        Don't wrap output around console

The /RAWRETURN option strips new line characters and formatting.
It is recognized by the /CREATE and /GET* commands.

Commands that take a <job> parameter will accept either a job name or a job ID
GUID inside braces.  BITSADMIN reports an error if a name is ambiguous.
```

