---
alias: generate-sequences-bash
category: bash
classification: public
date: 2020-06-23 14:37:06
date_modified: 2020-06-23 14:37:06
id: 20200623143706
link: 
pinned: false
series: 
tags: [bash, loop, iterate]
title: Generate Sequences in Bash
type: tech-note
uuid: 4c7c1951-f8f5-46c9-abbc-1d6f51667207
---

You can generate sequences in Bash using the following syntax.

```sh
# Syntax:
for i in {1..200}; do <command>; done

# Example:
for i in {1..200}; do printf "id: %s\n" "$(uuidgen)"; done
```