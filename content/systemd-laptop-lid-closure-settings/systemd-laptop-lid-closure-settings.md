---
aliases:
  - systemd-laptop-lid-closure-settings
archive_links: 
category: systemd
classification: public
date: 2022-02-12T16:43:24
date_modified: 2022-02-12T16:43:24
draft: false
id: 20220212164324
image: 
links:
  - https://unix.stackexchange.com/a/583059/331627
local_archive_links: 
pinned: false
print: false
series: 
tags: [screen, laptop, lid, sleep, suspend, monitor, power]
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