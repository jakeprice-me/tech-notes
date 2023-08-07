---
alias: journald-cheatsheet
archive_link: []
category: cli
classification: public
date: 2022-08-09 16:31:52
date_modified: 2022-08-09 16:31:52
id: 20220809163152
link: 
local_archive: 
pinned: false
series: 
tags: [journald, log, follow]
title: journald Cheatsheet
type: tech-note
uuid: ec28bb00-d300-4b1e-af36-8c38cd4b6798
---

```sh
# Follow all logs:
$ sudo journalctl --follow

# Follow logs for a service:
$ sudo journalctl --follow --unit tailscaled

# View logs since date/time:
$ journalctl --since "2022-10-14"
$ journalctl --since "2022-10-14 21:55"
```