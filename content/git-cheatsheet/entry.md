---
aliases:
  - git-cheatsheet
category: git
classification: public
date: 2020-05-16T21:19:55
date_modified: 2020-05-16T21:19:55
draft: false
id: 20200516211955
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [git, version-control, repository]
title: Git Cheatsheet
type: tech-note
---

```sh
# Set editor:
git config --global core.editor "vim"

# Create tag:
git tag --annotate v0.0.1 --message="Commit message"

# Push annotated tags only:
git push --follow-tags

# Push all tags (lightweight and annotated):
git push origin --tags
git push origin v0.0.1

# Delete tag:
git tag --delete v0.0.1
git push origin --delete v0.0.1

# Show tag data:
git show v0.0.1

# Retrospectively tag (if you forget to tag a commit):
git log --pretty=oneline
git tag -a v1.2 <checksum here (or part of it)>

# Git logging:
git log --pretty=format:"%h %an %ae"
```

