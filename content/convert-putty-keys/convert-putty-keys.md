---
aliases:
  - convert-putty-keys
archive_links: 
category: putty
classification: public
date: 2019-06-26T15:08:00
date_modified: 2019-06-26T15:08:00
draft: false
id: 20190626150800
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [putty, ppk, pem, ssh]
title: Convert Putty Keys
type: tech-note
---

To convert a PuTTY `.ppk` key to something that you can use on Linux or WSL start by installing "PuTTY Tools".

```sh
# Fedora
sudo dnf install putty

# Ubuntu
sudo apt install putty-tools
```

Then you can use the `puttygen` utility to convert to `.pem`.

```sh
# Private
puttygen <filename>.ppk -O private-openssh -o <filename>.pem

# Public
puttygen <filename>.ppk -O public-openssh -o <filename>.pem
```

If you need to convert the other way (to `.pem`), you can do that as well.

```sh
# Private
puttygen <filename>.pem -o <filename>.ppk -O private

# Public
puttygen <filename>.pem -o <filename>.ppk -O public
```