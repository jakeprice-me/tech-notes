---
aliases:
  - open-files-side-by-side-with-vim
category: vim
classification: public
date: 2022-11-16T17:22:41
date_modified: 2022-11-16T17:22:41
draft: false
id: 20221116172241
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - file
  - open
  - split
  - vim
title: Open Files Side-By-Side with Vim
type: tech-note
---

I'll often want to open a couple of files in Vim and then split the main window so I have one file on the left, and one file on the right. I've just learnt that you can tell Vim to open each in it's own split, a vertical split or a horizontal split.

```sh
# Vertical split:
vim -O <file1> <file2>

# Horizontal split:
vim -o <file1> <file2>
```

It works with more than one file as well, so you could open three files, and have a pane for each.