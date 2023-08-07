---
alias: clone-github-repository-with-token
archive_link: []
category: github
classification: public
date: 2022-09-09 21:13:39
date_modified: 2022-09-09 21:13:39
id: 20220909211339
link: 
local_archive: 
pinned: false
series: 
tags: [github, token, clone, personal-access-token]
title: Clone GitHub Repository with Personal Access Token
type: tech-note
uuid: 09381c0e-2aec-48cb-89c5-26ab448931eb
---

Create a Personal Access Token (PAT) [here](https://github.com/settings/tokens/new). Then you can use it to clone a repository, and save the need for a private key. Especially helpful on a server.

```sh
# Clone a repository:
git clone https://<token>@github.com/owner/repo.git

# Clone a branch from a repository:
git clone --branch <branch-name> https://<token>@github.com/owner/repo.git
```