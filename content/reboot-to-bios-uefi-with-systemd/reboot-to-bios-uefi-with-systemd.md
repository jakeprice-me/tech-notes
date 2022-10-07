---
aliases:
  - reboot-to-bios-uefi-with-systemd
archive_links: 
category: systemd
classification: public
date: 2022-10-07T21:33:34
date_modified: 2022-10-07T21:33:34
draft: false
id: 20221007213334
image: 
links:
  - https://www.freedesktop.org/software/systemd/man/systemctl.html#--firmware-setup
local_archive_links: 
pinned: false
print: false
series: 
tags: [systemd, systemctl, reboot, restart, bios, uefi, firmware]
title: Reboot to BIOS/UEFI with systemd
type: tech-note
---

Reboot to your device's BIOS/UEFI with systemd, by using the `systemctl` command.

```sh
$ systemctl reboot --firmware-setup
```