---
alias: systemd-laptop-lid-closure-settings
category: systemd
classification: public
date: 2022-02-12 16:43:24
date_modified: null
id: 20220212164324
link: https://unix.stackexchange.com/a/583059/331627
pinned: false
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
uuid: 6293d7b0-f206-49ad-8b40-ed52c6a3493f
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