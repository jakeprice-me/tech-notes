---
aliases:
  - connect-to-an-openvpn-tunnel-using-the-cli
category: openvpn
classification: public
date: 2019-09-14T21:34:52
date_modified: 2019-09-14T21:34:52
draft: false
id: 20190914213452
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - openvpn
  - ubuntu
title: Connect to an OpenVPN Tunnel Using the CLI
type: tech-note
---

Use an OpenVPN configuration file to connect to an OpenVPN tunnel.

``` sh
$ sudo openvpn --config <path-to-openvpn-config-file>
```

The `sudo` is important, otherwise it may fail to connect.