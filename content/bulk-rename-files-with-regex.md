---
alias: bulk-rename-files-with-regex
archive_links: []
category: cli
classification: public
date: 2020-03-27 20:20:03
date_modified: 2020-03-27 20:20:03
id: 20200327202003
link: 
local_archive: 
pinned: false
series: 
tags: [regex, bash, rename, perl]
title: Bulk Rename Regex Pattern
type: tech-note
uuid: e61a7627-6142-4f68-8f20-528e38791615
---

Make sure you've installed the Perl rename tool: `sudo dnf install prename`.

```sh
prename --verbose 's/~\d{8}-\d{6}//;' *
```