---
aliases:
  - loop-through-files-search-and-replace
archive_links: 
category: bash
classification: public
date: 2020-03-09T20:13:20
date_modified: 2020-03-09T20:13:20
draft: false
id: 20200309201320
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [bash, sed, loop, iteration]
title: Loop Through Files and Search and Replace
type: tech-note
---

Loop through all files, and run a search and replace with `sed`.

```sh
for i in *.txt; do
  sed -i "s/Date::/date:/g" $i;
done
```