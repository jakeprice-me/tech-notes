---
alias: exif-tool-cheatsheet
category: cli
classification: public
date: 2021-12-29 14:05:07
date_modified: null
id: 20211229140507
link: null
pinned: false
tags: [exif, photo, video, tag]
title: Exif Tool Cheatsheat
type: tech-note
uuid: d1e41021-e0b0-41e9-adb5-b3d29bae8661
---

More info [here](https://exiftool.org/filename.html)

```sh
# Dry-run in current directory:
exiftool -d %Y%m%d_%H%M%S-c.%%e "-testname<CreateDate" .

# Rename all files with "CreateDate" in directory and add copy number if required:
exiftool -d %Y%m%d_%H%M%S%%-c.%%e "-filename<CreateDate" .
```