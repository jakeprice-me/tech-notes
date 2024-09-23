---
aliases:
  - blink1-usb-notification-light
archive_links:
  - https://web.archive.org/web/20221128193120/https://github.com/todbot/blink1-python
category: blink
classification: public
date: 2022-02-04T20:29:34
date_modified: 2024-09-23T21:26:06
draft: false
id: 20220204202934
image: 
links:
  - https://github.com/todbot/blink1-python
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - blink1
  - usb
  - notification
  - github
title: blink(1) USB Notification Light
type: tech-note
---

## Install & Configure Dependencies

```sh
$ sudo dnf install hidapi libusb1-devel python3-devel python3-pyudev 
$ pip3 install --user blink1
$ echo 'SUBSYSTEM=="usb", ATTRS{idVendor}=="27b8", ATTRS{idProduct}=="01ed", MODE:="666", GROUP="plugdev"' | sudo tee /etc/udev/rules.d/51-blink1.rules
$ sudo udevadm control --reload
$ sudo udevadm trigger
```

## Run Provided Command Line Scripts

```sh
blink1-flash
blink1-shine
```