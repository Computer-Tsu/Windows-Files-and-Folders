
set device
set drivergroup
set drivergroupfilter
set driverpackage
set image
set imagegroup
set server
set transportserver
set multicasttransmission
start namespace
start server
start transportserver
stop server
stop transportserver

-----

---
layout: Conceptual
title: wdsutil | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/wdsutil
breadcrumb_path: /windows-server/breadcrumbs/toc.json
uhfHeaderId: MSDocsHeader-WindowsServer
feedback_system: Standard
recommendations: true
ms.service: windows-server
ms.subservice: windows-commands
ms.update-cycle: 1095-days
description: Reference article for wdsutil, which is a command-line utility used for managing your Windows Deployment Services server.
ms.topic: reference
ms.author: roharwoo
author: robinharwood
ms.date: 2017-10-16T00:00:00.0000000Z
locale: en-us
document_id: 9fd71269-684f-96af-ffca-099ec7aa52c1
document_version_independent_id: 05df26b2-bf29-47cf-9184-10e25445a725
updated_at: 2025-09-22T17:32:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/live/WindowsServerDocs/administration/windows-commands/wdsutil.md
gitcommit: https://github.com/MicrosoftDocs/windowsserverdocs-pr/blob/a55cfa381124bf9308e0f0bbda546cd10e2be85d/WindowsServerDocs/administration/windows-commands/wdsutil.md
git_commit_id: a55cfa381124bf9308e0f0bbda546cd10e2be85d
site_name: Docs
depot_name: MSDN.WindowsServerDocs-pr
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.WindowsServerDocs-pr/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_type: ''
feedback_help_link_url: ''
word_count: 298
asset_id: administration/windows-commands/wdsutil
moniker_range_name: 
monikers: []
item_type: Content
source_path: WindowsServerDocs/administration/windows-commands/wdsutil.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 6914c631-e644-3357-536b-09938e11d46c
---

# wdsutil | Microsoft Learn

Wdsutil is a command-line utility used for managing your Windows Deployment Services server. To run these commands, click **start**, right-click **Command prompt**, and click **Run as administrator**.

## Commands

| Command | Description |
| --- | --- |
| [wdsutil add command](wdsutil-add) | Adds objects or prestages computers. |
| [wdsutil approve-autoadddevices command](wdsutil-approve-autoadddevices) | Approves computers that are pending administrator approval. |
| [wdsutil convert-riprepimage command](wdsutil-convert-riprepimage) | Converts an existing remote Installation Preparation (RIPrep) image to a Windows Image (.wim) file. |
| [wdsutil copy command](wdsutil-copy) | Copies an image or a driver group. |
| [wdsutil delete-autoadddevices command](wdsutil-delete-autoadddevices) | Deletes computers that are in the Auto-add database (which stores information about the computers on the server). |
| [wdsutil disable command](wdsutil-disable) | Disables all services for Windows Deployment Services. |
| [wdsutil disconnect-client command](wdsutil-disconnect-client) | Disconnects a client from a multicast transmission or namespace. |
| [wdsutil enable command](wdsutil-enable) | Enables all services for Windows Deployment Services. |
| [wdsutil export-image command](wdsutil-export-image) | Exports an image from the image store to a .wim file. |
| [wdsutil get command](wdsutil-get) | Retrieves properties and attributes about the specified object. |
| [wdsutil initialize-server command](wdsutil-initialize-server) | Configures a Windows Deployment Services server for initial use. |
| [wdsutil new command](wdsutil-new) | creates new capture and discover images as well as multicast transmissions and namespaces. |
| [wdsutil progress command](wdsutil-progress) | Displays the progress status while a command is being executed. |
| [wdsutil reject-autoadddevices command](wdsutil-reject-autoadddevices) | Rejects computers that are pending administrator approval. |
| [wdsutil remove command](wdsutil-remove) | removes objects. |
| [wdsutil replace-image command](wdsutil-replace-image) | replaces a boot or installation image with a new version of that image. |
| [wdsutil set command](wdsutil-set) | Sets properties and attributes on the specified object. |
| [wdsutil start server command](wdsutil-start-server) | starts all services on the Windows Deployment Services server, including multicast transmissions, namespaces, and the Transport Server. |
| [wdsutil stop server command](wdsutil-stop-server) | Stops all services on the Windows Deployment Services server. |
| [wdsutil uninitialize-server command](wdsutil-uninitialize-server) | reverts changes made during server initialization. |
| [wdsutil update-serverfiles command](wdsutil-update-serverfiles) | Updates server files on the remoteInstall share. |
| [wdsutil verbose command](wdsutil-verbose) | Displays verbose output for the specified command. |




