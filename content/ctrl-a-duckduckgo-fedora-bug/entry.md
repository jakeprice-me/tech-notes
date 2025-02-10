---
aliases:
  - ctrl-a-duckduckgo-fedora-bug
category: fedora
classification: public
date: 2020-03-26T19:04:25
date_modified: 2020-03-26T19:04:25
draft: false
id: 20200326190425
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - duckduckgo
  - fedora
  - keyboard
  - shortcut
title: Ctrl-A and DuckDuckGo Fedora Bug
type: tech-note
---

When trying to "select all" using `Ctrl` + `A` on [DuckDuckGo](https://duckduckgo.com), the whole page is selected instead of the contents of the search input field.

It's caused by having `Pointer Location` turned on in GNOME:

> It seems `/usr/libexec/gsd-locate-pointer`, when invoked under fvwm without session
> manager, will enable "show pointer location when pressing Ctrl key"
> even when the underlying value of the dconf/gsettings key is false.
> This interferes duckduckgo's search box, making key shortcuts with Ctrl
> prefix (e.g. Ctrl+C for copy) unusable. The issue is gone after we stop invoking this gsd plugin. 
>
> — https://www.reddit.com/r/duckduckgo/comments/a4s35t/cannot_use_ctrl_prefix_key_shortcuts_in/