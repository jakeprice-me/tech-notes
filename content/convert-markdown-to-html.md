---
alias: convert-markdown-to-html
category: pandoc
classification: public
date: 2019-12-29 20:10:00
date_modified: 2019-12-29 20:10:00
id: 20191229201000
link: 
pinned: false
series: 
tags: [pandoc, convert, markdown, html]
title: Convert Markdown to HTML
type: tech-note
uuid: 6982152e-9231-4ec6-b9f9-f2be4b09f7ae
---

``` sh
# Convert Markdown to HTML:
pandoc --output=<output>.html --to=html5 --standalone <input>.md
```