---
aliases:
  - python-requests-cheatsheet
archive_links: 
category: python
classification: public
date: 2020-08-23T19:32:17
date_modified: 2020-08-23T19:32:17
draft: false
id: 20200823193217
link: 
local_archive: 
pinned: false
print: false
series: 
tags: [python, requests, api]
title: Requests Python Library
type: tech-note
---

## View raw HTTP Request

Helpful for debugging.

```py
print(r.request.body)
print(r.request.headers)
```