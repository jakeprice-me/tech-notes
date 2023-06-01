---
alias: python-requests-cheatsheet
category: python
classification: public
date: 2020-08-23 19:32:17
date_modified: 2020-08-23 19:32:17
id: 20200823193217
link: 
pinned: false
series: 
tags: [python, requests, api]
title: Requests Python Library
type: tech-note
uuid: a823cd35-212e-4ec4-a585-22f515c8e3f6
---

## View raw HTTP Request

Helpful for debugging.

```py
print(r.request.body)
print(r.request.headers)
```