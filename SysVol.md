Windows `\System Volume Information\'

Found on NTFS, ReFS, and some ExFAT volumes.

# System Volume Information (SVI) - Technical Reference

This document compiles Microsoft technical references and explanations of the System Volume Information folder, its purpose, and its internal components.

---

## Overview

The **System Volume Information (SVI)** folder is a hidden, protected system folder found on NTFS, exFAT, and ReFS volumes.  
It is used by Windows to store metadata and operational data for several core subsystems, including restore points, indexing, replication, and journaling.  
Administrators and users are normally denied access to prevent accidental changes that could break Windows features.

---

## Typical Contents of SVI

| Component                               | Description |
|-----------------------------------------|-------------|
| **Volume Shadow Copies / Restore Points** | Stores data for System Restore and Previous Versions. Managed by the Volume Shadow Copy Service (VSS). |
| **DFS Replication (DFSR) Database**      | Replication metadata and databases for DFS Replication on Windows Server. |
| **Data Deduplication**                   | Chunk store and deduplication metadata, available on Windows Server. |
| **Windows Backup Catalogs**              | Catalog files and backup information for Windows Backup and Windows Server Backup. |
| **NTFS Change Journal (USN Journal)**    | A continuously updated journal of file changes on the volume, used by antivirus, backup, and indexing services. |
| **Distributed Link Tracking (tracking.log)** | Maintains object identifiers and tracking for moved/renamed files to preserve links. |
| **Windows Search Index (IndexerVolumeGuid)** | Identifiers and indexing metadata for the Windows Search service. |
| **File History Database**                | Metadata used by the File History backup feature. |
| **Chkdsk Data**                          | Logs and repair data written by CHKDSK when scanning and repairing the volume. |
| **Miscellaneous Files**                  | Includes WPSettings.dat and other subsystem-specific data. |

---

## Microsoft Documentation Sources

- [Volume Shadow Copy Service (VSS)](https://learn.microsoft.com/en-us/windows/win32/vss/volume-shadow-copy-service)
- [Change Journal (USN Journal)](https://learn.microsoft.com/en-us/windows/win32/fileio/change-journals)
- [Distributed Link Tracking](https://learn.microsoft.com/en-us/windows/win32/fileio/distributed-link-tracking)
- [Search Indexing Architecture](https://learn.microsoft.com/en-us/windows/win32/search/-search-3x-architecture)
- [Data Deduplication Overview](https://learn.microsoft.com/en-us/windows-server/storage/data-deduplication/overview)
- [DFS Replication Overview](https://learn.microsoft.com/en-us/windows-server/storage/dfs-replication/dfsr-overview)
- [NTFS Technical Reference](https://learn.microsoft.com/en-us/windows/win32/fileio/ntfs-technical-reference)
- [System Volume Information Folder (Microsoft Support KB)](https://support.microsoft.com/en-us/topic/description-of-the-system-volume-information-folder-in-windows-8327c88a-25d5-438b-8f64-b0d7fa97b57f)
- [System Volume Information Large Folder Troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/windows-client/deployment/system-volume-information-large)

---
