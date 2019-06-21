---
aliases:
  - update-boot-manager-options
archive_links: 
category: linux
classification: public
date: 2019-06-21T14:59:22
date_modified: 2019-06-21T14:59:22
draft: false
id: 20190621145922
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [bootloader, efiboot]
title: Update Boot Manager Options
type: tech-note
---

When selecting a device to boot an OS from you may see old entries for operating systems that have previously been installed on the drive - especially if you distro hop or have installed Windows before.

You can manage these options in Linux using `efibootmgr`. To view the current list of boot options run:

``` sh
$ efibootmgr
```

That will return something like this:

```text
BootCurrent: 0000
Timeout: 0 seconds
BootOrder: 0000,0005,0002,0006,0001,0003,0004
Boot0000* Fedora
Boot0001  USB NETWORK BOOT:
Boot0002* WDC PC SN720 SDAQNTW-512G-1001-183935806637
Boot0003* Wi-Fi IPV4 Network
Boot0004* Wi-Fi IPV6 Network
Boot0005  USB:
Boot0006  USB NETWORK BOOT:
```

If there's an entry you want to delete, you can delete it as follows, where `--bootnum` is the number at the end of the first column. So `Boot0004` is `4`. Example below.

``` sh
$ efibootmgr --bootnum 4 --delete-bootnum
```