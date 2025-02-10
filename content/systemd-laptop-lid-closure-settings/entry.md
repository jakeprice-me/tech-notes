---
aliases:
  - systemd-laptop-lid-closure-settings
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
  - attachments/systemd-laptop-lid-closure-settings.html
pinned: false
print: false
series: 
tags:
  - laptop
  - lid
  - monitor
  - power
  - screen
  - sleep
  - suspend
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