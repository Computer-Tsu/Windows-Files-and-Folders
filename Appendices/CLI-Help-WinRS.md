# Windows Remote Shell

`C:\Windows\System32>winrs /?`
```
USAGE
=====
(ALL UPPER-CASE = value that must be supplied by user.)

winrs [-/SWITCH[:VALUE]] COMMAND

COMMAND - Any string that can be executed as a command in the cmd.exe shell.

SWITCHES
========
(All switches accept both short form or long form. For example both -r and
-remote are valid.)

-r[emote]:ENDPOINT      - The target endpoint using a NetBIOS name or the standard connection URL: [TRANSPORT://]TARGET[:PORT]. If not specified
-r:localhost is used.

-un[encrypted]          - Specify that the messages to the remote shell will not be encrypted. This is useful for troubleshooting, or when the network traffic is already encrypted using ipsec, or when physical security is enforced. By default the messages are encrypted using Kerberos or NTLM keys. This switch is ignored when HTTPS transport is selected.

-u[sername]:USERNAME    - Specify username on command line. If not specified the tool will use Negotiate authentication or prompt for the name.
If -username is specified, -password must be as well.

-p[assword]:PASSWORD    - Specify password on command line. If -password is not specified but -username is the tool will prompt for the password. If -password is specified, -user must be specified as well.

-t[imeout]:SECONDS      - This option is deprecated.

-d[irectory]:PATH       - Specifies starting directory for remote shell. If not specified the remote shell will start in the user's home directory defined by the environment variable %USERPROFILE%.

-env[ironment]:STRING=VALUE   - Specifies a single environment variable to be set when shell starts, which allows changing default environment for shell. Multiple occurrences of this switch must be used to specify multiple environment variables.

-noe[cho]               - Specifies that echo should be disabled. This may be necessary to ensure that user's answers to remote prompts are not displayed locally. By default echo is "on".

-nop[rofile]            - Specifies that the user's profile should not be loaded. By default the server will attempt to load the user profile. If the remote user is not a local administrator on the target system then this option will be required (the default will result in error).

-a[llow]d[elegate]      - Specifies that the user's credentials can be used to access a remote share, for example, found on a different machine than the target endpoint.

-comp[ression]          - Turn on compression.  Older installations on remote machines may not support compression so it is off by default.

-[use]ssl               - Use an SSL connection when using a remote endpoint.  Specifying this instead of the transport "https:" will use the default WinRM default port.

-?                      - Help

To terminate the remote command the user can type Ctrl-C or Ctrl-Break, which will be sent to the remote shell. The second Ctrl-C will force termination of winrs.exe.

To manage active remote shells or WinRS configuration, use the WinRM tool.  The URI alias to manage active shells is shell/cmd.  The URI alias for WinRS configuration is winrm/config/winrs.  Example usage can be found in the WinRM tool by typing "WinRM -?".

Examples:
winrs -r:https://myserver.com command
winrs -r:myserver.com -usessl command
winrs -r:myserver command
winrs -r:http://127.0.0.1 command
winrs -r:http://169.51.2.101:80 -unencrypted command
winrs -r:https://[::FFFF:129.144.52.38] command
winrs -r:http://[1080:0:0:0:8:800:200C:417A]:80 command
winrs -r:https://myserver.com -t:600 -u:administrator -p:$%fgh7 ipconfig
winrs -r:myserver -env:PATH=^%PATH^%;c:\tools -env:TEMP=d:\temp config.cmd
winrs -r:myserver netdom join myserver /domain:testdomain /userd:johns /passwordd:$%fgh789
winrs -r:myserver -ad -u:administrator -p:$%fgh7 dir \\anotherserver\share
```

