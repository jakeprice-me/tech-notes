---
aliases:
  - generate-sequences-bash
category: bash
classification: public
date: 2020-06-23T14:37:06
date_modified: 2020-06-23T14:37:06
draft: false
id: 20200623143706
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - bash
  - iterate
  - loop
title: Generate Sequences in Bash
type: tech-note
---

You can generate sequences in Bash using the following syntax.

```sh
# Syntax:
for i in {1..200}; do <command>; done

# Example:
for i in {1..200}; do printf "id: %s\n" "$(uuidgen)"; done
```