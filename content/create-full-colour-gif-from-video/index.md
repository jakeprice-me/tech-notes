---
aliases:
  - create-full-colour-gif-from-video
category: video
classification: public
date: 2024-05-17T20:21:59
date_modified: 2024-05-17T20:21:59
draft: false
id: 20240517202159
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - ffmpeg
  - gif
  - mp4
  - webm
  - palette
  - gnome
  - screenclip
title: Create Full Colour GIF from Video
type: tech-note
---

I follow this process when I record a clip of my screen using GNOME's built in screen clipping software.

I find I get the best quality if I generate a colour palette first, as below.

```sh
ffmpeg -i input.mp4 -filter:v "fps=15,scale=640:-1:flags=lanczos,palettegen" palette.png
```

Next, create the GIF and reference the palette. `ffmpeg` options are one of the deep mysteries of the universe, but this usually works well for me.

```sh
ffmpeg -i input.mp4 -i palette.png -filter_complex "fps=15,scale=640:-1:flags=lanczos[x];[x][1:v]paletteuse" -quality:v 3 output.gif
```
