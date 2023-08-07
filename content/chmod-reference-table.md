---
alias: chmod-reference-table
archive_link: []
category: linux
classification: public
date: 2019-01-13 16:39:01
date_modified: 2019-01-13 16:39:01
id: 20190113163901
link: https://dbiers.me/chmod-permissions-reference-chart/
local_archive: 
pinned: false
series: 
tags: [chmod, linux, permissions]
title: chmod Reference Table
type: tech-note
uuid: 6335c00d-5cbb-4f09-9d12-644a92d308f8
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