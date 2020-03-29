---
aliases:
  - list-apps-with-adb
archive_links: 
category: android
classification: public
date: 2020-03-29T22:07:01
date_modified: 2020-03-29T22:07:01
draft: false
id: 20200329220701
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [adb, android, app, search, find, filter]
title: List Apps with ADB
type: tech-note
---

```sh
# List Android apps and the app name:
adb shell pm list packages -f -s | sort

# Search for and list:
adb shell "pm list packages -f tplink"
```