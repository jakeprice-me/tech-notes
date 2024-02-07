---
aliases:
  - youtube-dl-cheatsheet
archive_links: 
category: cli
classification: public
date: 2022-07-11T13:13:09
date_modified: 2024-01-08T17:09:10
draft: false
id: 20220711131309
link: 
local_archive: 
pinned: false
series: 
tags:
  - youtube-dl
  - youtube
  - download
  - audio
  - video
  - cli
title: YouTube-DL Cheatsheet
type: tech-note
---

```sh
# Download best quality audio:
youtube-dl --extract-audio --format "bestaudio/best" https://www.youtube.com/watch?v=uWusmdmc0to

# Download Best MP3 Audio or something like that:
yt-dlp --format "bestaudio[ext=mp3]/bestaudio/best" --extract-audio --audio-format mp3 --output "%(title)s.%(ext)s" --embed-thumbnail --add-metadata --restrict-filenames "https://www.youtube.com/watch?v=PGkxpiTmL2s"
```