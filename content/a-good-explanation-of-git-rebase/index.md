---
aliases:
  - a-good-explanation-of-git-rebase
category: git
classification: public
date: 2023-02-02T16:56:12
date_modified: 2023-02-02T16:56:12
draft: false
id: 20230202165612
image: 
links:
  - https://www.reddit.com/r/git/comments/10jiyxu/is_making_too_many_commits_bad/
local_archive_links:
  - attachments/20240903192056.html
pinned: false
print: false
series: 
tags:
  - git
  - rebase
  - reddit
  - commit
title: A Good Explanation of git rebase
type: tech-note
---

A good explanation of `git rebase` from a [thread](https://www.reddit.com/r/git/comments/10jiyxu/is_making_too_many_commits_bad/) on r/git.

> The key to understanding rebase is to understand that the way everyone describes it is totally stupid. They describe it as "it replays commits from one branch to another". The problem is that describes how it does what it does. Not the what it does.
> 
> What it does is changes the commit your branch is based off of. If you create your branch off of commit 1 of main and do some dev on your branch. Then in the meantime main gets 5 more commits you can tell your branch "forgot all about the fact you were created from commit 1, let's just pretend I created you from commit 6".
> 
> Once I understood that the way it is described is stupid it made much more sense. (I still use merge instead of rebase though).
> 
> — u/wildjokers
