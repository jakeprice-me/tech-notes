---
aliases:
  - github-cli-cheatsheet
category: github
classification: public
date: 2022-08-01T14:03:00
date_modified: 2022-08-01T14:03:00
draft: false
id: 20220801140300
image: 
links:
  - https://cli.github.com/manual/gh
local_archive_links: 
pinned: false
print: false
series: 
tags: [github, gh, command-line, git, cheatsheet]
title: GitHub CLI Cheatsheet
type: tech-note
---

```sh
# View issue:
gh issue view --repo <org>/<repo> 6396

# View issue in browser:
gh issue view --repo <org>/<repo> 6396 --web

# Add a comment to an issue in browser:
gh issue comment --repo <org>/<repo> 6395 --web

# View list of repos for myself:
gh repo list

# View list of repos for an organisation:
gh repo list <org>

# Open repository browser:
gh repo view <org>/configuration --web

# View list of secrets:
gh secret --repo <org>/<repo> list

# Create secret:
gh secret --repo <org>/<repo> set AAS_PUBLISH_PROFILE

# Delete secret:
gh secret --repo <org>/<repo> delete AAS_PUBLISH_PROFILE

# Clone repo:
gh repo clone <org>/<repo>
```

