---
aliases:
  - install-hp-printer-fedora
category: fedora
classification: public
date: 2022-05-15T22:15:00
date_modified: 2022-05-15T22:15:00
draft: false
id: 20220515221500
image: 
links:
  - https://www.cyberciti.biz/faq/how-to-install-networked-hp-printer-and-scanner-on-fedora-linux/
local_archive_links:
  - attachments/20220515221500.html
pinned: false
print: false
series: 
tags:
  - hp
  - printer
  - fedora
  - hplip
title: Install HP Printer on Fedora
type: tech-note
---

The below article provided some pointers with some recent HP Printer issues I had on Fedora 36. 

What got it working was running `hp-setup <ip-address-of-printer>` after making sure I had installed `sudo dnf install hplip hplip-common hplip-libs libsane-hpaio hplip-gui`.

