---
aliases:
  - restart-display-manager
archive_links: 
category: cli
classification: public
date: 2022-10-14T19:23:44
date_modified: 2022-10-14T19:23:44
draft: false
id: 20221014192344
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [fedora, linux, monitor, multiple-monitor, screen, displayport, usb-c, dock]
title: Restart Display Manager
type: tech-note
---

When I connect my EliteBook to my Dock and Daisy Chain USB-C cable, sometimes there are issues with the screens coming on.

Historically I've just tended to restart, but you don't need to, you can just restart the display manager, as below.

```sh
$ sudo systemctl restart display-manager
```

This will log you out, so it's almost as inconvenient as a restart, but it tends to fix any issues I'm having.

