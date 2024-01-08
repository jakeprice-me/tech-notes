---
aliases:
  - jq-cheatsheet
archive_links: 
category: cli
classification: public
date: 2020-05-08T11:24:48
date_modified: 2020-05-08T11:24:48
id: 20200508112448
link: 
local_archive: 
pinned: false
series: 
tags: [jq, json]
title: jq Cheatsheet
type: tech-note
---

```sh
# Take value and add to a new key name.
.[ ] | .[ ] | { Name: .StackName, Status: .StackStatus, Created: .CreationTime }

# Put values into new object:
jq '.[]|{name,id}'
```
