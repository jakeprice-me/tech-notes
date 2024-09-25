---
aliases:
  - linux-date-command-cheatsheet
archive_links: 
category: cli
classification: public
date: 2020-10-13T19:02:22
date_modified: 2020-10-13T19:02:22
draft: false
id: 20201013190222
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [date, linux, shell]
title: Linux Date Command
type: tech-note
---

## Commands

```sh
date --set="23:59:58"                       # Set the system time.
date --set="2020-10-17"                     # Set the system date.
date --date=@1593966863                     # Convert from specifed Epoch time.
date --date=@1593964977 +"%Y%m%d%H%M%S"     # Convert from specified Epoch time to specific format.
date +%s -d "Jan 1, 1980 00:00:01"          # Convert from human readable to Epoch.
```

## Functions

### Print out Concurrent Date's

I use this for my plain-text calendar. Update the `START` and `END` date variables, and then you have a list of dates you can use.

```sh
#!/bin/bash
START="2021-01-01"
for i in {1..365}; do
    # custom format using +
    date '+%Y-%m-%d %a' -d "$START +$i days"
done
```

