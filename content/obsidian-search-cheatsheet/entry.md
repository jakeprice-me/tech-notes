---
aliases:
  - obsidian-search-cheatsheet
category: obsidian
classification: public
date: 2024-02-16T19:21:35
date_modified: 2024-09-23T16:47:01
draft: false
id: 20240216192135
image: 
links:
  - https://help.obsidian.md/Plugins/Search
local_archive_links:
  - attachments/obsidian-search-cheatsheet.html
pinned: false
print: false
series: 
tags:
  - cheatsheet
  - obsidian
  - search
title: Obsidian Search Cheatsheet
type: tech-note
---

I've ignored Obsidian's search for quite  while, but it's actually surprisingly powerful, and really very helpful.

Search for entries with a link to GitHub but no `github` tag:

```
["link":"https://github.com"] -tag:github
```

Search for entries with a category of `music`:

```
["category":music]
```

Search for entries with a category of `music`, and a series of `psalms`:

```
["category":music]["series":psalms]
```

Search for archive entries with links, but no archive link:

```
["type":archive][links:"https://"]-["archive_links":"https://"]
```