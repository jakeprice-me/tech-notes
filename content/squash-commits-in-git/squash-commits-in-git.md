---
aliases:
  - squash-commits-in-git
archive_links: 
category: git
classification: public
date: 2023-11-10T15:31:31
date_modified: 2023-11-10T15:31:31
draft: false
id: 20231110153131
image: 
links: 
local_archive_links:  
pinned: false
print: false
series: 
tags: [git, squash, history, commit, rebase, interactive]
title: Squash Commits in Git
type: tech-note
---

In most situations I don't like the idea of squashing commits, I feel like it's much better to have each change associated to a single commit. However, sometimes that's not always possible, and there's nothing worse than dozens of "trying this again" or "still not working" commit messages (especially when you're trying stuff in a pipeline), which if still working on a single issue, should really end up just being one commit most of the time.

Squashing commits is pretty simple once you know how though.

Start an interactive rebase.

```sh
# n is the number of commits back you want to squash including the most recent:
git rebase --interactive HEAD~<n>
```

Your default terminal editor will open, you can now choose which commits you want to squash, by changing `pick` to `squash`.

```sh
pick 6e24e1e Update cron
squash 8652f2b Add support for custom regular expressions
squash f18d5f2 Update licence to GNU GPLv3
squash 3fc60da Switch logging from file to stdout
```

Once you save and exit your editor, you can write the new commit message. Save and quit and that's the squash done.

```sh
# Before squashing:
$ git log --oneline
3fc60da (HEAD -> master, origin/master, origin/HEAD) Switch logging from file to stdout
f18d5f2 Update licence to GNU GPLv3
8652f2b Add support for custom regular expressions
6e24e1e Update cron
3f1ad6e Add template file and update instructions
7506054 Ignore config.yml

# After squashing:
$ git log --oneline
bda8f83 (HEAD -> master) Nice squashed commit
3f1ad6e Add template file and update instructions
7506054 Ignore config.yml
```

