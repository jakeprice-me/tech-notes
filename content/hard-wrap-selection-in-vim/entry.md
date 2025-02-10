---
aliases:
  - hard-wrap-selection-in-vim
category: vim
classification: public
date: 2022-10-21T12:37:10
date_modified: 2022-10-21T12:37:10
draft: false
id: 20221021123710
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - hard-wrap
  - text-width
  - vim
  - wrap
title: Hard Wrap Selection in Vim
type: tech-note
---

This is a handy little trick to hard wrap a selection of text to a specific column number. I usually use this when I'm rewriting a Git commit message which I may have edited a bit and lost the automatic hardwrapping Vim enables for Git commit messages.

Here's an example message.

```text
Change `entries` command to only list by default

`entries` will not prompt for an ID to edit after displaying the list, `--edit`, or `-e` can now be appended to prompt for an ID to edit in the
default editor.
```

Tell Vim the `textwidth` you want to hardwrap to:

```sh
:set textwidth=72
```

Then select the text you wish to wrap, and type the following key sequence.

```sh
gq$
```

You'll then get a perfectly hardwrapped message as can be seen below:

```text
Change `entries` command to only list by default

`entries` will not prompt for an ID to edit after displaying the list,
`--edit`, or `-e` can now be appended to prompt for an ID to edit in the
default editor.
```