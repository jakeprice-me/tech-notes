---
aliases:
  - exif-tool-cheatsheet
archive_links: 
category: cli
classification: public
date: 2021-12-29T14:05:07
date_modified: 2021-12-29T14:05:07
draft: false
id: 20211229140507
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [exif, photo, video, tag]
title: Exif Tool Cheatsheat
type: tech-note
---

More info [here](https://exiftool.org/filename.html)

```sh
# Dry-run in current directory:
exiftool -d %Y%m%d_%H%M%S-c.%%e "-testname<CreateDate" .

# Rename all files with "CreateDate" in directory and add copy number if required:
exiftool -d %Y%m%d_%H%M%S%%-c.%%e "-filename<CreateDate" .
```