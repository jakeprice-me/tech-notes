---
aliases:
  - create-a-qr-code
archive_links: 
category: cli
classification: public
date: 2021-09-02T15:05:32
date_modified: 2021-09-02T15:05:32
draft: false
id: 20210902150532
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - qrencode
  - credentials
  - password
  - wi-fi
title: Create a QR Code
type: tech-note
---

## Wi-Fi

Some smartphones have the ability to connect to Wi-Fi by scanning a QR code. You can use the `qrencode` tool to do this.

Here's the standard template:

```text
WIFI:S:<ssid>;T:<security-type>;P:<password>;;
```

Here's a couple of examples using `qrencode`, which you'll need to install.

```sh
# Example (print the output on the terminal):
qrencode --type=ansiutf8 "WIFI:S:<ssid>;T:WPA;P:<password>;;"

# Example (print the output to a file, which you can then print):
qrencode \
    --type=PNG \
    --size=6 \
    --foreground="4caf50" \
    --background="FFFFFF" \
    --output ppn5.png \
    "WIFI:S:PPN5;T:WPA;P:Groggily*Exclude1*Sublevel*Denial;;"
```

## Misc Information

```bash
# Multiline:
qrencode \
    --type=PNG \
    --size=6 \
    --foreground="006a4d" \
    --background="FFFFFF" \
    --output output.png \
    """
Multiline
QR Code
With Text
    """
```
