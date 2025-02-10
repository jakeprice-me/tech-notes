---
aliases:
  - save-vim-session
category: vim
classification: public
date: 2020-06-03T10:02:27
date_modified: 2020-06-03T10:02:27
draft: false
id: 20200603100227
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - buffers
  - sessions
  - vim
title: Save a Vim Session
type: tech-note
---

Save your Vim session into a session file, buffers and all.

```sh
# Start Vim with Session
vim -S <session>.vim

# Create a Session File
:mks[ession] <file>
```