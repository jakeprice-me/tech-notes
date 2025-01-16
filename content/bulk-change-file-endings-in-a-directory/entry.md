---
aliases:
  - bulk-change-file-endings-in-a-directory
category: linux
classification: public
date: 2020-03-02T15:10:26
date_modified: 2020-03-02T15:10:26
draft: false
id: 20200302151026
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - rename
  - file
title: Bulk change file endings in a directory
type: tech-note
---

> [!warning]
> The renaming has no safeguards by default or without any one of the options `--no-overwrite`, `--interactive` or `--no-act`.

```sh
# Rename all files ending with asc to txt:
rename asc txt *.asc

# Remove match from filenames:
rename 's/-MC02FW6SFMD6M//g' *.md
```

