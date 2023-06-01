---
alias: delete-files-matching-a-pattern-using-find
category: cli
classification: public
date: 2019-01-28 09:43:00
date_modified: 2019-01-28 09:43:00
id: 20190128094300
link: 
pinned: false
series: 
tags: [find, delete, file, directory, pattern]
title: Delete files matching a pattern using find
type: tech-note
uuid: f50484b6-1f51-4d3a-bcd6-40230a0b62b3
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