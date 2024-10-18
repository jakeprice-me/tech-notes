---
aliases:
  - set-static-ip-address-debian
category: network
classification: public
date: 2020-12-10T10:17:15
date_modified: 2020-12-10T10:17:15
draft: false
id: 20201210101715
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [debian, networking, ip, linux]
title: Set Static IP Address on Debian
type: tech-note
---

> [!danger]
> There's a not insignificant chance you'll get kicked out of the server, so you should be physically present to reboot it to get back in. Don't do it on a server you can't access.

```sh
# File: /etc/network/interfaces
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug eno1
#iface eno1 inet dhcp
```

```sh
# File: /etc/network/interfaces.d/eno1

iface eno1 inet static
        address 10.0.0.226
        netmask 255.255.255.255
        gateway 10.0.0.1
```

