---
alias: linux-vscode-colour-block-bug
category: vscode
classification: public
date: 2020-03-15 12:20:53
date_modified: null
id: 20200315122053
pinned: false
tags: [linux, vscode, bug]
title: Linux and Visual Studio Code Colour Block Bug
type: tech-note
uuid: 98d90302-4a7f-4d24-8146-79dc8feb2094
---

In vscode open the command palette with Ctrl-Shift-P and then "Configure Runtime Arguments". In the `argv.json` file that opens, set `"disable-color-correct-rendering":` to `false`. This seems to fix the weird issues with background colour blocks that I get on Linux.