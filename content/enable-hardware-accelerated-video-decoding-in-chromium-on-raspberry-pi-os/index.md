---
aliases:
  - enable-hardware-accelerated-video-decoding-in-chromium-on-raspberry-pi-os
category: raspberry-pi
classification: public
date: 2023-07-11T15:13:59
date_modified: 2023-07-11T15:13:59
draft: false
id: 20230711151359
image: 
links:
  - https://lemariva.com/blog/2020/08/raspberry-pi-4-video-acceleration-decode-chromium
local_archive_links:
  - attachments/20230711151359.html
pinned: false
print: false
series: 
tags:
  - video
  - decode
  - raspberry-pi
  - chromium
  - home-assistant
title: Enable Hardware Accelerated Video Decoding In Chromium On Raspberry Pi OS
type: tech-note
---

I have a Raspberry Pi 4B I use to display a Home Assistant dashboard, it includes cameras from around my house as well. After a fresh install of my RPI these camera streams don't stream, until I install the below packages.

```
libgles2-mesa
libgles2-mesa-dev
xorg-dev
```

Video decoding seems to be enabled on Chromium by default now, but I also enable these flags which I found in an article [here](https://lemariva.com/blog/2020/08/raspberry-pi-4-video-acceleration-decode-chromium) - although I'm relatively certain you no longer need to do this! I just haven't gotten round to testing that.

```
ignore-gpu-blocklist
enable-gpu-rasterization
```

