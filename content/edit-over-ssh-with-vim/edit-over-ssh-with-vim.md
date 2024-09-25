---
aliases:
  - edit-over-ssh-with-vim
archive_links: 
category: vim
classification: public
date: 2020-06-19T10:05:44
date_modified: 2020-06-19T10:05:44
draft: false
id: 20200619100544
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [vim, remote, scp]
title: Edit over SSH with Vim
type: tech-note
---

Vim can edit files remotely, on a server. It uses `scp` to copy it locally, allow you to work on it, and then it copies it back to the server. You can even use `netrw` to view remote directories, and then select a file to edit.

Firstly you need to add a host to your ssh `config` file:

```sh
Host <name>
    HostName <ip>
    User <username>
    IdentityFile <ssh-key>
```

Then you can simply edit as below:

```sh
# Directory:
vim scp://<name>//home/<username>/

# File:
vim scp://<name>//home/<username>/<file>.py
```

If you have an issue with the statusbar not displaying properly you can just refresh the screen with `^L`.

