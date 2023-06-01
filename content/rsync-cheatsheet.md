---
alias: rsync-cheatsheet
category: cli
classification: public
date: 2020-06-20 23:26:43
date_modified: 2020-06-20 23:26:43
id: 20200620232643
link: 
pinned: false
series: 
tags: [rsync, backups]
title: rsync Cheatsheet
type: tech-note
uuid: 1f677e56-3332-4990-a5d4-9c32caf4849e
---

```sh
# Backup `my` directory to `jp-archive-1` external drive.
rsync --verbose --recursive --perms --xattrs --times --human-readable $HOME/my /run/media/jprice/jp-archive-1/backups/
```