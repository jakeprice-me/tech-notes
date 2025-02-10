---
aliases:
  - remove-all-temporary-unison-files
category: cli
classification: public
date: 2022-11-06T10:19:01
date_modified: 2022-11-06T10:19:01
draft: false
id: 20221106101901
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - find
  - sync
  - temporary
  - unison
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