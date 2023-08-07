---
alias: open-file-at-line-number-with-vim
archive_link: []
category: vim
classification: public
date: 2022-11-16 17:19:31
date_modified: 2022-11-16 17:19:31
id: 20221116171931
link: 
local_archive: 
pinned: false
series: 
tags: [vim, line-number, open, file]
title: Open a File at Specified Line Number with Vim
type: tech-note
uuid: 8464c4ff-b2f5-4c9d-bea7-9570a90625c8
---

You can provide a line number as an argument when opening a file in Vim and Vim will open the file and put the cursor at that line number. 

```sh
vim +<line_number> <filename>
```

With a real example, the above becomes:

```sh
vim +82 playbook.yml
```