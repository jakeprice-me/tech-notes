---
aliases:
  - docker-breaks-kvm-networking
archive_links:
  - https://web.archive.org/web/20240917131756/https://wiki.archlinux.org/title/Docker
category: network
classification: public
date: 2023-01-23T16:28:35
date_modified: 2024-09-23T19:01:47
draft: false
id: 20230123162835
image: 
links:
  - https://wiki.archlinux.org/title/Docker#Starting_Docker_breaks_KVM_bridged_networking
local_archive_links:
  - attachments/20230123162835.html
pinned: false
print: false
series: 
tags:
  - docker
  - kvm
  - bridge
  - network
title: Fix for Docker Breaking KVM Networking
type: tech-note
---

Detailed on the ArchWiki below is a solution to an issue I was having when I tried to use a network bridge `br0` _alongside_ Docker on my server.

The solution that I thought worked initially was to add the below to `/etc/docker/daemon.json`. This got the bridge working for virtual machines, but broke Docker container external connectivity (containers couldn't access the internet).

```json
{
  "bridge": "br0"
}
```

In the end I needed to run the `iptables` rule _instead_, and that got things working for both Docker and the Virtual Machines.

```sh
iptables -I FORWARD -i br0 -o br0 -j ACCEPT
```