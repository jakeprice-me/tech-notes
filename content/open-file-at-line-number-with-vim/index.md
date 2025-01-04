---
aliases:
  - open-file-at-line-number-with-vim
category: vim
classification: public
date: 2022-11-16T17:19:31
date_modified: 2022-11-16T17:19:31
draft: false
id: 20221116171931
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [vim, line-number, open, file]
title: Open a File at Specified Line Number with Vim
type: tech-note
---

You can provide a line number as an argument when opening a file in Vim and Vim will open the file and put the cursor at that line number. 

```sh
vim +<line_number> <filename>
```

With a real example, the above becomes:

```sh
vim +82 playbook.yml
```

