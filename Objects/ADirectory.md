# Active Directory Services

LDAP differences

ADSI

DS commands

LDIF

NetDom

NTSUtil

A user can only add 10 domain members, any user has rights to join domain.
admins can add computer name in advance, admins can associate GUID, ethernet MAC to computer name record for WDS.
Default domain join OU
Set Read-Only to stop accidental deletions.

How To Undelete<br>
change attributes - remove the deleted flag, and increase version so it won't be synced again as deleted.

Ties to DNS<br>
srv records<br>
split-brain internal vs external hosts and domain name lookup.<br>
.local, .internal, .corp, .lan *vs* ad.mydomain.com, corp.mydomain.com

Ties to Exchange

Other services (roles) like DFS

Location (Scopes)

  Ties to Replication

  Ties to (Shared) Printing

Logon folder, scripts, replication

User attributes

  logon script
  restricted time/machines
  details and attributes
  last logged on
  which are publicly visible (security)

Security (ACL)
