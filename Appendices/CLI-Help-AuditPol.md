

`C:\Windows\System32>auditpol.exe /?`
```
Usage: AuditPol command [<sub-command><options>]


Commands (only one command permitted per execution)
  /?               Help (context-sensitive)
  /get             Displays the current audit policy.
  /set             Sets the audit policy.
  /list            Displays selectable policy elements.
  /backup          Saves the audit policy to a file.
  /restore         Restores the audit policy from a file.
  /clear           Clears the audit policy.
  /remove          Removes the per-user audit policy for a user account.
  /resourceSACL    Configure global resource SACLs


Use AuditPol <command> /? for details on each command
```

### Get

```
C:\Windows\System32>AuditPol.exe /Get /?
Usage: AuditPol /get [/user[:<username>|<{sid}>]]
       [/category:*|<name>|<{guid}>[,:<name>|<{guid}>...]]
       [/subcategory:<name>|<{guid}>[,:<name>|<{guid}>...]]
       [/option:<option name>]
       [/sd]
       [/r]


This command displays the current audit policy.


Commands
  /?               Help (context-sensitive)
  /user            The security principal for whom the per-user audit
                   policy is queried. Either the /category or /subcategory
                   option must be specified. The user may be specified as
                   a SID or name. If no user account is specified, then
                   the system audit policy is queried.
  /category        One or more audit categories specified by GUID or name.
                   An asterisk ("*") may be used to indicate that all audit
                   categories should be queried.
  /subcategory     One or more audit subcategories specified by GUID or
                   name.
  /sd              Retrieves the security descriptor used to delegate
                   access to the audit policy.
  /option          Retrieve existing policy for CrashOnAuditFail,
                   FullPrivilegeAuditing, AuditBaseObjects or
                   AuditBaseDirectories.
  /r               Display the output in report (CSV) format.


Sample usage:
  auditpol /get /user:domain\user /Category:"Detailed Tracking","Object Access"
  auditpol /get /Subcategory:{0cce9212-69ae-11d9-bed3-505054503030} /r
  auditpol /get /option:CrashOnAuditFail
  auditpol /get /user:{S-1-5-21-397123417-1234567} /Category:"System"
  auditpol /get /sd
```

### Set

```
C:\Windows\System32>AuditPol.exe /Set /?
Usage: AuditPol /set
       [/user[:<username>|<{sid}>][/include][/exclude]]
       [/category:<name>|<{guid}>[,:<name>|<{guid}>...]]
          [/success:<enable>|<disable>][/failure:<enable>|<disable>]
       [/subcategory:<name>|<{guid}>[,:<name>|<{guid}>...]]
          [/success:<enable>|<disable>][/failure:<enable>|<disable>]
       [/option:<option name> /value:<enable>|<disable>]


This command sets the current audit policy.


Commands
  /?               Help (context-sensitive)
  /user            The security principal for whom per-user audit policy
                   specified by the category/subcategory is set. Either
                   the category or subcategory option must be specified,
                   as a SID or name.
  /include         Specified with /user; indicates that user's per-user
                   policy will cause audit to be generated even if not
                   specified by the system audit policy. This setting is
                   the default and is automatically applied if neither
                   the /include nor /exclude options are explicitly
                   specified.
  /exclude         Specified with /user; indicates that the user's per-user
                   policy will cause audit to be suppressed regardless of
                   the system audit policy. This setting is not honored for
                   users who are members of the Administrators local group.
  /category        One or more audit categories specified by GUID or name.
                   If no user is specified, the system policy is set.
  /subcategory     One or more audit subcategories specified by GUID or
                   name. If no user is specified, system policy is set.
  /success         Specifies success auditing. This setting is the default
                   and is automatically applied if neither the /success nor
                   /failure options are explicitly specified. This setting
                   must be used with a parameter indicating whether to
                   enable or disable the setting.
  /failure         Specifies failure auditing. This setting must be used with
                   a parameter indicating whether to enable or disable the
                   setting.
  /option          Set the audit policy for CrashOnAuditFail,
                   FullPrivilegeAuditing, AuditBaseObjects or
                   AuditBaseDirectories.
  /sd              Sets the security descriptor used to delegate access
                   to the audit policy. The security descriptor must be
                   specified using SDDL. The security descriptor must have a
                   DACL.


Example:
  auditpol /set /user:domain\user /Category:"System" /success:enable /include
  auditpol /set /subcategory:{0cce9212-69ae-11d9-bed3-505054503030} /failure:disable
  auditpol /set /option:CrashOnAuditFail /value:enable
  auditpol /set /sd:D:(A;;DCSWRPDTRC;;;BA)(A;;DCSWRPDTRC;;;SY)
The command was successfully executed.
```

### List

```
C:\Windows\System32>AuditPol.exe /List /?
Usage: AuditPol /list
       [/user|/category|/subcategory[:<categoryname>|<{guid}>|*]
       [/v] [/r]


This command lists audit policy categories, subcategories, or lists users for
whom per-user audit policy is defined.


Commands
  /?               Help (context-sensitive)
  /user            Retrieves all users for whom per-user audit policy
                   has been defined. If used with the /v option, the
                   sid of the user is also displayed.
  /category        Displays the names of categories understood by the
                   system. If used with the /v option, the category
                   GUID is also displayed.
  /subcategory     Displays the names of subcategories understood by the
                   system, for subcategories in a specified category.
                   The subcategory GUIDs are also displayed if the /v
                   option is used.


Example:
  auditpol /list /user
  auditpol /list /category /v
  auditpol /list /subcategory:"Detailed Tracking","Object Access"
```

### Backup

```
C:\Windows\System32>AuditPol.exe /Backup /?
Usage: AuditPol /backup /file:<filename>


This command backs up system audit policy settings and per-user audit policy
settings for all users and all auditing options into a file. The backup will
be written to a CSV-formatted text file.


Options
  /?               Help (context-sensitive).
  /file            Specifies the name of the file to which the audit policy
                   will be backed-up.


Example:
  auditpol /backup /file:c:\auditpolicy.csv
The command was successfully executed.
```

### Restore

```
C:\Windows\System32>AuditPol.exe /Restore /?
Usage: AuditPol /restore /file:<filename>


This command restores system audit policy settings, per-user audit policy
settings for all users and all auditing options from a file created with the
/backup command.


Options
  /?               Help (context-sensitive).
  /file            Specifies the file where the audit policy should be
                   read from. The file must have been created by the
                   /backup option or must be syntactically consistent
                   with that file format.


Example:
  auditpol /restore /file:c:\auditpolicy.csv
The command was successfully executed.
```

### Clear

```
C:\Windows\System32>AuditPol.exe /Clear /?
Usage: AuditPol /clear [/y]
This command deletes per-user audit policy for all users, resets system
audit policy for all subcategories and sets all the auditing options to disabled.


Options
  /?               Help (context-sensitive).
  /y               Suppresses the prompt to confirm if all the audit policy
                   should be cleared.


Example:
  auditpol /clear
  auditpol /clear /y
The command was successfully executed.
```

### Remove

```
C:\Windows\System32>AuditPol.exe /Remove /?
Usage: AuditPol /remove [/user[:<username>|<{sid}>]]
       [/allusers]


This command removes per-user audit policy for a specified account.


Options
  /?               Help (context-sensitive).
  /user            Specifies the SID or user name for the user for whom
                   per-user audit policy is to be deleted
  /allusers        Deletes per-user audit policy for all users.


Example:
  auditpol /remove /user:{S-1-5-21-397123417-1234567}
  auditpol /remove /allusers
The command was successfully executed.
```

### resourceSACL

```
C:\Windows\System32>AuditPol.exe /resourceSACL /?
Usage: AuditPol /resourceSACL
       [/set /type:<resource> [/success] [/failure] /user:<user>
         [/access:<access flags>] [/condition:<expression>]]
       [/remove /type:<resource> /user:<user> [/type:<resource>]]
       [/clear [/type:<resource>]]
       [/view [/user:<user>] [/type:<resource>]]


This command configures settings for global object access auditing. The
corresponding object access subcategory needs to be enabled for the events
to be generated by the system. Type auditpol /set /? for more information.


Commands
  /?            Displays Help for the command.
  /set          Adds a new entry to or updates an existing entry in the
                resource system access control list for the resource type
                specified.
  /remove       Removes all entries for the given user from the global
                object access auditing list specified by the resource
                type.
  /clear        Removes all entries from the global object access auditing
                list for the specified resource type.
  /view         Lists the global object access auditing entries for the
                specified resource type and user. Specifying a user is
                optional.


Arguments


/type           The resource for which object access auditing is being
                configured. The supported argument values are File and
                Key. Note that these values are case sensitive.
                File: Directories and files.
                Key:  Registry keys.
/success        Specifies success auditing.
/failure        Specifies failure auditing.
/user           Specifies a user in one of the following forms:
                - DomainName\Account (such as DOM\Administrators)
                - StandaloneServer\Group
                - Account (see LookupAccountName API)
                - {S-1-x-x-x-x}. x is expressed in decimal, and the entire
                  SID must be enclosed in curly braces.
                  For example: {S-1-5-21-5624481-130208933-164394174-1001}
                  Warning: If SID form is used, no check is done to verify
                  the existence of this account.
/access         Specifies a permission mask that can be specified in one
                of two forms:
                - A sequence of simple rights:
                  Generic access rights:
                    GA - GENERIC ALL
                    GR - GENERIC READ
                    GW - GENERIC WRITE
                    GX - GENERIC EXECUTE
                  Access rights for files:
                    FA - FILE ALL ACCESS
                    FR - FILE GENERIC READ
                    FW - FILE GENERIC WRITE
                    FX - FILE GENERIC EXECUTE
                  Access rights for registry keys:
                    KA - KEY ALL ACCESS
                    KR - KEY READ
                    KW - KEY WRITE
                    KX - KEY EXECUTE
                  For example: '/access:FRFW' will enable audit events
                  for read and write operations.
                - A hex value representing the access mask (such as
                  0x1200a9).
                  This is useful when using resource-specific bit masks
                  that are not part of the SDDL standard. If omitted,
                  Full access is used.
/condition      Appends an attribute based expression like the following:
                Document sensitivity is HBI ("High")
                "(@Resource.Sensitivity == \"High\")"



Examples:


  auditpol /resourceSACL /set /type:Key /user:MYDOMAIN\myuser /success
  auditpol /resourceSACL /set /type:File /user:MYDOMAIN\myuser /success
    /failure /access:FRFW
  auditpol /resourceSACL /set /type:File /user:everyone /success
    /failure /access:FRFW /condition:"(@Resource.Sensitivity == \"High\")"
  auditpol /resourceSACL /type:File /clear
  auditpol /resourceSACL /remove /type:File
    /user:{S-1-5-21-56248481-1302087933-1644394174-1001}
  auditpol /resourceSACL /type:File /view
  auditpol /resourceSACL /type:File /view /user:MYDOMAIN\myuser
The command was successfully executed.
```

