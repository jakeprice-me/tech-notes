---
alias: macos-chromium-damaged-cant-be-opened-fix
category: macos
classification: public
date: 2022-01-09 17:41:01
date_modified: null
id: 20220109174101
link: https://old.reddit.com/r/MacOS/comments/q9d772/homebrew_chromium_is_damaged_and_cant_be_openend/
pinned: false
tags:
- macos
- chromium
- damaged
- xattr
- attribute
- application
title: Fix "... Damaged Can't be Opened" on MacOS
type: tech-note
uuid: f1f272f1-c910-4662-90bf-a5b8c7b117d7
---

How to fix "Chromium is Damaged Can't Be Opened".

```sh
xattr -cr /Applications/Chromium.app
```