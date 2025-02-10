---
aliases:
  - make-table-headings-sticky
category: css
classification: public
date: 2024-02-25T08:03:01
date_modified: 2024-02-25T08:03:01
draft: false
id: 20240225080301
image: 
links:
  - https://btxx.org/posts/Please_Make_Your_Table_Headings_Sticky/
local_archive_links:
  - attachments/make-table-headings-sticky.html
pinned: false
print: false
series: 
tags:
  - css
  - sticky
  - tables
title: Make Table Headings Sticky
type: tech-note
---

Handy tip on making table headings sticky:

> You only need to add 2 CSS properties on your `thead`:
> 
> ```css
> position: sticky;
> top: 0;
> ```
> 
> That’s it! Best of all, `sticky` has [~96% global support](https://caniuse.com/?search=sticky) which means this isn’t some “bleeding-edge” property and can safely support a ton of browsers. Not to mention the improved experience for your end-users!