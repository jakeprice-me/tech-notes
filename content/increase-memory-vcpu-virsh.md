---
alias: increase-memory-vcpu-virsh
category: libvirt
classification: public
date: 2022-02-21 22:50:05
date_modified: null
id: 20220221225005
link: null
pinned: false
tags:
- virsh
- vm
- domain
- memory
- ram
- vcpu
- cpu
- max
- maximum
title: Increase Memory & Virtual CPU on Virtual Machine
type: tech-note
uuid: 37ada0cf-74b3-4c04-9648-f5cf8901f46d
---

```sh
# Shutdown domain:
virsh shutdown <domain>

# Increase max memory:
virsh setmaxmem <domain> 4G --config

# Increase memory:
virsh setmem <domain> 4G --config

# ---

# Set max vcpu:
virsh setvcpus --domain <domain> --maximum 2 --config

# Set vcpu:
virsh setvcpus --domain <domain> --count 2 --config

# Restart domain:
virsh start <domain>
```