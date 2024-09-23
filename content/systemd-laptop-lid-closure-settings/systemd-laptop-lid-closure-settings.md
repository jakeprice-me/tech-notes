---
aliases:
  - systemd-laptop-lid-closure-settings
archive_links:
  - https://web.archive.org/web/20240923202131/https://unix.stackexchange.com/questions/307497/gnome-disable-sleep-on-lid-close/583059
category: systemd
classification: public
date: 2022-02-12T16:43:24
date_modified: 2024-09-23T21:23:13
draft: false
id: 20220212164324
image: 
links:
  - https://unix.stackexchange.com/a/583059/331627
local_archive_links:
  - attachments/20220212164324.html
pinned: false
print: false
series: 
tags:
  - screen
  - laptop
  - lid
  - sleep
  - suspend
  - monitor
  - power
title: Laptop Lid Closure Settings on Linux
type: tech-note
---

```sh
# Don't go to sleep if lid closed and monitor connected:
sed --in-place .backup 's/#HandleLidSwitchDocked=ignore/HandleLidSwitchDocked=ignore/' /etc/systemd/logind.conf

$ /etc/systemd/logind.conf
HandleLidSwitch=suspend                # suspend when on battery
HandleLidSwitchExternalPower=ignore    # inhibit suspend when on AC 
HandleLidSwitchDocked=ignore           # inhibit suspend when on external monitor

$ reboot
# ↓ or ↑
$ sudo systemctl restart systemd-logind  # will kill current X/Wayland session
```