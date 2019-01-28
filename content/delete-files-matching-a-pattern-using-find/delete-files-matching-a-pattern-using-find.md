---
aliases:
  - delete-files-matching-a-pattern-using-find
archive_links: 
category: cli
classification: public
date: 2019-01-28T09:43:00
date_modified: 2019-01-28T09:43:00
draft: false
id: 20190128094300
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [find, delete, file, directory, pattern]
title: Delete files matching a pattern using find
type: tech-note
---

Delete all files that match a specific pattern. This is just `find` with `-delete` appended, so be careful!

Get your pattern working and returning the results you want before you use `-delete`.

```sh
# Files & directories:
$ find <path-to-search> -name '<pattern>' #-delete

# Files only:
$ find <path-to-search> -type f -name '<pattern>' #-delete

# Directories only:
$ find <path-to-search> -type d -name '<pattern>' #-delete
```