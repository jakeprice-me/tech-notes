---
alias: restart-display-manager
archive_link: []
category: cli
classification: public
date: 2022-10-14 19:23:44
date_modified: 2022-10-14 19:23:44
id: 20221014192344
link: 
local_archive: 
pinned: false
series: 
tags: [fedora, linux, monitor, multiple-monitor, screen, displayport, usb-c, dock]
title: Restart Display Manager
type: tech-note
uuid: b043e38d-2273-448f-9dd0-270b6aeaccd7
---

When I connect my EliteBook to my Dock and Daisy Chain USB-C cable, sometimes there are issues with the screens coming on.

Historically I've just tended to restart, but you don't need to, you can just restart the display manager, as below.

```sh
$ sudo systemctl restart display-manager
```

This will log you out, so it's almost as inconvenient as a restart, but it tends to fix any issues I'm having.