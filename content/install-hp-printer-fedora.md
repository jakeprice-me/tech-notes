---
alias: install-hp-printer-fedora
category: fedora
classification: public
date: 2022-05-15 22:15:00
date_modified: null
id: 20220515221500
link: https://www.cyberciti.biz/faq/how-to-install-networked-hp-printer-and-scanner-on-fedora-linux/
pinned: false
tags:
- hp
- printer
- fedora
- hplib
- hplip
title: Install HP Printer on Fedora
type: tech-note
uuid: 72987850-7ff1-48b5-b326-13c99b90ab73
---

The below article provided some pointers with some recent HP Printer issues I had on Fedora 36. What got it working was running `hp-setup 192.168.2.250` after making sure I had installed `sudo dnf install hplip hplip-common hplip-libs libsane-hpaio hplip-gui`.

![[public-webpage-archive/install-hp-printer-fedora.html.html]]