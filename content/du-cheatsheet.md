---
aliases:
  - du-cheatsheet
archive_links: 
category: cli
classification: public
date: 2020-07-05T19:40:16
date_modified: 2020-07-05T19:40:16
id: 20200705194016
link: 
local_archive: 
pinned: false
series: 
tags: [disk-usage, du, bash, linux]
title: File Space Usage with du
type: tech-note
---

```sh
# Show disk usage.
du --human-readable --max-depth=1

# Show and then sort disk usage.
du --human-readable --max-depth=1 | sort -n
```