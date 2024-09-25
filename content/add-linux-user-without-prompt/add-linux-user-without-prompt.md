---
aliases:
  - add-linux-user-without-prompt
archive_links: 
category: linux
classification: public
date: 2023-01-07T20:41:07
date_modified: 2023-01-07T20:41:07
draft: false
id: 20230107204107
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [linux, user, useradd, mkpasswd]
title: Add Linux User without Prompt
type: tech-note
---

```sh
# Create Password (Escape $ with \$ as per https://askubuntu.com/a/982857/911046):
mkpasswd -m sha-512 | sed 's/\$/\\$/g'

# Create user with password:
useradd --create-home --password \$6\$ob93e.m1abmoZRB.\$ad4gujCIwkv8khaT3VeHsR9HJ4QC3J7jUpQO/Z/hIn0b.xHfG5SD8BmS2LmrWsicz3eIHJ.7v..XvajRapSFT0 --shell /bin/bash --groups sudo admin
```

