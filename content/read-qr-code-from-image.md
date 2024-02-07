---
aliases:
  - read-qr-code-from-image
archive_links: 
category: cli
classification: public
date: 2022-07-05T20:01:59
date_modified: 2022-07-05T20:01:59
draft: false
id: 20220705200159
link: 
local_archive: 
pinned: false
series: 
tags: [qr, qrcode]
title: Read QR Code from Image
type: tech-note
---

```sh
# Install zbar:
sudo dnf install zbar

# Read and display QR code contents:
zbarimg <filename>
```