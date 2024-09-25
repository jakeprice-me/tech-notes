---
aliases:
  - increase-memory-vcpu-virsh
archive_links: 
category: libvirt
classification: public
date: 2022-02-21T22:50:05
date_modified: 2022-02-21T22:50:05
draft: false
id: 20220221225005
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - virsh
  - virtual-machine
  - domain
  - memory
  - ram
  - vcpu
  - maximum
title: Increase Memory & Virtual CPU on Virtual Machine
type: tech-note
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

