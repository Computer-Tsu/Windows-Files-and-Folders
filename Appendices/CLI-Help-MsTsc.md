MS Terminal Services Client (RDP - Remote Desktop Client)

commandline switches

`.rdp` cfg file structure

Deprecated, use msstore Windows App

Digital Sign RDP to bypass security warnings https://lazyadmin.nl/it/how-to-sign-rdp-files/

-----

---
layout: Conceptual
title: Administrative session | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393663(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Administrative session
ms:assetid: 3b21fbf3-8e37-4ccc-99ef-be052b8016e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393663(v=WS.10)
ms:contentKeyID: 28576030
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 52bc5639-a44f-19b6-52a1-9073471d30ff
document_version_independent_id: 52bc5639-a44f-19b6-52a1-9073471d30ff
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393663(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393663(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 83
asset_id: ff393663(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393663(v=ws.10).md
platformId: 91a9407f-14e6-39ec-888c-49ea1a0b17c3
---

# Administrative session | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting configures the client computer to connect to the administrative session of the remote computer. This setting is the same as the /admin parameter used with mstsc.exe.

## Syntax

```
administrative session:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | When connecting to the remote computer, do not use the administrative session. |
| 1 | When connecting to the remote computer, use the administrative session. |

The default value is 0.

## Examples

To connect to the administrative session on the remote computer, type:

```
administrative session:i:1
```




---
layout: Conceptual
title: Alternate full address | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393657(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Alternate full address
ms:assetid: 113fa054-61d4-478a-ac80-fe3ad9a72769
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393657(v=WS.10)
ms:contentKeyID: 28576024
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: c3c114a5-419d-d2e5-5ded-78e5c2f39c41
document_version_independent_id: c3c114a5-419d-d2e5-5ded-78e5c2f39c41
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393657(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393657(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 99
asset_id: ff393657(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393657(v=ws.10).md
platformId: d5f50d46-12b8-76c6-6164-7702802a1af1
---

# Alternate full address | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies an alternate name or IP address of the remote computer that you want to connect to by using Remote Desktop Connection (RDC).

Note

With clients running RDC 7, this setting takes precedence over the full address setting. 

## Syntax

```
alternate full address:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A valid computer name, IPv4 address, or IPv6 address* | Specifies the remote computer to which you want to connect |

There is no default value.

## Examples

To specify Server1, type:

```
alternate full address:s:server1
```

To specify a computer with the IP address of 10.10.15.15, type:

```
alternate full address:s:10.10.15.15
```




---
layout: Conceptual
title: Audiocapturemode | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393705(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Audiocapturemode
ms:assetid: 87d7bcad-3dfb-4457-90fc-ccc695f75a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393705(v=WS.10)
ms:contentKeyID: 28576070
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 40dca2d5-cd76-0b99-59da-bac2501a7f41
document_version_independent_id: 40dca2d5-cd76-0b99-59da-bac2501a7f41
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393705(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393705(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 107
asset_id: ff393705(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393705(v=ws.10).md
platformId: 9b878071-8d55-c100-00cd-f278884fa4e6
---

# Audiocapturemode | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines how sounds captured on the local computer are handled when you are connected to the remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selections in the **Remote audio** area on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
audiocapturemode:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Do not capture audio from the local computer (**Do not record**). |
| 1 | Capture audio from the local computer and send to the remote computer (**Record from this computer**). |

The default value is 0.

## Examples

To record from the local computer and send it to the remote computer, type:

```
audiocapturemode:i:1
```




---
layout: Conceptual
title: Audiomode | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393707(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Audiomode
ms:assetid: 892bbd6c-a685-4541-87fa-688d8e6aba3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393707(v=WS.10)
ms:contentKeyID: 28576072
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: f647bde3-f05d-ffcd-4775-b0d23b9ec5a9
document_version_independent_id: f647bde3-f05d-ffcd-4775-b0d23b9ec5a9
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393707(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393707(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 101
asset_id: ff393707(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393707(v=ws.10).md
platformId: 92451830-fc7f-d2a0-6468-d18fd274c3e7
---

# Audiomode | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines how sounds on a remote computer are handled when you are connected to the remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the settings in the **Remote audio** area on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
audiomode:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Play sounds on the local computer (**Play on this computer**) |
| 1 | Play sounds on the remote computer (**Play on remote computer**) |
| 2 | Do not play sounds (**Do not play**) |

The default value is 0.

## Examples

To play sounds on the remote computer, type:

```
audiomode:i:1
```




---
layout: Conceptual
title: Audioqualitymode | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393679(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Audioqualitymode
ms:assetid: 7a462a74-90e5-4de6-8f5b-f141cc70ca26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393679(v=WS.10)
ms:contentKeyID: 28576044
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: e70be0bd-6f56-c538-b99e-14b822cc7c13
document_version_independent_id: e70be0bd-6f56-c538-b99e-14b822cc7c13
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393679(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393679(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 58
asset_id: ff393679(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393679(v=ws.10).md
platformId: ef76a9d5-a712-17b9-b4c2-2449cf01d36b
---

# Audioqualitymode | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines the audio playback quality on the local computer.

## Syntax

```
audioqualitymode:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Dynamically adjust audio quality based on available bandwidth. |
| 1 | Always use medium audio quality. |
| 2 | Always use uncompressed audio quality. |

The default value is 0.

## Examples

To play sounds on the remote computer, type:

```
audioqualitymode:i:1
```




---
layout: Conceptual
title: Authentication level | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393709(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Authentication level
ms:assetid: 899662de-094b-4f2e-94ac-70823c92c030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393709(v=WS.10)
ms:contentKeyID: 28576074
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 9dcda5f8-cfbc-fca3-65e1-ca3528541287
document_version_independent_id: 9dcda5f8-cfbc-fca3-65e1-ca3528541287
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393709(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393709(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 115
asset_id: ff393709(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393709(v=ws.10).md
platformId: 5e18b9b0-c48b-5f80-b777-463f9f7139de
---

# Authentication level | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines what Remote Desktop Connection (RDC) should do when server authentication fails.

This setting corresponds to the selection in the **If server authentication fails** drop-down list on the **Advanced** tab under **Options** in RDC.

## Syntax

```
authentication level:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | If server authentication fails, connect to the computer without warning (**Connect and don’t warn me**). |
| 1 | If server authentication fails, do not establish a connection (**Do not connect**). |
| 2 | If server authentication fails, show a warning and allow me to connect or refuse the connection (**Warn me**). |
| 3 | No authentication requirement is specified. |

The default value is 3.

## Examples

To require server authentication, type:

```
authentication level:i:1
```




---
layout: Conceptual
title: Autoreconnection enabled | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393670(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Autoreconnection enabled
ms:assetid: 4f6da0e9-3874-4c29-a140-2f0aceb48496
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393670(v=WS.10)
ms:contentKeyID: 28576036
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: d3fa9b1c-8a4c-306e-a817-a4716c7fc077
document_version_independent_id: d3fa9b1c-8a4c-306e-a817-a4716c7fc077
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393670(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393670(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 96
asset_id: ff393670(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393670(v=ws.10).md
platformId: 7b08c400-3e47-a366-51ab-870f09c57f87
---

# Autoreconnection enabled | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the client computer will automatically try to reconnect to the remote computer if the connection is dropped; for example, when there is an interruption of network connectivity.

This setting corresponds to the **Reconnect if the connection is dropped** check box on the **Experience** tab under **Options** in Remote Desktop Connection (RDC).

## Syntax

```
autoreconnection enabled:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Client computer does not automatically try to reconnect. |
| 1 | Client computer automatically tries to reconnect. |

The default value is 1.

## Examples

To disable automatic reconnection, type:

```
autoreconnection enabled:i:0
```




---
layout: Conceptual
title: Autoreconnect max retries | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393672(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Autoreconnect max retries
ms:assetid: 5000556a-fb26-4579-beac-b39fa2519b5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393672(v=WS.10)
ms:contentKeyID: 28576038
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: f86ce2bf-966d-1e76-17a7-9aef37f08b99
document_version_independent_id: f86ce2bf-966d-1e76-17a7-9aef37f08b99
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393672(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393672(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 95
asset_id: ff393672(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393672(v=ws.10).md
platformId: b66bf14e-c1c4-2b08-3810-7f72bbd729a2
---

# Autoreconnect max retries | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines the maximum number of times the client computer will automatically try to reconnect to the remote computer if the connection is dropped, for example, when there is an interruption of network connectivity.

## Syntax

```
autoreconnect max retries:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A number* | Specifies the maximum number of times the client computer will attempt to automatically reconnect to the remote session. |

If this setting is not specified, the default value is 20.

## Examples

To configure the maximum number of reconnection attempts to be 10, type:

```
autoreconnect max retries:i:10
```




---
layout: Conceptual
title: Bitmapcachepersistenable | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393688(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Bitmapcachepersistenable
ms:assetid: 31d3a3ac-a9cc-426b-b84f-dbb0d5b88865
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393688(v=WS.10)
ms:contentKeyID: 28576054
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 4ab2a1e5-ad7a-6154-174f-ae1ad81ccc50
document_version_independent_id: 4ab2a1e5-ad7a-6154-174f-ae1ad81ccc50
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393688(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393688(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 64
asset_id: ff393688(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393688(v=ws.10).md
platformId: 11a7eb1c-fab5-b9ad-632e-3a0308ccc6f5
---

# Bitmapcachepersistenable | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether bitmaps are cached on the local computer. Bitmap caching can improve the performance of your remote session by storing frequently used images on the local computer.

## Syntax

```
bitmapcachepersistenable:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Bitmap caching is not enabled. |
| 1 | Bitmap caching is enabled. |

The default value is 1.

## Examples

To disable bitmap caching, type:

```
bitmapcachepersistenable:i:0
```




---
layout: Conceptual
title: Compression | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393691(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Compression
ms:assetid: 45b4aed9-9bf8-4fe5-bdb2-9299721921b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393691(v=WS.10)
ms:contentKeyID: 28576057
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: fa93b0dc-a69f-d213-7ff1-5bdaead9e7cc
document_version_independent_id: fa93b0dc-a69f-d213-7ff1-5bdaead9e7cc
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393691(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393691(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 55
asset_id: ff393691(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393691(v=ws.10).md
platformId: cc013f5a-8dc5-18a9-08c0-94311467c520
---

# Compression | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether bulk compression is enabled when it is transmitted by RDP to the local computer.

## Syntax

```
compression:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | RDP bulk compression is not enabled. |
| 1 | RDP bulk compression is enabled. |

The default value is 1.

## Examples

To disable RDP bulk compression, type:

```
compression:i:0
```




---
layout: Conceptual
title: Connection type | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/gg607280(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Connection type
ms:assetid: dc28bc6d-bc12-4c72-8f9a-939134a1d3a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607280(v=WS.10)
ms:contentKeyID: 34135424
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 64429724-47cc-13e9-64d6-aea086dee18d
document_version_independent_id: 64429724-47cc-13e9-64d6-aea086dee18d
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/gg607280(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/9e9f7d6a8372513ab26061a12c9741131d3feb56?path=/windows-server-2008-R2-and-2008/gg607280(v=ws.10).md&_a=contents
git_commit_id: 9e9f7d6a8372513ab26061a12c9741131d3feb56
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 305
asset_id: gg607280(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/gg607280(v=ws.10).md
platformId: 1dac9b27-dd47-14dc-9687-e31704f7f720
---

# Connection type | Microsoft Learn

Applies To: Windows Server 2008 R2, Windows Server 2008 R2 with SP1

This setting configures the client computer’s connection speed.

This setting corresponds to the selections for **Choose your connection speed to optimize performance** on the **Experience** tab under **Options** in Remote Desktop Connection.

## Syntax

```
connection type:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 1 | When connecting to the remote computer, set the connection speed to **Modem (56 Kbps)**.<br><br>With this setting, the following are allowed:<br><br>- Persistent bitmap caching |
| 2 | When connecting to the remote computer, set the connection speed to **Low-speed broadband (256 Kbps – 2 Mbps)**.<br><br>With this setting, the following are allowed:<br><br>- Visual styles<br>- Persistent bitmap caching |
| 3 | When connecting to the remote computer, set the connection speed to **Satellite (2Mbps – 16 Mbps with high latency)**.<br><br>With this setting, the following are allowed:<br><br>- Desktop composition<br>- Visual styles<br>- Persistent bitmap caching |
| 4 | When connecting to the remote computer, set the connection speed to **High-speed broadband (2Mbps – 10 Mbps)**.<br><br>With this setting, the following are allowed:<br><br>- Desktop composition<br>- Visual styles<br>- Persistent bitmap caching |
| 5 | When connecting to the remote computer, set the connection speed to **WAN (10 Mbps or higher with high latency)**.<br><br>With this setting, the following are allowed:<br><br>- Desktop background<br>- Font smoothing<br>- Desktop composition<br>- Show window contents while dragging<br>- Menu and window animation<br>- Visual styles<br>- Persistent bitmap caching |
| 6 | When connecting to the remote computer, set the connection speed to **LAN (10 Mbps or higher)**.<br><br>With this setting, the following are allowed:<br><br>- Desktop background<br>- Font smoothing<br>- Desktop composition<br>- Show window contents while dragging<br>- Menu and window animation<br>- Visual styles<br>- Persistent bitmap caching<br><br><br><br>| ![](images/cc770628.important(ws.10).gif)Important |<br>| --- |<br>| This setting is required to use Microsoft RemoteFX. | |
| --- | --- |

The default value is 2.

## Examples

To configure the client computer’s connection speed to **Modem (56 Kbps)**, type:

```
connection type:i:1
```

To configure the client computer’s connection speed to use RemoteFX, type:

```
connection type:i:6
```




---
layout: Conceptual
title: Desktopheight | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393702(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Desktopheight
ms:assetid: 7c0a76a5-cb5d-4f55-aa43-209bb9fe9e99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393702(v=WS.10)
ms:contentKeyID: 28576068
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 7035548f-e993-02a4-af74-496c695e5c7d
document_version_independent_id: 7035548f-e993-02a4-af74-496c695e5c7d
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393702(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393702(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 88
asset_id: ff393702(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393702(v=ws.10).md
platformId: 1b5af659-5afb-de74-7ec3-f01abc9ed56c
---

# Desktopheight | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines the resolution height (in pixels) on the remote computer when you connect by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Display configuration** slider on the **Display** tab under **Options** in RDC.

## Syntax

```
desktopheight:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *Numerical value from 200 to 2048* | Resolution height (in pixels) of remote session desktop |

The default value is set to the resolution on the local computer.

## Examples

To configure the resolution height to be 768, type:

```
desktopheight:i:768
```




---
layout: Conceptual
title: Desktopwidth | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393697(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Desktopwidth
ms:assetid: 6d072da6-2352-4a72-821f-cdca4c2298b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393697(v=WS.10)
ms:contentKeyID: 28576063
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: de7eeb29-7235-0604-6de8-39062a368543
document_version_independent_id: de7eeb29-7235-0604-6de8-39062a368543
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393697(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393697(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 88
asset_id: ff393697(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393697(v=ws.10).md
platformId: 618f4954-2671-7e23-986d-8d67daff310d
---

# Desktopwidth | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines the resolution width (in pixels) on the remote computer when you connect by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Display configuration** slider on the **Display** tab under **Options** in RDC.

## Syntax

```
desktopwidth:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *Numerical value from 200 to 4096* | Resolution width (in pixels) of remote session desktop |

The default value is set to the resolution on the local computer.

## Examples

To configure the resolution width to be 1024, type:

```
desktopwidth:i:1024
```




---
layout: Conceptual
title: Devicestoredirect | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393728(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Devicestoredirect
ms:assetid: c8f1dbf4-029d-49de-867f-ce2edcfcc484
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393728(v=WS.10)
ms:contentKeyID: 28576084
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: d8298c86-8cba-41e9-fe1b-7bbe3d1a3f1f
document_version_independent_id: d8298c86-8cba-41e9-fe1b-7bbe3d1a3f1f
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393728(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393728(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 172
asset_id: ff393728(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393728(v=ws.10).md
platformId: da6698d3-12dd-dec6-ba42-4078525d98cc
---

# Devicestoredirect | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines which supported Plug and Play devices on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selections for **Other supported Plug and Play (PnP) devices** under **More** on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
devicestoredirect:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *No value specified* | Do not redirect any supported Plug and Play devices. |
| \* | Redirect all supported Plug and Play devices. |
| DynamicDevices | Redirect any supported Plug and Play devices that are connected later. |
| *The hardware ID for the supported Plug and Play device* | Redirect the specified supported Plug and Play device. |

No value is specified for the default value.

## Examples

To redirect all supported Plug and Play devices, type:

```
devicestoredirect:s:*
```

To redirect any supported Plug and Play devices that are connected later, type:

```
devicestoredirect:s:DynamicDevices
```

To redirect a particular camera and any supported Plug and Play devices that are connected later, type:

```
devicestoredirect:s:USB\VID_04A9&PID_30C1\6&4BD985D&0&2;,DynamicDevices
```




---
layout: Conceptual
title: Disable ctrl+alt+del | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393711(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Disable ctrl+alt+del
ms:assetid: ab44b256-2ab3-4ac0-bd6d-17a6215b4e0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393711(v=WS.10)
ms:contentKeyID: 28576076
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: b13cf46d-8dce-d81e-c71a-4daf70d5a62a
document_version_independent_id: b13cf46d-8dce-d81e-c71a-4daf70d5a62a
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393711(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393711(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 78
asset_id: ff393711(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393711(v=ws.10).md
platformId: 04985387-6889-8beb-5f18-0dc814135fe2
---

# Disable ctrl+alt+del | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the CTRL+ALT+DELETE security attention sequence is required to enter credentials after you are connected to the remote computer.

## Syntax

```
disable ctrl+alt+del:i:<value>
```

## Syntax

| Value | Explanation |
| --- | --- |
| 0 | Require the CTRL+ALT+DELETE security attention sequence on the remote computer. |
| 1 | Do not require the CTRL+ALT+DELETE security attention sequence on the remote computer. |

The default value is 0.

## Examples

To disable the requirement to enter the CTRL+ALT+DELETE security attention sequence, type:

```
disable ctrl+alt+del:i:1
```




---
layout: Conceptual
title: Disableprinterredirection | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393725(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Disableprinterredirection
ms:assetid: c10722e4-5833-4fbd-b739-dbe1bd3dd66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393725(v=WS.10)
ms:contentKeyID: 28576082
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 8be93ba7-da5a-7754-dff1-d732d60eb992
document_version_independent_id: 8be93ba7-da5a-7754-dff1-d732d60eb992
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393725(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393725(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 56
asset_id: ff393725(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393725(v=ws.10).md
platformId: c1beef63-9644-13c4-c8b7-7edcd8e4fe80
---

# Disableprinterredirection | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether Easy Print printer redirection is enabled when connecting to the remote computer.

## Syntax

```
disableprinterredirection:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Easy Print printer redirection is enabled. |
| 1 | Easy Print printer redirection is not enabled. |

The default value is 0.

## Examples

To disable Easy Print printer redirection, type:

```
disableprinterredirection:i:1
```




---
layout: Conceptual
title: Disableclipboardredirection | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393674(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Disableclipboardredirection
ms:assetid: 64209163-4f9f-411d-97b1-94c6ac4dabaf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393674(v=WS.10)
ms:contentKeyID: 28576040
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 3d8cec1d-289f-87b4-985b-29c27db9d497
document_version_independent_id: 3d8cec1d-289f-87b4-985b-29c27db9d497
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393674(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393674(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 48
asset_id: ff393674(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393674(v=ws.10).md
platformId: d2865bf0-f1d1-2c12-a6b9-ab1a42df27e4
---

# Disableclipboardredirection | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether Clipboard redirection is enabled when connecting to the remote computer.

## Syntax

```
disableclipboardredirection:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Clipboard redirection is enabled. |
| 1 | Clipboard redirection is not enabled. |

The default value is 0.

## Examples

To disable Clipboard redirection, type:

```
disableclipboardredirection:i:1
```




---
layout: Conceptual
title: Displayconnectionbar | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393703(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Displayconnectionbar
ms:assetid: 7fd853fe-8a44-4252-804a-0fa735d24785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393703(v=WS.10)
ms:contentKeyID: 28576069
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 6fc6610f-2f8f-ecfa-235c-a517b6a77de6
document_version_independent_id: 6fc6610f-2f8f-ecfa-235c-a517b6a77de6
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393703(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393703(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 92
asset_id: ff393703(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393703(v=ws.10).md
platformId: bf41881e-f414-60e4-b019-da236ed5d223
---

# Displayconnectionbar | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the connection bar appears when you are in full screen mode when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the **Display the connection bar when I use the full screen** check box on the **Display** tab under **Options** in RDC.

## Syntax

```
displayconnectionbar:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The connection bar does not appear. |
| 1 | The connection bar appears. |

The default value is 1.

## Examples

To configure the connection bar not to appear, type:

```
displayconnectionbar:i:0
```




---
layout: Conceptual
title: Domain | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393673(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Domain
ms:assetid: 619fa984-1382-408e-b330-90ca12c52eb6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393673(v=WS.10)
ms:contentKeyID: 28576039
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 0e9b1dcf-1a2c-25d1-37a1-59e4b9716c56
document_version_independent_id: 0e9b1dcf-1a2c-25d1-37a1-59e4b9716c56
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393673(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393673(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 101
asset_id: ff393673(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393673(v=ws.10).md
platformId: abb77ee0-e66b-cceb-d1f8-b3eca881686d
---

# Domain | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies the name of the domain in which the user account that will be used to log on to the remote computer by using Remote Desktop Connection (RDC) is located.

The value of this setting, along with the value of the username setting, will appear in the **User name** text box on the **General** tab under **Options** in RDC.

## Syntax

```
domain:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A valid domain name* | Specifies the name of the domain that will be displayed in RDC |

There is no default value.

## Examples

To specify the CONTOSO domain, type:

```
domain:s:contoso
```




---
layout: Conceptual
title: Enablecredsspsupport | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393716(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Enablecredsspsupport
ms:assetid: a77f9c29-4c35-4159-8997-0c623ece9f55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393716(v=WS.10)
ms:contentKeyID: 28576079
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: c6840c0b-2af9-7b10-941f-dc763379f64d
document_version_independent_id: c6840c0b-2af9-7b10-941f-dc763379f64d
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393716(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393716(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 76
asset_id: ff393716(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393716(v=ws.10).md
platformId: 47bd685d-76c1-6eb5-1bc9-5bb33aa9458d
---

# Enablecredsspsupport | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether RDP will use the Credential Security Support Provider (CredSSP) for authentication if it is available.

## Syntax

```
enablecredsspsupport:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | RDP will not use CredSSP, even if the operating system supports CredSSP. |
| 1 | RDP will use CredSSP, if the operating system supports CredSSP. |

The default value is 1.

## Examples

To configure RDP to not use CredSSP even if the operating system supports it, type:

```
enablecredsspsupport:i:0
```




---
layout: Conceptual
title: Full address | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393661(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Full address
ms:assetid: 30209340-0de7-47ac-98ad-49aab3fc6f42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393661(v=WS.10)
ms:contentKeyID: 28576028
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 4932e6b2-99cb-3e30-090f-0fe06f38e3a3
document_version_independent_id: 4932e6b2-99cb-3e30-090f-0fe06f38e3a3
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393661(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393661(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 99
asset_id: ff393661(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393661(v=ws.10).md
platformId: b630931b-08ff-a8e1-5223-5865292d15e3
---

# Full address | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies the name or IP address of the remote computer that you want to connect to by using Remote Desktop Connection (RDC).

This setting corresponds to the entry in the **Computer** text box on the **General** tab under **Options** in RDC.

## Syntax

```
full address:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A valid computer name, IPv4 address, or IPv6 address* | Specifies the remote computer to which you want to connect |

There is no default value.

## Examples

To specify Server1, type:

```
full address:s:server1
```

To specify a computer with the IP address of 10.10.15.15, type:

```
full address:s:10.10.15.15
```




---
layout: Conceptual
title: Keyboardhook | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393668(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Keyboardhook
ms:assetid: 4dd4494b-6e2e-4eb3-b7e9-84d603305894
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393668(v=WS.10)
ms:contentKeyID: 28576034
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: d572b77f-56b5-f9db-5bdc-cdbf6d02a044
document_version_independent_id: d572b77f-56b5-f9db-5bdc-cdbf6d02a044
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393668(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393668(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 117
asset_id: ff393668(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393668(v=ws.10).md
platformId: 6de0580a-91f1-ff75-21f9-d0194f40df16
---

# Keyboardhook | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines how Windows key combinations are applied when you are connected to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Keyboard** drop-down list on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
keyboardhook:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Windows key combinations are applied on the local computer (**On this computer**). |
| 1 | Windows key combinations are applied on the remote computer (**On the remote computer**). |
| 2 | Windows key combinations are applied in full-screen mode only (**Only when using the full screen**). |

The default value is 2.

## Examples

To configure Windows key combinations to be applied on the remote computer, type:

```
keyboardhook:i:1
```




---
layout: Conceptual
title: Load balance info | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393684(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Load balance info
ms:assetid: 140fa067-0a34-43bf-9a4d-b9b0a4aa1b6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393684(v=WS.10)
ms:contentKeyID: 28576049
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 0673fe74-9540-8c47-265e-1b4d7573427b
document_version_independent_id: 0673fe74-9540-8c47-265e-1b4d7573427b
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393684(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/9026bea517a93f81e019d9915a9e801c14939e48?path=/windows-server-2008-R2-and-2008/ff393684(v=ws.10).md&_a=contents
git_commit_id: 9026bea517a93f81e019d9915a9e801c14939e48
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 49
asset_id: ff393684(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393684(v=ws.10).md
platformId: 35fd529f-3359-02e5-1007-132ff6153b3c
---

# Load balance info | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies the provider name, endpoint type, and an endpoint.\

## Syntax

```
loadbalanceinfo:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *String* | Load-balancing information used to choose the best server for the client computer. For more information about LoadBalanceInfo, see ([https://msdn.microsoft.com/en-us/library/aa381177(VS.85).aspx](https://msdn.microsoft.com/en-us/library/aa381177%28vs.85%29.aspx)). |

There is no default value.

## Examples

```
LoadBalanceInfo:s:tsv://vmresource.1.VMFarm
```




---
layout: Conceptual
title: Negotiate security layer | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393719(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Negotiate security layer
ms:assetid: b7ec8cdc-a65d-4a5d-8f78-72db593ee6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393719(v=WS.10)
ms:contentKeyID: 28576081
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 04092e81-534f-ef10-a661-659d9e85fef2
document_version_independent_id: 04092e81-534f-ef10-a661-659d9e85fef2
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393719(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393719(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 72
asset_id: ff393719(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393719(v=ws.10).md
platformId: 507ffb3a-4fe3-6842-3abd-c748c3fc2360
---

# Negotiate security layer | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether or not RDP negotiates the security layer.

## Syntax

```
negotiate security layer:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Security layer negotiation is not enabled and the session is started by using Secure Sockets Layer (SSL). |
| 1 | Security layer negotiation is enabled and the session is started by using x.224 encryption. |

The default value is 1.

## Examples

To disable security layer negotiation, type:

```
negotiate security layer:i:0
```




---
layout: Conceptual
title: Pinconnectionbar | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393714(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Pinconnectionbar
ms:assetid: a46a5b79-64a8-4b16-b4d9-0309d0dba858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393714(v=WS.10)
ms:contentKeyID: 28576078
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 985e5ce8-0825-4f1a-bb79-022228b69a68
document_version_independent_id: 985e5ce8-0825-4f1a-bb79-022228b69a68
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393714(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393714(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 84
asset_id: ff393714(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393714(v=ws.10).md
platformId: 2a33655b-cba7-d64c-9c5d-5cd24085e5ff
---

# Pinconnectionbar | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether or not the connection bar should be pinned to the top of the remote session upon connection.

## Syntax

```
pinconnectionbar:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The connection bar should not be pinned to the top of the remote session. |
| 1 | The connection bar should be pinned to the top of the remote session. |

The default value is 1.

## Examples

To ensure that the connection bar is not pinned on top of the remote session, type:

```
pinconnectionbar:i:0
```




---
layout: Conceptual
title: Prompt for credentials on client | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393660(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Prompt for credentials on client
ms:assetid: 261c12b2-76be-4f08-adb4-9b3584df4401
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393660(v=WS.10)
ms:contentKeyID: 28576027
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: e548b279-8493-a0e0-915d-3ff357fcb8c2
document_version_independent_id: e548b279-8493-a0e0-915d-3ff357fcb8c2
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393660(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393660(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 105
asset_id: ff393660(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393660(v=ws.10).md
platformId: 3673b05a-b3ec-0b68-49ae-c117d59793ea
---

# Prompt for credentials on client | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether or not Remote Desktop Connection (RDC) prompts for credentials when connecting to a server that does not support server authentication.

## Syntax

```
prompt for credentials on client:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | RDC will not prompt for credentials when connecting to a server that does not support server authentication. |
| 1 | RDC will prompt for credentials when connecting to a server that does not support server authentication. |

The default value is 0.

## Examples

To ensure that RDC will prompt for credentials when connecting to a server that does not support server authentication, type:

```
prompt for credentials on client:i:1
```




---
layout: Conceptual
title: Redirectclipboard | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393676(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Redirectclipboard
ms:assetid: 677dc7c6-046f-47ac-8696-56b9511871e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393676(v=WS.10)
ms:contentKeyID: 28576043
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 321f53b1-60f3-4185-a102-d0637656202c
document_version_independent_id: 321f53b1-60f3-4185-a102-d0637656202c
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393676(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393676(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 99
asset_id: ff393676(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393676(v=ws.10).md
platformId: a04f66e1-bb05-d9f5-8601-d3c916750ac9
---

# Redirectclipboard | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the Clipboard on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the **Clipboard** check box on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
redirectclipboard:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The Clipboard on the local computer is not available in the remote session. |
| 1 | The Clipboard on the local computer is available in the remote session. |

The default value is 1.

## Examples

To disable Clipboard redirection, type:

```
redirectclipboard:i:0
```




---
layout: Conceptual
title: Redirectcomports | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393694(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Redirectcomports
ms:assetid: 84bf6953-8374-4050-a615-69dcf4ea3736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393694(v=WS.10)
ms:contentKeyID: 28576060
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: d8acdf12-bf43-ab96-1915-18de1284e5c9
document_version_independent_id: d8acdf12-bf43-ab96-1915-18de1284e5c9
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393694(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393694(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 106
asset_id: ff393694(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393694(v=ws.10).md
platformId: 187529fd-8e75-302c-a04e-7b51d5c62427
---

# Redirectcomports | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the COM (serial) ports on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the **Ports** check box under **More** on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
redirectcomports:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The COM ports on the local computer are not available in the remote session. |
| 1 | The COM ports on the local computer are available in the remote session. |

The default value is 0.

## Examples

To enable COM port redirection, type:

```
redirectcomports:i:1
```




---
layout: Conceptual
title: Redirectdrives | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393706(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Redirectdrives
ms:assetid: a6f6fd58-cc93-407e-8d09-70ab59510a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393706(v=WS.10)
ms:contentKeyID: 28576071
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 686f3611-cadf-5008-48bf-48dd78cfa2b5
document_version_independent_id: 686f3611-cadf-5008-48bf-48dd78cfa2b5
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393706(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393706(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 100
asset_id: ff393706(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393706(v=ws.10).md
platformId: dddca07f-1404-1f2c-5ead-418464850a9b
---

# Redirectdrives | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether drives on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selections for **Drives** under **More** on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
redirectdrives:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The drives on the local computer are not available in the remote session. |
| 1 | The drives on the local computer are available in the remote session. |

The default value is 0.

## Examples

To enable drive redirection, type:

```
redirectdrives:i:1
```




---
layout: Conceptual
title: Redirectprinters | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393671(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Redirectprinters
ms:assetid: 5bd2cf35-7ed2-41f2-a884-584a58741309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393671(v=WS.10)
ms:contentKeyID: 28576037
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: f4272314-b228-c5eb-3435-692ef0f4382f
document_version_independent_id: f4272314-b228-c5eb-3435-692ef0f4382f
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393671(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393671(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 102
asset_id: ff393671(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393671(v=ws.10).md
platformId: c52a8f33-6857-8ddc-2a82-08806af9ded5
---

# Redirectprinters | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether printers configured on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Printers** check box on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
redirectprinters:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The printers on the local computer are not available in the remote session. |
| 1 | The printers on the local computer are available in the remote session. |

The default value is 1.

## Examples

To disable printer redirection, type:

```
redirectprinters:i:0
```




---
layout: Conceptual
title: Redirectsmartcards | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393713(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Redirectsmartcards
ms:assetid: 97190325-4166-4369-bae1-3b1c97da265b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393713(v=WS.10)
ms:contentKeyID: 28576077
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: d2ca50ab-82f9-38bd-67ea-dd4758d7ff0a
document_version_independent_id: d2ca50ab-82f9-38bd-67ea-dd4758d7ff0a
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393713(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393713(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 111
asset_id: ff393713(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393713(v=ws.10).md
platformId: 05958499-38be-78a6-f38e-ce740a77cc88
---

# Redirectsmartcards | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether smart card devices on the client computer will be redirected and available in the remote session when you connect to a remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Smart cards** check box under **More** on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
redirectsmartcards:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The smart card device on the local computer is not available in the remote session. |
| 1 | The smart card device on the local computer is available in the remote session. |

The default value is 1.

## Examples

To disable smart card redirection, type:

```
redirectsmartcards:i:0
```




---
layout: Conceptual
title: Screen mode ID | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393692(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Screen mode ID
ms:assetid: 4f27133d-c361-4361-8827-89980848f47b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393692(v=WS.10)
ms:contentKeyID: 28576058
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 07947447-4b2f-4817-7b95-c0bcc7ee8720
document_version_independent_id: 07947447-4b2f-4817-7b95-c0bcc7ee8720
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393692(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393692(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 93
asset_id: ff393692(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393692(v=ws.10).md
platformId: bf10ec78-c2cb-4e77-8db4-8870eb1d6dd2
---

# Screen mode ID | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the remote session window appears full screen when you connect to the remote computer by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Display configuration** slider on the **Display** tab under **Options** in RDC.

## Syntax

```
screen mode id:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 1 | The remote session will appear in a window. |
| 2 | The remote session will appear full screen. |

The default value is 2.

## Examples

To configure the remote session to appear in a window, type:

```
screen mode id:i:1
```




---
layout: Conceptual
title: Server port | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393683(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Server port
ms:assetid: 0e874bb6-5fdd-4c57-9505-cfd3b2384efe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393683(v=WS.10)
ms:contentKeyID: 28576050
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 220e936b-c4e4-3ac7-135d-ddb1f4e0f9bf
document_version_independent_id: 220e936b-c4e4-3ac7-135d-ddb1f4e0f9bf
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393683(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393683(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 63
asset_id: ff393683(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393683(v=ws.10).md
platformId: 3f2a406b-3df5-e108-a24b-803915f7df62
---

# Server port | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines which TCP port the Remote Desktop Protocol (RDP) will use when you connect to the remote computer by using Remote Desktop Connection (RDC).

## Syntax

```
server port:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *Hexadecimal value* | Specifies the port to connect to on the remote computer. |

The default value is 0xD3D.

## Examples

To specify port 3900, type:

```
server port:i:0xF3C
```




---
layout: Conceptual
title: Session bpp | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393680(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Session bpp
ms:assetid: 02129b18-05c6-4ec6-bff6-220b66d58568
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393680(v=WS.10)
ms:contentKeyID: 28576046
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: efc4f719-e193-5b55-1e02-b15db29a901d
document_version_independent_id: efc4f719-e193-5b55-1e02-b15db29a901d
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393680(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393680(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 93
asset_id: ff393680(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393680(v=ws.10).md
platformId: 7045b487-08b6-b764-fb76-3be8f685bb70
---

# Session bpp | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines the color depth on the remote computer when you connect by using Remote Desktop Connection (RDC).

This setting corresponds to the selection in the **Colors** drop-down list on the **Display** tab under **Options** in RDC.

## Syntax

```
session bpp:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 15 | High color (15 bit) |
| 16 | High color (16 bit) |
| 24 | True color (24 bit) |
| 32 | Highest quality (32 bit) |

The default value is set to the color depth on the local computer.

## Examples

To specify True color (24 bit), type:

```
session bpp:i:24
```




---
layout: Conceptual
title: Smart sizing | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393693(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Smart sizing
ms:assetid: 505a9b57-58ae-4a9c-9b8e-08b3e61286d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393693(v=WS.10)
ms:contentKeyID: 28576059
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 99a05bdd-a03d-00ff-d7be-87e6748a1f88
document_version_independent_id: 99a05bdd-a03d-00ff-d7be-87e6748a1f88
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393693(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393693(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 85
asset_id: ff393693(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393693(v=ws.10).md
platformId: b585259b-bb77-ebc9-4b61-38d981b2b95e
---

# Smart sizing | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether or not the client computer can scale the content on the remote computer to fit the window size of the client computer.

## Syntax

```
smart sizing:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | The client window display of desktop will not be scaled when resized. |
| 1 | The client window display of desktop will be scaled when resized. |

The default value is 0.

## Examples

To configure the client to not scale the content on the remote computer, type:

```
smart sizing:i:1
```




---
layout: Conceptual
title: Span monitors | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393686(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Span monitors
ms:assetid: 7bb17f74-9db3-4212-8a9c-e1a526222cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393686(v=WS.10)
ms:contentKeyID: 28576052
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 3d5a291c-cfbf-4551-853d-d296f4cea326
document_version_independent_id: 3d5a291c-cfbf-4551-853d-d296f4cea326
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393686(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393686(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 96
asset_id: ff393686(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393686(v=ws.10).md
platformId: a6a657ca-631b-9197-1cb3-03a017ddb9cf
---

# Span monitors | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines whether the remote session window will be spanned across multiple monitors when you connect to the remote computer by using Remote Desktop Connection (RDC).

Note

If the client computer is running Windows 7 and the server you are connecting to is running Windows Server 2008 R2, we recommend that you use the **Use multimon** RDP setting instead. 

## Syntax

```
span monitors:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Monitor spanning is not enabled. |
| 1 | Monitor spanning is enabled. |

The default value is 0.

## Examples

To enable monitor spanning, type:

```
span monitors:i:1
```




---
layout: Conceptual
title: Usbdevicestoredirect | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/gg607271(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Usbdevicestoredirect
ms:assetid: c74e4512-3bdf-4078-896b-d9a02c18c020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607271(v=WS.10)
ms:contentKeyID: 34135426
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 484347db-989c-a21e-f989-3d8122783a99
document_version_independent_id: 484347db-989c-a21e-f989-3d8122783a99
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/gg607271(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/gg607271(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 324
asset_id: gg607271(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/gg607271(v=ws.10).md
platformId: 6eae0030-c9c7-9e57-bdb7-0cafd6ba8e7f
---

# Usbdevicestoredirect | Microsoft Learn

Applies To: Windows Server 2008 R2 with SP1

This setting determines which supported RemoteFX USB devices on the client computer will be redirected and available in the remote session when you connect to a remote session that supports RemoteFX USB redirection by using Remote Desktop Connection (RDC).

This setting corresponds to the selections for **Other supported RemoteFX USB devices** under **More** on the **Local Resources** tab under **Options** in RDC.

## Syntax

```
usbdevicestoredirect:s:<value1>[;<value2>…]
```

## Values

| Value | Explanation |
| --- | --- |
| *No value specified* | Do not redirect any supported RemoteFX USB devices. |
| \* | Redirect all supported RemoteFX USB devices for redirection that are not redirected by high-level redirection mechanisms. |
| *{Device Setup Class GUID}* | Redirect all supported RemoteFX USB devices that are members of the specified device setup class. |
| *USB\InstanceID* | Redirect a supported RemoteFX USB device specified by the given instance ID. |
| -*USB\InstanceID* | Do not redirect a supported RemoteFX USB device specified by the given instance ID, even if the device is in a device setup class that is redirected. |

There is no default value.

## Examples

To redirect all supported RemoteFX USB devices that are not redirected by high-level redirection mechanisms, type:

```
usbdevicestoredirect:s:* 
```

To redirect all supported RemoteFX USB devices with a device setup class GUID of {6bdd1fc6-810f-11d0-bec7-08002be2092f}, type:

```
usbdevicestoredirect:s:{6bdd1fc6-810f-11d0-bec7-08002be2092f}
```

To redirect all supported RemoteFX USB devices that are not redirected by high-level redirection mechanisms, RemoteFX USB devices with a device setup class GUID of {6bdd1fc6-810f-11d0-bec7-08002be2092f}, and RemoteFX USB devices with device setup class GUID of {4d36e96c-e325-11ce-bfc1-08002be10318}, type:

```
usbdevicestoredirect:s:*;{6bdd1fc6-810f-11d0-bec7-08002be2092f};{4d36e96c-e325-11ce-bfc1-08002be10318}
```

To redirect supported RemoteFX USB devices with an instance ID of USB\VID\_095D&PID\_9208\5&23639F31&0&2 or USB\VID\_045E&PID\_076F\5&14D1A39&0&7, type:

```
usbdevicestoredirect:s:USB\VID_095D&PID_9208\5&23639F31&0&2;USB\VID_045E&PID_076F\5&14D1A39&0&7
```

To redirect all supported RemoteFX USB devices that are not redirected by high-level redirection mechanisms except for a device with an instance ID of USB\VID\_045E&PID\_076F\5&14D1A39&0&7, all supported RemoteFX USB devices with a device setup class GUID of {6bdd1fc6-810f-11d0-bec7-08002be2092f}, all supported RemoteFX USB devices with a device setup class GUID of {4d36e96c-e325-11ce-bfc1-08002be10318}, and a supported RemoteFX USB device with an instance ID of USB\VID\_095D&PID\_9208\5&23639F31&0&2, type:

```
usbdevicestoredirect:s:*;{6bdd1fc6-810f-11d0-bec7-08002be2092f};{4d36e96c-e325-11ce-bfc1-08002be10318};USB\VID_095D&PID_9208\5&23639F31&0&2;-USB\VID_045E&PID_076F\5&14D1A39&0&7
```




---
layout: Conceptual
title: Username | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393678(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Username
ms:assetid: 6fc50183-1b39-4fb0-abef-d684fffe036f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393678(v=WS.10)
ms:contentKeyID: 28576045
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 377b080e-fd7c-1d84-2e6a-45a5b770a924
document_version_independent_id: 377b080e-fd7c-1d84-2e6a-45a5b770a924
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393678(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393678(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 90
asset_id: ff393678(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393678(v=ws.10).md
platformId: d6b8d2a5-a27d-f2b3-fb1f-a1339f4ed275
---

# Username | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies the name of the user account that will be used to log on to the remote computer by using Remote Desktop Connection (RDC).

The value of this setting, along with the value of the domain setting, will appear in the **User name** box on the **General** tab under **Options** in RDC.

## Syntax

```
username:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A valid user name* | Specifies the user account that will be displayed in RDC. |

There is no default value.

## Examples

To specify User1, type:

```
username:s:user1
```




---
layout: Conceptual
title: Use multimon | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393695(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Use multimon
ms:assetid: 8864451e-bd62-45a9-b1df-406139347bfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393695(v=WS.10)
ms:contentKeyID: 28576061
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 5807305c-34e3-539e-43f9-4ac90e525fdf
document_version_independent_id: 5807305c-34e3-539e-43f9-4ac90e525fdf
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393695(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393695(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 92
asset_id: ff393695(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393695(v=ws.10).md
platformId: 079100aa-39d6-8e9d-cf89-d014a975a32b
---

# Use multimon | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting configures multiple monitor support when you connect to the remote computer by using Remote Desktop Connection (RDC).

Note

If the client computer is running Windows 7 and the server you are connecting to is running Windows Server 2008 R2, you should use this RDP setting instead of the **Span monitors** RDP setting. 

## Syntax

```
use multimon:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Do not enable multiple monitor support. |
| 1 | Enable multiple monitor support. |

The default value is 0.

## Examples

To enable multiple monitor support, type:

```
use multimon:i:1
```




---
layout: Conceptual
title: Videoplaybackmode | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393718(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Videoplaybackmode
ms:assetid: aaf22e0b-bab7-413c-a6b4-3844beb939bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393718(v=WS.10)
ms:contentKeyID: 28576080
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 4cfb9ad9-513a-6b21-4d3d-2fec8cc0d08a
document_version_independent_id: 4cfb9ad9-513a-6b21-4d3d-2fec8cc0d08a
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393718(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393718(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 71
asset_id: ff393718(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393718(v=ws.10).md
platformId: e50a9226-8166-3745-68e8-7de0b008629f
---

# Videoplaybackmode | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting determines if Remote Desktop Connection (RDC) will use RDP efficient multimedia streaming for video playback.

## Syntax

```
videoplaybackmode:i:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| 0 | Do not use RDP efficient multimedia streaming for video playback. |
| 1 | Use RDP efficient multimedia streaming for video playback when possible. |

The default value is 1.

## Examples

To configure RDC to not use RDP efficient multimedia streaming for video playback, type:

```
videoplaybackmode:i:0
```




---
layout: Conceptual
title: Winposstr | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393696(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Winposstr
ms:assetid: 673bea3d-82f6-4c0e-9dbb-ff13a8485fdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393696(v=WS.10)
ms:contentKeyID: 28576064
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: 1ec78a9a-4b6d-917f-4771-5442ec9ff367
document_version_independent_id: 1ec78a9a-4b6d-917f-4771-5442ec9ff367
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393696(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/9026bea517a93f81e019d9915a9e801c14939e48?path=/windows-server-2008-R2-and-2008/ff393696(v=ws.10).md&_a=contents
git_commit_id: 9026bea517a93f81e019d9915a9e801c14939e48
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 69
asset_id: ff393696(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393696(v=ws.10).md
platformId: 45b4084a-85d5-566f-1a70-91b8ef81659a
---

# Winposstr | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting specifies the position of the Remote Desktop Connection (RDC) window on the client computer.

## Syntax

```
winposstr:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *6 numbers separated by commas* | Represents a string form of the WINDOWSPOS structure. For more information about the WINDOWSPOS function, see https://msdn2.microsoft.com/en-us/library/ms632612.aspx. |

The default value is 0,3,0,0,800,600.

## Examples

To specify the window to be the dimensions of 1024 x 768, type:

```
winposstr:s:0,3,0,0,1024,768
```




---
layout: Conceptual
title: Workspace id | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/ff393710(v=ws.10)
breadcrumb_path: /previous-versions/windows/it-pro/breadcrumb/toc.json
ROBOTS: NOINDEX,NOFOLLOW
current_version_url: https://docs.microsoft.com/windows-server/windows-server
is_archived: true
uhfHeaderId: MSDocsHeader-Archive
ms.author: Archiveddocs
ms.prod: windows-server-2008-R2
ms.topic: archived
author: Archiveddocs
TOCTitle: Workspace id
ms:assetid: 8f8c7cc3-b75a-41cc-b43d-60d11c872f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Ff393710(v=WS.10)
ms:contentKeyID: 28576075
ms.date: 2012-07-02T00:00:00.0000000Z
mtps_version: v=WS.10
locale: en-us
document_id: e4fa0032-59ee-4fc6-2d6e-010c64887ab9
document_version_independent_id: e4fa0032-59ee-4fc6-2d6e-010c64887ab9
updated_at: 2021-11-12T17:51:00.0000000Z
original_content_git_url: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr?path=/windows-server-2008-R2-and-2008/ff393710(v=ws.10).md&version=GBlive&_a=contents
gitcommit: https://docs-archive.visualstudio.com/DefaultCollection/docs-archive-project/_git/windows-itpro-docs-archive-2-pr/commit/ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1?path=/windows-server-2008-R2-and-2008/ff393710(v=ws.10).md&_a=contents
git_commit_id: ab1a0ea5e8ffb7765f2d7524fa1233618671e6e1
site_name: Docs
depot_name: MSDN.windows-server-2008-R2-and-2008
page_type: conceptual
toc_rel: toc.json
feedback_system: None
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 65
asset_id: ff393710(v=ws.10)
moniker_range_name: 
monikers: []
item_type: Content
source_path: windows-server-2008-R2-and-2008/ff393710(v=ws.10).md
platformId: b6368c9e-8bc5-2636-6798-5463c4715346
---

# Workspace id | Microsoft Learn

Applies To: Windows Server 2008 R2

This setting defines the RemoteApp and Desktop ID associated with the RDP file that contains this setting.

## Syntax

```
workspaceid:s:<value>
```

## Values

| Value | Explanation |
| --- | --- |
| *A valid RemoteApp and Desktop Connection ID* | Specifies the RemoteApp and Desktop Connection ID associated with the RDP file. |

There is no default value.

## Examples

To specify contoso1 as the RemoteApp and Desktop Connection ID, type:

```
workspaceid:s:contoso1
```




