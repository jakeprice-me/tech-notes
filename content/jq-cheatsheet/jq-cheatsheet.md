---
aliases:
  - jq-cheatsheet
category: jq
classification: public
date: 2020-05-08T11:24:48
date_modified: 2024-05-22T09:45:33
draft: false
id: 20200508112448
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - jq
  - json
  - cheatsheet
title: jq Cheatsheet
type: tech-note
---

```sh
# Take value and add to a new key name:
.[ ] | .[ ] | { Name: .StackName, Status: .StackStatus, Created: .CreationTime }

# Put values into new object:
jq '.[]|{name,id}'

# Sort by date key:
jq '. | sort_by(.date)'
```
