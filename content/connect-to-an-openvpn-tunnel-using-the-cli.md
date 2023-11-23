---
aliases:
  - connect-to-an-openvpn-tunnel-using-the-cli
archive_links: 
category: openvpn
classification: public
date: 2019-09-14 21:34:52
date_modified: 2019-09-14 21:34:52
id: 20190914213452
link: 
local_archive: 
pinned: false
series: 
tags: [openvpn, ubuntu]
title: Connect to an OpenVPN Tunnel Using the CLI
type: tech-note
---

Use an OpenVPN configuration file to connect to an OpenVPN tunnel.

``` sh
$ sudo openvpn --config <path-to-openvpn-config-file>
```

The `sudo` is important, otherwise it may fail to connect.