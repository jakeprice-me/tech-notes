---
aliases:
  - send-output-to-clipboard-using-xclip
category: cli
classification: public
date: 2022-02-04T11:54:27
date_modified: 2023-11-19T11:39:22
draft: false
id: 20220204115427
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - clipboard
  - copy
  - paste
  - stdin
  - stdout
  - xclip
  - xsel
title: Send Output to Clipboard using xclip
type: tech-note
---

To send the output of a command in the terminal to the clipboard, the below is super helpful.

```sh
# Send contents of file to clipboard:
xclip -selection clip /tmp/owm.json

# Send pipe to clipboard:
rg --files-with-matches "^tags: \[\]" *.md | xclip -selection clip
```