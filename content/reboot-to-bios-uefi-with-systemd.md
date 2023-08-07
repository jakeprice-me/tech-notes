---
alias: reboot-to-bios-uefi-with-systemd
archive_link: []
category: systemd
classification: public
date: 2022-10-07 21:33:34
date_modified: 2022-10-07 21:33:34
id: 20221007213334
link: https://www.freedesktop.org/software/systemd/man/systemctl.html#--firmware-setup
local_archive: 
pinned: false
series: 
tags: [systemd, systemctl, reboot, restart, bios, uefi, firmware]
title: Reboot to BIOS/UEFI with systemd
type: tech-note
uuid: e7a31ab1-62d6-4f58-8285-2968d4c51bfe
---

Reboot to your device's BIOS/UEFI with systemd, by using the `systemctl` command.

```sh
$ systemctl reboot --firmware-setup
```