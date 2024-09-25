---
aliases:
  - pandoc-cheatsheet
archive_links: 
category: pandoc
classification: public
date: 2020-05-16T10:46:32
date_modified: 2020-05-16T10:46:32
draft: false
id: 20200516104632
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [pandoc, commands, markdown, markup, cheatsheet]
title: Pandoc Cheatsheet
type: tech-note
---

```sh
# Convert Markdown to HTML:
pandoc --from=markdown --to=html <file>.md > <file>.html

# Create a self-contained HTML file:
pandoc --toc --css <stylesheet>.css --standalone <input>.md --toc --output <output>.html
```

