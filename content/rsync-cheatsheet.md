---
aliases:
  - rsync-cheatsheet
archive_links: 
category: cli
classification: public
date: 2020-06-20 23:26:43
date_modified: 2020-06-20 23:26:43
id: 20200620232643
link: 
local_archive: 
pinned: false
series: 
tags: [rsync, backups]
title: rsync Cheatsheet
type: tech-note
---

```sh
# Backup `my` directory to `jp-archive-1` external drive.
rsync --verbose --recursive --perms --xattrs --times --human-readable $HOME/my /run/media/jprice/jp-archive-1/backups/
```