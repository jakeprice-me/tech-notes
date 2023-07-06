---
alias: sort-files-and-directories-by-disk-size
category: cli
classification: public
date: 2019-01-28 12:52:01
date_modified: 2019-01-28 12:52:01
id: 20190128125201
link: 
link_archive: 
pinned: false
series: 
tags: [file, directory, size]
title: Sort files and directories by disk size
type: tech-note
uuid: 2a700633-f389-476a-ba70-f79f4ed8288b
---

Sort files and directories by human-readable disk size order.

```sh
$ du --summarize --human-readable * | sort --human-numeric-sort --reverse
```