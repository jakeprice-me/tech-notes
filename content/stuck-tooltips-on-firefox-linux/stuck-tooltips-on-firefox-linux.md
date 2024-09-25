---
aliases:
  - stuck-tooltips-on-firefox-linux
archive_links:
  - https://web.archive.org/web/20230528203743/https://bugzilla.mozilla.org/show_bug.cgi?id=1569439
category: firefox
classification: public
date: 2022-12-27T20:42:31
date_modified: 2022-12-27T20:42:31
draft: false
id: 20221227204231
image: 
links:
  - https://bugzilla.mozilla.org/show_bug.cgi?id=1569439
local_archive_links: 
  - attachments/20221227204231.html
pinned: false
print: false
series: 
tags:
  - firefox
  - fedora
  - linux
  - tooltip
  - bug
title: Stuck Tooltips on Firefox Linux
type: tech-note
---

Basically, hover over a link on a page in Firefox and wait for the tooltip to display, then Alt-Tab out of Firefox to another program, and more often than not, the tooltip will remain on the screen. To remove it, you must go back to Firefox, and move the mouse.

As of 2023-11-29 this is still happening for me on Fedora Linux 38, running Gnome 44.5 and Firefox 118.0.2.

As a temporary, if not sometimes inconvenient fix, I've set `browser.chrome.toolbar_tips` to `true` in about:config as per [here](https://bugzilla.mozilla.org/show_bug.cgi?id=1569439#c28)

