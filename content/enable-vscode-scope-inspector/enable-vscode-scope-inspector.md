---
aliases:
  - enable-vscode-scope-inspector
archive_links: 
category: vscode
classification: public
date: 2020-07-05T19:43:21
date_modified: 2020-07-05T19:43:21
draft: false
id: 20200705194321
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [vscode, editor]
title: Enable Scope Inspector in VS Code
type: tech-note
---

Use the scope inspector to debug grammars. You can view scopes for a selected token.

Enable it with `Ctrl-Shift-P` and type in `scope` and select `Developer: Inspect Editor Tokens and Scopes`

You can also create a keybinding for it.

``` bash
{
  "key": "cmd+alt+shift+i",
  "command": "editor.action.inspectTMScopes"
}
```