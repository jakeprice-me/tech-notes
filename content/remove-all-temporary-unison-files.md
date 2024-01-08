---
aliases:
  - remove-all-temporary-unison-files
archive_links: 
category: cli
classification: public
date: 2022-11-06T10:19:01
date_modified: 2022-11-06T10:19:01
id: 20221106101901
link: 
local_archive: 
pinned: false
series: 
tags: [unison, sync, find, temporary]
title: Remove all Temporary Unison Files
type: tech-note
---

Find and delete all `.unison.tmp` files.

```sh
# Dry run:
find my/ -type f -name *.unison.tmp

# Find and delete:
find my/ -type f -name *.unison.tmp -delete
```