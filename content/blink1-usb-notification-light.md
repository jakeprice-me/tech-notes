---
alias: blink1-usb-notification-light
category: blink
classification: public
date: 2022-02-04 20:29:34
date_modified: 2022-02-04 20:29:34
id: 20220204202934
link: https://github.com/todbot/blink1-python
pinned: false
series: 
tags: [blink1, usb, notification]
title: blink(1) USB Notification Light
type: tech-note
uuid: e230f402-d4ad-4a68-87b5-6f6bd60479ad
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