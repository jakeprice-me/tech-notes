---
aliases:
  - block-javascript-on-website-using-ublock-origin
archive_links: 
category: firefox
classification: public
date: 2024-06-25T14:51:57
date_modified: 2024-06-25T14:51:57
draft: false
id: 20240625145157
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - ublock
  - javascript
title: Block Javascript on Website Using uBlock Origin
type: tech-note
---

Add the below to the "Permanent rules" section under "My rules" in uBlock Origin's settings.

```
no-scripting: website.co.uk true
no-scripting: www.website.co.uk true
```
