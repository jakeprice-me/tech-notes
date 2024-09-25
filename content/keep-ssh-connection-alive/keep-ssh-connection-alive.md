---
aliases:
  - keep-ssh-connection-alive
archive_links: 
category: cli
classification: public
date: 2020-07-01T21:26:41
date_modified: 2020-07-01T21:26:41
draft: false
id: 20200701212641
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [ssh, connection, linux]
title: Keep SSH Connection Alive
type: tech-note
---

The option `-o ServerAliveInterval=60` tells the SSH agent to keep sending "pings" to keep the connection alive.

Example below.

```sh
ssh -v -o ServerAliveInterval=60 myname@myhost.com
```

Alternatively you can add it the your ssh config file for all hosts:

```sh
Host *
    ServerAliveInterval 60
```

