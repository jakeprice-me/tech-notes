---
aliases:
  - reboot-to-bios-uefi-with-systemd
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
  - attachments/reboot-to-bios-uefi-with-systemd.html
pinned: false
print: false
series: 
tags:
  - bios
  - firmware
  - reboot
  - restart
  - systemctl
  - systemd
  - uefi
title: Reboot to BIOS/UEFI with systemd
type: tech-note
---

Reboot to your device's BIOS/UEFI with systemd, by using the `systemctl` command.

```sh
$ systemctl reboot --firmware-setup
```