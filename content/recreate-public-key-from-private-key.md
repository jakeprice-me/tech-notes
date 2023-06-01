---
alias: recreate-public-key-from-private-key
category: ssh
classification: public
date: 2019-03-09 20:07:45
date_modified: 2019-03-09 20:07:45
id: 20190309200745
link: 
pinned: false
series: 
tags: [ssh, ssh-keygen, public-key, private-key]
title: Recreate Public Key from Private Key
type: tech-note
uuid: 0e90b140-9245-4fef-bc5f-982a70e1f1d8
---

If you've lost a public key you can read the private key and have `ssh-keygen` recreate the public key.

```sh
$ ssh-keygen -y -f <private-key-file> > <public-key-file>.pub
```

It won't retain the private key's comment so you will need to manually append a comment to the public key if required.