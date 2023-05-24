---
alias: connect-to-an-openvpn-tunnel-using-the-cli
category: openvpn
classification: public
date: 2019-09-14 21:34:52
date_modified: null
id: 20190914213452
pinned: false
tags:
- openvpn
- ubuntu
title: Connect to an OpenVPN Tunnel Using the CLI
type: tech-note
uuid: f897a427-3bf4-4f96-ad5e-89f5efc2b7e0
---

Use an OpenVPN configuration file to connect to an OpenVPN tunnel.

``` sh
$ sudo openvpn --config <path-to-openvpn-config-file>
```

The `sudo` is important, otherwise it may fail to connect.