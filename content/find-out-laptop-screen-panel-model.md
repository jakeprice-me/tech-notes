---
alias: find-out-laptop-screen-panel-model
category: linux
classification: public
date: 2022-01-19 20:51:59
date_modified: 2022-01-19 20:51:59
id: 20220119205159
link: 
link_archive: 
pinned: false
series: 
tags: [laptop, lcd, panel, edid, edp]
title: Find out Laptop Screen Panel Model
type: tech-note
uuid: 3bf4ba87-4adf-4afb-8988-d82d6a070f89
---

```sh
sudo dnf install edid-decode
cat /sys/class/drm/card0-eDP-1/edid | edid-decode
```