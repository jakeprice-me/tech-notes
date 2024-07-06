---
aliases:
  - exiftool-cheatsheet
archive_links: 
category: cli
classification: public
date: 2024-07-06T12:07:28
date_modified: 2024-07-06T12:07:28
draft: false
id: 20240706120728
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - exif
  - command-line
  - metadata
title: exiftool Cheatsheet
type: tech-note
---

```sh
# View tag names for use in commands:
exiftool -s <files-or-dir>

# Display tag values:
exiftool -T -DateTimeOriginal -FileName <files-or-dir>
exiftool -T -FileModifyDate -FileName <files-or-dir>
```
