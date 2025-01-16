---
aliases:
  - mount-windows-drive-in-wsl
category: windows
classification: public
date: 2021-07-21T10:39:17
date_modified: 2024-09-23T22:01:34
draft: false
id: 20210721103917
image: 
links:
  - https://www.public-health.uiowa.edu/it/support/kb48568/
local_archive_links:
  - attachments/20210721103917.html
pinned: false
print: false
series: 
tags:
  - wsl
  - mount
  - windows
  - fstab
title: Mount Windows Drive in WSL
type: tech-note
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

