---
aliases:
  - specify-dns-resolver-for-dig-query
archive_links: 
category: network
classification: public
date: 2023-11-03T21:38:16
date_modified: 2023-11-03T21:38:16
draft: false
id: 20231103213816
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [dig, dns, resolver, unbound]
title: Specify DNS Resolver for dig Query
type: tech-note
---

I probably did know this, but had forgotten it, and it just came in handy whilst trying to confirm some stuff with Unbound.

When using `dig` you can specify the DNS resolver:

```sh
dig google.co.uk @10.19.90.5
dig google.co.uk @10.19.90.1
dig google.co.uk @1.1.1.1
```

