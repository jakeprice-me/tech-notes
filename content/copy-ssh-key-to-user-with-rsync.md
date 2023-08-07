---
alias: copy-ssh-key-to-user-with-rsync
archive_link: []
category: ssh
classification: public
date: 2020-07-05 19:42:36
date_modified: 2020-07-05 19:42:36
id: 20200705194236
link: 
local_archive: 
pinned: false
series: 
tags: [ssh, rsync, server]
title: Copy an SSH Key to Another User with Rsync
type: tech-note
uuid: 4de4b631-a8eb-4512-8d20-a5e9f5dbd620
---

If you want to allow another user to login to a server with the same key as another user (which is terrible!), you should login as the user with the key you want to copy and run the below `rsync` command, replacing `username` with the username of the user you are copying the key too.

`rsync --archive --chown=username:username ~/.ssh /home/username`

Then afterwards try logging in to the server as that user, and you should be able to.