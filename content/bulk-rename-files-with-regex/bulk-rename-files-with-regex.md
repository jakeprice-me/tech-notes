---
aliases:
  - bulk-rename-files-with-regex
archive_links: 
category: cli
classification: public
date: 2020-03-27T20:20:03
date_modified: 2020-03-27T20:20:03
draft: false
id: 20200327202003
link: 
local_archive: 
pinned: false
print: false
series: 
tags: [regex, bash, rename, perl]
title: Bulk Rename Regex Pattern
type: tech-note
---

Make sure you've installed the Perl rename tool: `sudo dnf install prename`.

```sh
prename --verbose 's/~\d{8}-\d{6}//;' *
```