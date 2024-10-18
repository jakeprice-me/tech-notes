---
aliases:
  - retrieve-nameservers-for-hostname
category: cli
classification: public
date: 2019-03-05T09:44:09
date_modified: 2019-03-05T09:44:09
draft: false
id: 20190305094409
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [nameserver, dns, hostname, domain]
title: Retrieve Nameservers for Hostname
type: tech-note
---

Return the nameservers for a hostname.

```sh
$ host -t ns domain.com
```

For other records replace `ns` with one of the following.

```sh
a       ip address
mx      mail servers
ns      name servers
txt     txt record
cname   cname record
soa     soa record
any     all details
```

