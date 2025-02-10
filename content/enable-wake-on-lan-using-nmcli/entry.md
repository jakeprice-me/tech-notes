---
aliases:
  - enable-wake-on-lan-using-nmcli
category: network
classification: public
date: 2024-07-11T11:42:37
date_modified: 2024-07-11T11:42:37
draft: false
id: 20240711114237
image: 
links:
  - https://wiki.archlinux.org/title/Wake-on-LAN#NetworkManager
local_archive_links:
  - attachments/enable-wake-on-lan-using-nmcli.html
pinned: false
print: false
series: 
tags:
  - lan
  - network
  - nmcli
  - wake-on-lan
  - wol
title: Enable Wake-on-LAN using NMCLI
type: tech-note
---

It's extremely easy to enable Wake-on-LAN support on Fedora using NMCLI.

The first step is to turn it on/enable it in the BIOS/UEFI/Firmware. That'll be slightly different for everybody, but you want to enable it on your network card.

It's then simply a case of running the below command, against your ethernet interface.

```sh
nmcli connection modify "<ethernet-interface>" 802-3-ethernet.wake-on-lan magic
```

Reboot the machine and then check it's enabled. If you see `magic` you're good.

```sh
$ nmcli connection show "<ethernet-interface>" | grep 802-3-ethernet.wake-on-lan
802-3-ethernet.wake-on-lan:             magic
802-3-ethernet.wake-on-lan-password:    --
```

You can now test it by shutting the machine down, and then sending a Wake-on-LAN packet from another device (I use `wol` - `sudo dnf install wol`).

```sh
wol <mac-address-of-device-to-power-on>
```