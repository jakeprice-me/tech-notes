---
aliases:
  - install-blink1-tool-on-raspberry-pi
archive_links: 
category: raspberry-pi
classification: public
date: 2024-09-11T08:54:29
date_modified: 2024-09-11T08:54:29
draft: false
id: 20240911085429
image: 
links:
  - https://github.com/todbot/blink1-tool
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - blink1
  - thingm
  - raspberry-pi
  - raspberry-pi-os
title: Install blink1-tool on Raspberry Pi
type: tech-note
---

Download `blink1-tool` from GitHub:

```sh
wget https://github.com/todbot/blink1-tool/releases/download/v2.3.0/blink1-tool-v2.3.0-linux-aarch64.zip
unzip blink1-tool-v2.3.0-linux-aarch64.zip
```

Create a file called `51-blink1.rules` and paste the below rules into it:

```
# Copy this udev with "sudo cp 51-blink1.rules /etc/udev/rules.d/"
# When done, do "sudo udevadm control --reload && sudo udevadm trigger"
# Edit it to suit your type of Linux. It's currently set up for modern Ubuntu
ATTRS{idVendor}=="27b8", ATTRS{idProduct}=="01ed", MODE:="666", GROUP="plugdev"
```

Then run the below commands:

```sh
sudo cp 51-blink1.rules /etc/udev/rules.d/51-blink1.rules
sudo udevadm control --reload
sudo udevadm trigger
```

You can now run `blink1-tool` without using `sudo`:

```sh
./blink1-tool --on
```
