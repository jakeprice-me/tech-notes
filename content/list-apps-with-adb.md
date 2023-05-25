---
alias: list-apps-with-adb
category: android
classification: public
date: 2020-03-29 22:07:01
date_modified: null
id: 20200329220701
pinned: false
tags: [adb, android, apps, search, find, filter]
title: List Apps with ADB
type: tech-note
uuid: 31f7f32d-e368-46ed-b481-bde887db8c13
---

```sh
# List Android apps and the app name:
adb shell pm list packages -f -s | sort

# Search for and list:
adb shell "pm list packages -f tplink"
```