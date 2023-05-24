---
alias: read-qr-code-from-image
category: cli
classification: public
date: 2022-07-05 20:01:59
date_modified: null
id: 20220705200159
link: null
pinned: false
tags:
- qr
- qrcode
title: Read QR Code from Image
type: tech-note
uuid: fa59305f-2ebc-4185-b455-437aef40acb5
---

```sh
# Install zbar:
sudo dnf install zbar

# Read and display QR code contents:
zbarimg <filename>
```