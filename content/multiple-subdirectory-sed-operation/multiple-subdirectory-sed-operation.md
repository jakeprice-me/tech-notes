---
aliases:
  - multiple-subdirectory-sed-operation
archive_links: 
category: bash
classification: public
date: 2020-11-24T18:51:02
date_modified: 2020-11-24T18:51:02
draft: false
id: 20201124185102
link: 
local_archive: 
pinned: false
print: false
series: 
tags: [loop, iterate, sed, bash]
title: Multiple Subdirectory sed Operation
type: tech-note
---

The below will loop through each subdirectory from wherever you run it, then perform a `sed` operation on files matching the file ending.

As can be seen in the example, I've used this to quickly update providers across lots of Terraform modules, without having to manually update them.

```sh
# Formatted:
for directory in *; do
    for file in $directory/*.tf; do
        sed --in-place=.bak --regexp-extended 's/aws    = "2.67.0"/aws    = "3.17.0"/g' $file
    done
done
```