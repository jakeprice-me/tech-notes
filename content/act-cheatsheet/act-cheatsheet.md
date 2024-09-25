---
aliases:
  - act-cheatsheet
archive_links: 
category: github
classification: public
date: 2022-08-08T11:05:14
date_modified: 2022-08-08T11:05:14
draft: false
id: 20220808110514
image: 
links:
  - https://github.com/nektos/act
local_archive_links: 
pinned: false
print: false
series: 
tags: [github, action, runner, local, ci-cd, pipeline]
title: act Cheatsheet
type: tech-note
---

```sh
# Run act with specific workflow, include a secrets file and specify container architecture:
act --workflows .github/workflows/azure_app_service.yml --secret-file .secrets --container-architecture linux/amd64

# Run act with a place to put an artifact:
act --workflows .github/workflows/azure_app_service.yml --secret-file .secrets --container-architecture linux/amd64 --artifact-server-path /tmp/act-artifacts
```

