---
aliases:
  - wrap-systemctl-output
archive_links: 
category: cli
classification: public
date: 2022-10-25T15:10:42
date_modified: 2022-10-25T15:10:42
draft: false
id: 20221025151042
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [systemctl, systemd, wrap, log]
title: Wrap systemctl output
type: tech-note
---

If you're checking the logs of a systemd service, and they are going off the screen, although you can use the arrow keys to view the rest of the line, you can also just stop it from happening with the below flags.

```sh
$ sudo systemctl status <service> --full --no-pager
```