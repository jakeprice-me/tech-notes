---
aliases:
  - recreate-public-key-from-private-key
archive_links: 
category: ssh
classification: public
date: 2019-03-09T20:07:45
date_modified: 2019-03-09T20:07:45
draft: false
id: 20190309200745
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [ssh, ssh-keygen, public-key, private-key]
title: Recreate Public Key from Private Key
type: tech-note
---

If you've lost a public key you can read the private key and have `ssh-keygen` recreate the public key.

```sh
$ ssh-keygen -y -f <private-key-file> > <public-key-file>.pub
```

It won't retain the private key's comment so you will need to manually append a comment to the public key if required.