---
alias: sed-cheatsheet
archive_links: []
category: sed
classification: public
date: 2020-06-01 18:03:09
date_modified: 2020-06-01 18:03:09
id: 20200601180309
link: 
local_archive: 
pinned: false
series: 
tags: [sed, bash, linux]
title: sed Cheatsheet
type: tech-note
uuid: 3ffa8c38-0d7c-4605-9054-df71bc888656
---

```sh
# Prepend to beginning of line number:
sed '<line>s/^/hello/' <file>

# Multiple `sed` commands:
sed '337s/^/+++<s>+++/; 337s/$/+++<\/s>+++/' <file>

# Regex to identify numbers as \d{*} doesn't work:
sed 's/?ref=v[0-9]*\.[0-9]*\.[0-9]*//g'

# Takes filename minus ending and appends to image frontmatter path.
for file in *.md; do BOOK=$(basename --suffix=.md $file) && sed --in-place=.orig "7s/$/$BOOK.png/" $file; done

# Replace ## Chapter with frontmatter book name:
for file in *.md; do BOOK=$(grep "book: " $file | sed 's/book: //'); echo $BOOK && sed --in-place=.orig "s/## Chapter/## $BOOK/" $file ; done
```