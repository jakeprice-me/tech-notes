---
aliases:
  - find-out-laptop-screen-panel-model
archive_links: 
category: linux
classification: public
date: 2022-01-19T20:51:59
date_modified: 2022-01-19T20:51:59
draft: false
id: 20220119205159
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [laptop, lcd, panel, edid, edp]
title: Find out Laptop Screen Panel Model
type: tech-note
---

```sh
sudo dnf install edid-decode
cat /sys/class/drm/card0-eDP-1/edid | edid-decode
```

