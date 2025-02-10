---
aliases:
  - borg-backup-item-flags
category: borg
classification: public
date: 2022-10-26T13:49:07
date_modified: 2024-09-23T19:07:10
draft: false
id: 20221026134907
image: 
links:
  - https://borgbackup.readthedocs.io/en/stable/usage/create.html#item-flags
local_archive_links:
  - attachments/borg-backup-item-flags.html
pinned: false
print: false
series: 
tags:
  - backup
  - borg
  - character
  - flag
  - status
  - type
title: Borg Backup Item Flags
type: tech-note
---

When Borg Backup runs each file will show a status character, these are detailed below:

> A uppercase character represents the status of a regular file relative to the "files" cache (not relative to the repo -- this is an issue if the files cache is not used). Metadata is stored in any case and for `A` and `M` also new data chunks are stored. For `U` all data chunks refer to already existing chunks.
>
> - `A` = regular file, added (see also I am seeing `A` (added) status for an unchanged file!? in the FAQ)
> - `M` = regular file, modified
> - `U` = regular file, unchanged
> - `C` = regular file, it changed while we backed it up
> - `E` = regular file, an error happened while accessing/reading this file
>
> A lowercase character means a file type other than a regular file, borg usually just stores their metadata:
>
> - `d` = directory
> - `b` = block device
> - `c` = char device
> - `h` = regular file, hardlink (to already seen inodes)
> - `s` = symlink
> - `f` = fifo
>
> Other flags used include:
>
> - `i` = backup data was read from standard input (stdin)
> - `-` = dry run, item was not backed up
> - `x` = excluded, item was not backed up
> - `?` = missing status code (if you see this, please file a bug report!)
>
> — [borg create — Borg - Deduplicating Archiver 1.2.3 documentation](https://borgbackup.readthedocs.io/en/stable/usage/create.html#item-flags)