---
aliases:
  - openwrt-cheatsheet
category: network
classification: public
date: 2023-11-03T21:34:52
date_modified: 2023-11-03T21:34:52
draft: false
id: 20231103213452
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - command-line
  - openwrt
  - router
title: OpenWRT Cheatsheet
type: tech-note
---

```sh
# Follow unbound logs:
logread -f | grep unbound

# View DHCP leases:
vim /tmp/dhcp.leases

# Restart DHCP:
service dnsmasq restart
```