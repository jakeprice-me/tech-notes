---
aliases:
  - terminal-mouse-scroll-escape-codes
category: cli
classification: public
date: 2020-11-14T15:58:33
date_modified: 2020-11-14T15:58:33
draft: false
id: 20201114155833
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [mouse, scrolling, escape, terminal, shell]
title: Mouse Scroll Escape Codes in Terminal
type: tech-note
---

Very rarely I lose the ability to scroll in a terminal window, and when I try, the escape code `65;70;7M` is printed constantly instead.

There's a quick way to fix this, and that's to simply run `reset` to reset the terminal window, and you'll be back to normal.

More can be read here: [Scrolling is disabled all of a sudden in terminal - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/259922/scrolling-is-disabled-all-of-a-sudden-in-terminal)

