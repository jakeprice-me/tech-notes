---
aliases:
  - anker-soundcore-mini-2-bluetooth-volume-control-on-windows-10
category: hardware
classification: public
date: 2023-09-01T21:14:06
date_modified: 2024-09-23T16:50:21
draft: false
id: 20230901211406
image: 
links:
  - https://community.anker.com/t/cant-change-volume-via-windows/66148
local_archive_links:
  - attachments/20230901211406.html
pinned: false
print: false
series: 
tags:
  - anker
  - bluetooth
  - volume
  - windows
  - registry
title: Anker Soundcore Mini 2 Bluetooth Volume Control on Windows 10
type: tech-note
---

When connecting an Anker Soundcore Mini 2 to a Windows 10 device the volume slider on Windows has no effect.

To fix the issue, in Registry Editor change the below value to `1` and restart the device.

```
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\Bluetooth\Audio\AVRCP\CT\DisableAbsoluteVolume
```

