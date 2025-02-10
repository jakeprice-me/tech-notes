---
aliases:
  - chmod-reference-table
category: linux
classification: public
date: 2019-01-13T16:39:01
date_modified: 2024-09-23T22:28:19
draft: false
id: 20190113163901
image: 
links:
  - https://dbiers.me/chmod-permissions-reference-chart/
local_archive_links:
  - attachments/chmod-reference-table.html
pinned: false
print: false
series: 
tags:
  - chmod
  - linux
  - permission
title: chmod Reference Table
type: tech-note
---

A helpful overview of `chmod` permissions.

| Permission | User | Group | Other |
|------------|------|-------|-------|
| Read       | 4    | 4     | 4     |
| Write      | 2    | 2     | 2     |
| Execute    | 1    | 1     | 1     |
|            | U    | G     | O     |
|            | X    | X     | X     |

| Numeric | Permission |
|---------|------------|
| 777     | rwxrwxrwx  |
| 755     | rwxr-xr-x  |
| 644     | rw-r–r–    |
| 700     | rwx——      |
| 750     | rwxr-x—    |