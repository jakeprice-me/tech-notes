---
alias: loop-through-files-search-and-replace
category: bash
classification: public
date: 2020-03-09 20:13:20
date_modified: 2020-03-09 20:13:20
id: 20200309201320
link: 
link_archive: 
pinned: false
series: 
tags: [bash, sed, loop, iteration]
title: Loop Through Files and Search and Replace
type: tech-note
uuid: 4d3bf7a5-1fa2-4bd0-9639-d1657aa7552d
---

Loop through all files, and run a search and replace with `sed`.

```sh
for i in *.txt; do
  sed -i "s/Date::/date:/g" $i;
done
```