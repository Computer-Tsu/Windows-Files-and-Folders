# Referenced Objects that are not files or folders

environmental variables

from registry

network shares and paths

Libraries touched upon here? (More at: [http://www.grimadmin.com/article.php/creating-modifying-windows-7-libraries](http://technet.microsoft.com/en-us/magazine/jj663498.aspx))

note see apendice for shell extension clsid?


### Shares {#h.6mgfjeh2d4bo" id="h.6mgfjeh2d4bo

ADMIN$

C$

IPC$

FAX$

PRINT$

[http://support.microsoft.com/kb/314984](http://support.microsoft.com/kb/314984)

[http://www.itworld.com/security/53406/disabling-hidden-administrative-shares](http://www.itworld.com/security/53406/disabling-hidden-administrative-shares)

More shares found in Active Directory section above


### Environmental Variables {#h.27tpyo2kf7eg" id="h.27tpyo2kf7eg


### Credential (Password) Storage

#### Credential Manager Command Line Utility

`%WinDir%\System32\cmdkey.exe /list`


```
Install-Module -Name CredentialManager -Scope CurrentUser
# This shows target names and some metadata
Get-StoredCredential -Target "TargetName"
```

`Get-StoredCredential -All | Format-Table Target, UserName`

`Remove-StoredCredential -Target "TERMSRV/myserver.example.com"`


#### Windows Vault (Web/Windows Credentials)

`vaultcmd /list`

`vaultcmd /listcreds /vault:"Windows Credentials"'


#### Open Credential Manager (GUI):

`control /name Microsoft.CredentialManager`

`rundll32.exe keymgr.dll,KRShowKeyMgr`



``1. [http://technet.microsoft.com/en-us/library/cc783264%28v=ws.10%29.aspx](http://technet.microsoft.com/en-us/library/cc783264\(v=ws.10\).aspx) ↑``
2. [http://support.microsoft.com/kb/154599](http://support.microsoft.com/kb/154599) ↑
3. [http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a](http://superuser.com/questions/38476/this-file-came-from-another-computer-how-can-i-unblock-all-the-files-in-a) ↑
4. [http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/](http://www.slipstick.com/outlook/2010/multiple-accounts-and-the-default-account/) ↑
``5. See ANSI.SYS [http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm](http://academic.evergreen.edu/projects/biophysics/technotes/program/ansi\_esc.htm) ↑``
6. Variables in Preference Items ↑
