---
aliases:
  - linux-vscode-colour-block-bug
category: vscode
classification: public
date: 2020-03-15T12:20:53
date_modified: 2020-03-15T12:20:53
draft: false
id: 20200315122053
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [linux, vscode, bug]
title: Linux and Visual Studio Code Colour Block Bug
type: tech-note
---

In vscode open the command palette with Ctrl-Shift-P and then "Configure Runtime Arguments". In the `argv.json` file that opens, set `"disable-color-correct-rendering":` to `false`. This seems to fix the weird issues with background colour blocks that I get on Linux.

