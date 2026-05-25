# Windows Remote Management

`C:\Windows\System32>winrm /?`
```
Windows Remote Management Command Line Tool

Windows Remote Management (WinRM) is the Microsoft implementation of
the WS-Management protocol which provides a secure way to communicate
with local and remote computers using web services.

Usage:
  winrm OPERATION RESOURCE_URI [-SWITCH:VALUE [-SWITCH:VALUE] ...]
        [@{KEY=VALUE[;KEY=VALUE]...}]

For help on a specific operation:
  winrm g[et] -?        Retrieving management information.
  winrm s[et] -?        Modifying management information.
  winrm c[reate] -?     Creating new instances of management resources.
  winrm d[elete] -?     Remove an instance of a management resource.
  winrm e[numerate] -?  List all instances of a management resource.
  winrm i[nvoke] -?     Executes a method on a management resource.
  winrm id[entify] -?   Determines if a WS-Management implementation is
                        running on the remote machine.
  winrm quickconfig -?  Configures this machine to accept WS-Management
                        requests from other machines.
  winrm configSDDL -?   Modify an existing security descriptor for a URI.
  winrm helpmsg -?      Displays error message for the error code.

For help on related topics:
  winrm help uris       How to construct resource URIs.
  winrm help aliases    Abbreviations for URIs.
  winrm help config     Configuring WinRM client and service settings.
  winrm help certmapping Configuring client certificate access.
  winrm help remoting   How to access remote machines.
  winrm help auth       Providing credentials for remote access.
  winrm help input      Providing input to create, set, and invoke.
  winrm help switches   Other switches such as formatting, options, etc.
  winrm help proxy      Providing proxy information.
```

