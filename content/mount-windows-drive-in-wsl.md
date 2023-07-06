---
alias: mount-windows-drive-in-wsl
category: windows
classification: public
date: 2021-07-21 10:39:17
date_modified: 2021-07-21 10:39:17
id: 20210721103917
link: https://www.public-health.uiowa.edu/it/support/kb48568/
link_archive: 
pinned: false
series: 
tags: [wsl, mount, windows, fstab]
title: Mount Windows Drive in WSL
type: tech-note
uuid: 45f649ee-cd99-4fa9-9c54-a1050babe912
---

> ## Mount Drives in a Persistent Manner
> 
> 1.  Ensure the folder exists for the mount target (e.g. `/mnt/m`)
> 2.  Open `/etc/fstab` and add a line such as the following:  
> 
> ```sh
> M: /mnt/m drvfs defaults 0 0
> ```
> 3.  Mount the drives in `/etc/fstab` with `sudo mount -a`
> 
> - [How to Mount Windows Network Drives in WSL - University of Iowa College of Public Health](https://www.public-health.uiowa.edu/it/support/kb48568/)