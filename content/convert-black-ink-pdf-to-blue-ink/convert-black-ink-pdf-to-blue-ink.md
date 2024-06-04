---
aliases:
  - convert-black-ink-pdf-to-blue-ink
archive_links:
  - https://web.archive.org/web/20210506190019/https://superuser.com/questions/202935/how-can-i-print-out-a-pdf-substituting-pixels-for-blue-pixels
category: cli
classification: public
date: 2024-06-04T17:11:45
date_modified: 2024-06-04T17:11:45
draft: false
id: 20240604171145
image: 
links:
  - https://superuser.com/questions/202935/how-can-i-print-out-a-pdf-substituting-pixels-for-blue-pixels
local_archive_links:
  - attachments/20240604171145.html
pinned: false
print: false
series: 
tags:
  - printer
  - low-ink
  - black
  - blue
  - link
  - imagemagick
  - convert
  - colour
title: Convert Black Ink PDF to Blue Ink
type: tech-note
---

This is a handy command from [Super User](https://superuser.com/questions/202935/how-can-i-print-out-a-pdf-substituting-pixels-for-blue-pixels), for when you've run out of black printer ink and really need to print something. 

If you have some colour left, you can run this to convert the black ink in the PDF to blue (or any other colour you specify), and print what you need to print until you can get some new ink.

```sh
magick convert -density 300 input.pdf -fill blue -opaque black output.pdf
```
