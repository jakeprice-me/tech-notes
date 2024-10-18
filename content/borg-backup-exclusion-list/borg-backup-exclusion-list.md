---
aliases:
  - borg-backup-exclusion-list
category: borg
classification: public
date: 2023-07-10T22:16:40
date_modified: 2023-07-10T22:16:40
draft: false
id: 20230710221640
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - borg
  - backup
  - exclusion
  - ignore
title: Borg Backup Exclusion List
type: tech-note
---

I've had a few occasions where Borg Backup has reported back an error because the file couldn't be accessed. Often it's a Docker created directory owned by `root`. I often won't even care about backing those directories up so it's handy to specify a list of files to exclude from the backup.

Here's an example command including the `--exclude-from` flag which specifies the path to the exclusion file.

```sh
borg create \
	--verbose \
	--debug \
	--show-rc \
	--progress \
	--stats \
	--exclude-from exclude.txt \
	borg::$(date +\%Y\%m\%d\%H\%M\%S) <path-to-backup>
```

The file itself is a simple plain-text list of paths to files/directories you want to exclude.

Example contents:

```sh
/home/user/example.txt
/etc/config/settings.ini
/usr/local/bin
/mnt/storage
```
