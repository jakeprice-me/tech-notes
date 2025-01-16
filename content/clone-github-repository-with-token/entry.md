---
aliases:
  - clone-github-repository-with-token
category: github
classification: public
date: 2022-09-09T21:13:39
date_modified: 2022-09-09T21:13:39
draft: false
id: 20220909211339
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [github, token, clone, personal-access-token]
title: Clone GitHub Repository with Personal Access Token
type: tech-note
---

Create a Personal Access Token (PAT) [here](https://github.com/settings/tokens/new). Then you can use it to clone a repository, and save the need for a private key. Especially helpful on a server.

```sh
# Clone a repository:
git clone https://<token>@github.com/owner/repo.git

# Clone a branch from a repository:
git clone --branch <branch-name> https://<token>@github.com/owner/repo.git
```

