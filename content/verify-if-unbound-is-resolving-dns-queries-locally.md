---
alias: verify-if-unbound-is-resolving-dns-queries-locally
archive_links: 
category: network
classification: public
date: 2023-11-03 21:43:53
date_modified: 2023-11-03 21:43:53
id: 20231103214353
link: https://old.reddit.com/r/pihole/comments/etp9vm/how_do_i_verify_if_unbound_is_working/
local_archive: attachments/archive/20231103214353.html
pinned: false
series: 
tags:
  - unbound
  - dns
  - recursive
  - resolve
title: Verify if Unbound is Resolving DNS Queries Locally
type: tech-note
uuid: 7759706c-6fd9-4353-8ff4-b38c1fef46dc
---

I needed to verify that my Unbound DNS server (which is, as of a few weeks ago now running as a service on my OpenWRT router as opposed to a Raspberry Pi) was actually resolving it's own queries and not passing them off to Google or Cloudflare. 

Turns out it's simply a case of running a DNS Leak Test. I used the one [here](https://dnsleaktest.com).

If Unbound is working and resolving locally then you should see your ISP provided IP address.

![](attachments/20231103214353_1.png)
