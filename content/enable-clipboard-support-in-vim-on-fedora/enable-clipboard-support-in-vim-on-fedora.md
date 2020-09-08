---
aliases:
  - enable-clipboard-support-in-vim-on-fedora
archive_links: 
category: vim
classification: public
date: 2020-09-08T20:12:31
date_modified: 2020-09-08T20:12:31
draft: false
id: 20200908201231
image: 
links:
  - https://vi.stackexchange.com/a/2065
local_archive_links: 
pinned: false
print: false
series: 
tags: [fedora, vim, x11, clipboard, register]
title: Enable Vim +clipboard Support On Fedora
type: tech-note
---

> So, installing vim-enhanced and vim-X11 is enough, but is not at the same time. To enable the system functions like +clipboard, you moreover need to use the `vimx` executable rather than vim or vi (even though they are probably identical, the name changes the behaviour).
> 
> One way how to do that permanently is by adding aliases in your .bashrc file:
> 
> ```sh
> alias vi='vimx'
> alias vim='vimx'
> ```
> 
> The complete list of features that get enabled this way is: +balloon_eval, +browse, +clientserver, +clipboard, +dnd, +mouseshape, +toolbar, +X11, +xim, +xsmp_interact, +xterm_clipboard, +xpm.
> 
> However, some of them are probably irrelevant for the terminal version of vimx and only do something for GVim.
>
> — [How do I get +clipboard support in Fedora 20?](https://vi.stackexchange.com/a/2065)