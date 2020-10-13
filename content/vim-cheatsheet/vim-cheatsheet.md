---
aliases:
  - vim-cheatsheet
archive_links: 
category: vim
classification: public
date: 2020-10-13T12:53:36
date_modified: 2020-10-13T12:53:36
draft: false
id: 20201013125336
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [vim, cheatsheet, keys]
title: Vim Cheatsheet
type: tech-note
---

Here's a list of shortcuts for Vim that I might not always remember.

```text
:g!/^\s*"/d                 Delete all lines that do not contain a pattern
:g/^\s*$/d                  Delete all lines that are empty of contain only whitespace
:g/profile/d                Delete all lines containing profile
:set background=dark		Set syntax color for dark background
:set syntax=json            Set syntax highlighting
:sort u                     Sort selection, removing duplicates
:v/^\s*"/d                  You can use :v instead of :g!
:v/error\|warn\|fail/d      Delete all lines except
:w !sudo tee "%"            Override read-only file.
"*p							Paste from system register
"*y                         Yank to system register
"+p							Paste from system register
"+y                         Yank to system register
$A                          In visual block mode, this will append to all lines
gj                          Move down within a long, wrapped string
gk                          Move up within a long, wrapped, string
vim -d <file1> <file2>     Diff between two files with a good interface to edit them into line.
zH                          Move view to the left.
zL                          Move view to the right.
```

### Insert Literal Tab

While in insert mode or command mode (the : prompt at the bottom of the editor), type CTRL + V then TAB.

Using CTRL + V signals Vim that it should take the next character literally. Even in insert mode.