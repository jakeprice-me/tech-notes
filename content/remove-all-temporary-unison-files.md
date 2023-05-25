---
alias: remove-all-temporary-unison-files
category: cli
classification: public
date: 2022-11-06 10:19:01
date_modified: null
id: 20221106101901
link: null
pinned: false
tags: [unison, sync, find, temporary]
title: Remove all Temporary Unison Files
type: tech-note
uuid: f3fcafc1-90fb-4383-aca3-fd1dd49b8521
---

Find and delete all `.unison.tmp` files.

```sh
# Dry run:
find my/ -type f -name *.unison.tmp

# Find and delete:
find my/ -type f -name *.unison.tmp -delete
```