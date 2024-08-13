---
aliases:
  - tcpdump-cheatsheet
archive_links: 
category: network
classification: public
date: 2024-08-13T09:43:44
date_modified: 2024-08-13T09:43:44
draft: false
id: 20240813094344
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - tcpdump
  - network
  - packet
  - router
  - openwrt
  - trace
  - host
title: tcpdump Cheatsheet
type: tech-note
---

Running `tcpdump` on your router is fantastic, because you can see any traffic going to/from any device on your network.

```sh
# View packets on 10.19.90.71, excluding if they are to/from 10.19.90.32:
tcpdump -i any src host 10.19.90.71 and not host 10.19.90.32
```