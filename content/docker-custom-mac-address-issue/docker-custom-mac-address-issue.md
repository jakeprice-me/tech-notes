---
aliases:
  - docker-custom-mac-address-issue
archive_links: 
category: docker
classification: public
date: 2021-12-10T21:01:16
date_modified: 2021-12-10T21:01:16
draft: false
id: 20211210210116
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [docker, raspberry-pi, mac, range]
title: Docker cannot start service app
type: tech-note
---

Docker on Raspberry Pi - I manually set MAC's but I get the below error.

```sh
docker-compose up
Starting ppn-int-gb1-co-pihole-01 ... error

ERROR: for ppn-int-gb1-co-pihole-01  Cannot start service app: OCI runtime create failed: container_linux.go:380: starting container process caused: process_linux.go:545: container init ca
used: Running hook #0:: error running hook: exit status 1, stdout: , stderr: time="2021-12-10T20:59:08Z" level=fatal msg="failed to add interface vetha3df5ce to sandbox: error setting inte
rface \"vetha3df5ce\" MAC to \"07:51:9a:4d:8f:30\": cannot assign requested address": unknown

ERROR: for app  Cannot start service app: OCI runtime create failed: container_linux.go:380: starting container process caused: process_linux.go:545: container init caused: Running hook #0
:: error running hook: exit status 1, stdout: , stderr: time="2021-12-10T20:59:08Z" level=fatal msg="failed to add interface vetha3df5ce to sandbox: error setting interface \"vetha3df5ce\"
 MAC to \"07:51:9a:4d:8f:30\": cannot assign requested address": unknown
ERROR: Encountered errors while bringing up the project.
```

It's because I must user this specific MAC range: `02:42:0a:13:5a:**`. Although it seems to be that it's `02:42` that's the important part. I didn't document this very well at the time, and I'm struggling to find any documentation on it though, so I can't quite remember how I came across it.