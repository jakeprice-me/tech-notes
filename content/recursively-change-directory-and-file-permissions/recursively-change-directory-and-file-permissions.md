---
aliases:
  - recursively-change-directory-and-file-permissions
category: cli
classification: public
date: 2021-07-26T14:37:38
date_modified: 2021-07-26T14:37:38
draft: false
id: 20210726143738
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [find, chmod, recursive, permission]
title: Recursively Change Directory and File Permissions
type: tech-note
---

If you've messed up the permissions in a directory, you can recursively fix it with `find`.

```sh
# Operate on directories:
find <path> -type d -exec chmod 755 {} \;

# Operate on files:
find <path> -type f -exec chmod 644 {} \;
```

