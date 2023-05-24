---
alias: retrieve-nameservers-for-hostname
category: cli
classification: public
date: 2019-03-05 09:44:09
date_modified: null
id: 20190305094409
pinned: false
tags:
- nameserver
- dns
- hostname
- domain
title: Retrieve Nameservers for Hostname
type: tech-note
uuid: ec9eff1d-18e0-4560-a0c3-418a77915f73
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