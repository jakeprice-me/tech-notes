---
aliases:
  - read-qr-code-from-image
category: cli
classification: public
date: 2022-07-05T20:01:59
date_modified: 2022-07-05T20:01:59
draft: false
id: 20220705200159
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - qrcode
  - zbar
title: Read QR Code from Image
type: tech-note
---

```sh
# Install zbar:
sudo dnf install zbar

# Read and display QR code contents:
zbarimg <filename>
```