---
aliases:
  - sort-files-and-directories-by-disk-size
category: cli
classification: public
date: 2019-01-28T12:52:01
date_modified: 2019-01-28T12:52:01
draft: false
id: 20190128125201
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - directory
  - file
  - size
title: Sort files and directories by disk size
type: tech-note
---

Sort files and directories by human-readable disk size order.

```sh
$ du --summarize --human-readable * | sort --human-numeric-sort --reverse
```