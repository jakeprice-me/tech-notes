---
aliases:
  - video-frozen-but-audio-playing-whilst-scrubbing-on-firefox
category: firefox
classification: public
date: 2025-04-01T20:22:57
date_modified: 2025-04-01T20:22:57
draft: false
id: 20250401202257
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - firefox
  - fedora
  - ffmpeg
title: Video Frozen but Audio Playing Whilst Scrubbing on Firefox
type: tech-note
---

On Fedora 41, running Firefox version 136, I had regularly been having an issue where, when scrubbing through a video on Firefox the video would freeze but the audio and progress bar would continue.

It seems to be caused by Fedora having ffmpeg-free installed by default. 

When I replaced ffmpeg-free with ffmpeg from [RPM Fusion](https://rpmfusion.org/) the issues stopped.

```sh
sudo dnf remove ffmpeg-free
sudo dnf install ffmpeg --allowerasing
```

I'm not sure when this became an issue, or whether it's only an issue with Firefox 136, but this was the first time I had done a fresh install for years.
