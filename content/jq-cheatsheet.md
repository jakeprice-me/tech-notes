---
alias: jq-cheatsheet
archive_link: []
category: cli
classification: public
date: 2020-05-08 11:24:48
date_modified: 2020-05-08 11:24:48
id: 20200508112448
link: 
local_archive: 
pinned: false
series: 
tags: [jq, json]
title: jq Cheatsheet
type: tech-note
uuid: 9bf4766e-2481-45d2-bd37-5c9e61e5d05c
---

```sh
# Take value and add to a new key name.
.[ ] | .[ ] | { Name: .StackName, Status: .StackStatus, Created: .CreationTime }

# Put values into new object:
jq '.[]|{name,id}'
```
