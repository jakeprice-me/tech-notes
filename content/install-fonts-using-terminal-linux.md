---
alias: install-fonts-using-terminal-linux
archive_link: []
category: linux
classification: public
date: 2021-01-01 15:03:58
date_modified: 2021-01-01 15:03:58
id: 20210101150358
link: 
local_archive: 
pinned: false
series: 
tags: [linux, fonts]
title: Install Fonts on Linux
type: tech-note
uuid: 7749921f-4855-4c8c-aca2-248aa4ad0f18
---

Install fonts using the Terminal on Linux.

Using _Inconsolata_ as an example.

```sh
wget https://github.com/googlefonts/Inconsolata/releases/download/v3.000/fonts_ttf.zip --output-document=/tmp/inconsolata_v3.zip
sudo mkdir --parents /usr/local/share/fonts
sudo cp /tmp/fonts/ttf/Inconsolata-*.ttf /usr/local/share/fonts/
sudo fc-cache /usr/local/share/fonts/
```

!!! tip
	You can check `/etc/fonts/fonts.conf` for a list of directories that contain fonts.