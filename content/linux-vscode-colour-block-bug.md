---
aliases:
  - linux-vscode-colour-block-bug
archive_links: 
category: vscode
classification: public
date: 2020-03-15T12:20:53
date_modified: 2020-03-15T12:20:53
id: 20200315122053
link: 
local_archive: 
pinned: false
series: 
tags: [linux, vscode, bug]
title: Linux and Visual Studio Code Colour Block Bug
type: tech-note
---

In vscode open the command palette with Ctrl-Shift-P and then "Configure Runtime Arguments". In the `argv.json` file that opens, set `"disable-color-correct-rendering":` to `false`. This seems to fix the weird issues with background colour blocks that I get on Linux.