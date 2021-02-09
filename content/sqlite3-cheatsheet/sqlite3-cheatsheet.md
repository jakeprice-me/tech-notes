---
aliases:
  - sqlite3-cheatsheet
archive_links: 
category: sqlite
classification: public
date: 2021-02-09T12:33:11
date_modified: 2021-02-09T12:33:11
draft: false
id: 20210209123311
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [cheatsheet, sql, sqlite, database]
title: SQLite3 Cheat Sheet
type: tech-note
---

```sh
# Run script on database:
sqlite3 example.db
sqlite> .read create.sql

# Run script on database:
sqlite3 example.db < create.sql

# Run query on database:
sqlite3 example.db 'CREATE TABLE entries(id TEXT, title TEXT, date TEXT, tags TEXT, content TEXT);'

# Delete row where column equals:
sqlite3 wiki.db "DELETE FROM entries WHERE id=20210209145248;"

# Delete row:
DELETE FROM "main"."entries" WHERE _rowid_ IN ('918');
```