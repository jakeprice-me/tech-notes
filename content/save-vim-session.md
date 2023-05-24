---
alias: save-vim-session
category: vim
classification: public
date: 2020-06-03 10:02:27
date_modified: null
id: 20200603100227
pinned: false
tags:
- vim
- sessions
- buffers
title: Save a Vim Session
type: tech-note
uuid: 6b48fcd2-a258-4c3e-8377-3b6bc879123c
---

Save your Vim session into a session file, buffers and all.

```sh
# Start Vim with Session
vim -S <session>.vim

# Create a Session File
:mks[ession] <file>
```