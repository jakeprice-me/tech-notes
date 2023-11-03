---
alias: add-linux-user-without-prompt
archive_links: []
category: linux
classification: public
date: 2023-01-07 20:41:07
date_modified: 2023-01-07 20:41:07
id: 20230107204107
link: 
local_archive: 
pinned: false
series: 
tags: [linux, user, useradd, mkpasswd]
title: Add Linux User without Prompt
type: tech-note
uuid: 8e63ef41-15b9-4cc3-86dc-3b57417d3979
---

```sh
# Create Password (Escape $ with \$ as per https://askubuntu.com/a/982857/911046):
mkpasswd -m sha-512 | sed 's/\$/\\$/g'

# Create user with password:
useradd --create-home --password \$6\$ob93e.m1abmoZRB.\$ad4gujCIwkv8khaT3VeHsR9HJ4QC3J7jUpQO/Z/hIn0b.xHfG5SD8BmS2LmrWsicz3eIHJ.7v..XvajRapSFT0 --shell /bin/bash --groups sudo admin
```