---
aliases:
  - rsync-cheatsheet
category: cli
classification: public
date: 2020-06-20T23:26:43
date_modified: 2020-06-20T23:26:43
draft: false
id: 20200620232643
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - backup
  - rsync
title: rsync Cheatsheet
type: tech-note
---

```sh
# Backup `my` directory to `jp-archive-1` external drive.
rsync --verbose --recursive --perms --xattrs --times --human-readable $HOME/my /run/media/jprice/jp-archive-1/backups/
```