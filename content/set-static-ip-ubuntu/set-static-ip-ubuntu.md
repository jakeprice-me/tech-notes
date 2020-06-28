---
aliases:
  - set-static-ip-ubuntu
archive_links: 
category: network
classification: public
date: 2020-06-28T13:02:40
date_modified: 2020-06-28T13:02:40
draft: false
id: 20200628130240
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [static, networking, ubuntu]
title: Set Static IP on Ubuntu 20.04
type: tech-note
---

Create or edit `/etc/netplan/01-netcfg.yaml` and insert the below, replacing the adapter name and IP info if required:

```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: no
      addresses: [10.0.0.2/24]
      gateway4: 10.0.0.1
      nameservers:
        addresses: [1.1.1.1,1.0.0.1]
```

The example above sets a static IP on my Raspberry Pi.

To restart networking, you can then run `sudo netplan apply`.