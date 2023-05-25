---
alias: keep-ssh-connection-alive
category: cli
classification: public
date: 2020-07-01 21:26:41
date_modified: null
id: 20200701212641
link: null
pinned: false
series: null
tags: [ssh, connection, linux]
title: Keep SSH Connection Alive
type: tech-note
uuid: 114c1d46-2549-4ee5-b6f5-9e27549d9bc1
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