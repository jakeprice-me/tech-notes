---
alias: send-output-to-clipboard-using-xclip
category: cli
classification: public
date: 2022-02-04 11:54:27
date_modified: 2022-02-04 11:54:27
id: 20220204115427
link: 
link_archive: 
pinned: false
series: 
tags: [xclip, xsel, clipboard, stdout, stdin, copy, paste]
title: Send Output to Clipboard using xclip
type: tech-note
uuid: faf3cb58-4fd5-4642-8f90-c6cb472e65c0
---

To send the output of a command in the terminal to the clipboard, the below is super helpful.

```sh
xclip -selection clip /tmp/owm.json
```