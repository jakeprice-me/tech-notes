---
alias: pandoc-cheatsheet
category: pandoc
classification: public
date: 2020-05-16 10:46:32
date_modified: 2020-05-16 10:46:32
id: 20200516104632
link: 
link_archive: 
pinned: false
series: 
tags: [pandoc, commands, markdown, markup, cheatsheet]
title: Pandoc Cheatsheet
type: tech-note
uuid: 73da8d1e-66ed-41af-bfd0-5985bd117e70
---

```sh
# Convert Markdown to HTML:
pandoc --from=markdown --to=html <file>.md > <file>.html

# Create a self-contained HTML file:
pandoc --toc --css <stylesheet>.css --standalone <input>.md --toc --output <output>.html
```