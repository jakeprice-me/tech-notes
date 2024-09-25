---
aliases:
  - journald-cheatsheet
archive_links: 
category: cli
classification: public
date: 2022-08-09T16:31:52
date_modified: 2022-08-09T16:31:52
draft: false
id: 20220809163152
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [journald, log, follow]
title: journald Cheatsheet
type: tech-note
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

