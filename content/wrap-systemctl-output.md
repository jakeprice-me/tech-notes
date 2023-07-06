---
alias: wrap-systemctl-output
category: cli
classification: public
date: 2022-10-25 15:10:42
date_modified: 2022-10-25 15:10:42
id: 20221025151042
link: 
link_archive: 
pinned: false
series: 
tags: [systemctl, systemd, wrap, log]
title: Wrap systemctl output
type: tech-note
uuid: 2895f11b-c9ff-412b-b223-18c775ed515a
---

If you're checking the logs of a systemd service, and they are going off the screen, although you can use the arrow keys to view the rest of the line, you can also just stop it from happening with the below flags.

```sh
$ sudo systemctl status <service> --full --no-pager
```