---
aliases:
  - copy-ssh-key-to-user-with-rsync
category: ssh
classification: public
date: 2020-07-05T19:42:36
date_modified: 2020-07-05T19:42:36
draft: false
id: 20200705194236
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - rsync
  - server
  - ssh
title: Copy an SSH Key to Another User with Rsync
type: tech-note
---

If you want to allow another user to login to a server with the same key as another user (which is terrible!), you should login as the user with the key you want to copy and run the below `rsync` command, replacing `username` with the username of the user you are copying the key too.

`rsync --archive --chown=username:username ~/.ssh /home/username`

Then afterwards try logging in to the server as that user, and you should be able to.