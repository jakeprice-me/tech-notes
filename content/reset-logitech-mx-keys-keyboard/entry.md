---
aliases:
  - reset-logitech-mx-keys-keyboard
category: hardware
classification: public
date: 2023-06-07T15:03:44
date_modified: 2023-06-07T15:03:44
draft: false
id: 20230607150346
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [logitech, mx, keyboard, bolt, macos, factory-reset]
title: Reset Logitech MX Keys Keyboard
type: tech-note
---

I had an issue where the volume down and volume up keys on my Logitech MX Keys keyboard were _both_ increasing the volume on macOS. 

I came across the below steps to reset it, which fixed the issue. 

1. Turn the keyboard off and then back on.
2. Press the following key combinations: Esc + `O`, then Esc + `O` then Esc + `B`
3. The device switching lights will blink rapidly.
4. Turn the keyboard off and on again.

Device Switch 1 will now blink rapidly, which means it's ready to be paired again.

> [!tip]
> On macOS at least I had to manually remove the keyboard from Logi Bolt before I could actually re-pair it with my Unifying Receiver.
