---
aliases:
  - restart-kde-plasma-shell
category: cli
classification: public
date: 2021-07-03T09:37:45
date_modified: 2021-07-03T09:37:45
draft: false
id: 20210703093745
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - kde
  - plasma
title: Restart KDE Plasma
type: tech-note
---

```sh
# For KDE > 5.10
kquitapp5 plasmashell || killall plasmashell && kstart5 plasmashell
```

> Remarks:
> 1. If you are not sure which KDE version your run, kinfocenter --version will tell you.
> 2. you can skip the `kquitapp5 plasmashell ||` part if you don't want to be stuck in the timeout when plasmashell is not responding.

Original Source: [kwin - Can I restart the KDE Plasma Desktop without logging out? - Ask Ubuntu](https://askubuntu.com/questions/481329/can-i-restart-the-kde-plasma-desktop-without-logging-out)