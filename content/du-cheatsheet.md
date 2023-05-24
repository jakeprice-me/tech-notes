---
alias: du-cheatsheet
category: cli
classification: public
date: 2020-07-05 19:40:16
date_modified: null
id: 20200705194016
pinned: false
tags:
- disk-usage
- du
- bash
- linux
title: File Space Usage with du
type: tech-note
uuid: 2cdf7e39-e5ab-4517-bbae-0b1846269fe4
---

```sh
# Show disk usage.
du --human-readable --max-depth=1

# Show and then sort disk usage.
du --human-readable --max-depth=1 | sort -n
```