---
aliases:
  - use-dig-to-get-your-public-ip
category: cli
classification: public
date: 2020-05-30T13:34:52
date_modified: 2024-09-23T22:28:12
draft: false
id: 20200530133452
image: 
links:
  - https://unix.stackexchange.com/questions/22615/how-can-i-get-my-external-ip-address-in-a-shell-script)
local_archive_links:
  - attachments/20200530133452.html
pinned: false
print: false
series: 
tags:
  - dig
  - linux
  - ip
  - dnsutils
title: Use Dig to Get Public IP
type: tech-note
---

Source: [How can I get my external IP address in a shell script?](https://unix.stackexchange.com/questions/22615/how-can-i-get-my-external-ip-address-in-a-shell-script)

A safer and more reliable way than using `curl` to get your public IP is to use `dig` as below:

```sh
# OpenDNS:
dig @resolver1.opendns.com ANY myip.opendns.com +short

# Google:
dig @ns1.google.com TXT o-o.myaddr.l.google.com +short

# Akamai:
dig @ns1-1.akamaitech.net ANY whoami.akamai.net +short
```

Just make sure `dnsutils` is installed if `dig` isn't installed.

