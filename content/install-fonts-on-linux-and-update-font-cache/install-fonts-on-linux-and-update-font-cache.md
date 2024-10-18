---
aliases:
  - install-fonts-on-linux-and-update-font-cache
category: linux
classification: public
date: 2021-01-01T15:03:58
date_modified: 2024-06-13T15:06:11
draft: false
id: 20210101150358
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - linux
  - fonts
  - font-cache
title: Install Fonts on Linux and Update Font Cache
type: tech-note
---

Install fonts using the Terminal on Linux.

Using _Inconsolata_ as an example.

> [!tip]
> You can check `/etc/fonts/fonts.conf` for a list of directories that contain fonts.

```sh
wget https://github.com/googlefonts/Inconsolata/releases/download/v3.000/fonts_ttf.zip --output-document=/tmp/inconsolata_v3.zip
sudo mkdir --parents /usr/local/share/fonts
sudo cp /tmp/fonts/ttf/Inconsolata-*.ttf /usr/local/share/fonts/
sudo fc-cache /usr/local/share/fonts/
```
