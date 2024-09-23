---
aliases:
  - macos-chromium-damaged-cant-be-opened-fix
archive_links:
  - https://web.archive.org/web/20211016143800/https://old.reddit.com/r/MacOS/comments/q9d772/homebrew_chromium_is_damaged_and_cant_be_openend/
category: macos
classification: public
date: 2022-01-09T17:41:01
date_modified: 2024-09-23T21:50:33
draft: false
id: 20220109174101
image: 
links:
  - https://old.reddit.com/r/MacOS/comments/q9d772/homebrew_chromium_is_damaged_and_cant_be_openend/
local_archive_links:
  - attachments/20220109174101.html
pinned: false
print: false
series: 
tags:
  - macos
  - chromium
  - damaged
  - xattr
  - attribute
  - application
title: Fix "... Damaged Can't be Opened" on MacOS
type: tech-note
---

How to fix "Chromium is Damaged Can't Be Opened".

```sh
xattr -cr /Applications/Chromium.app
```