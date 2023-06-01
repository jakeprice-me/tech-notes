---
alias: act-cheatsheet
category: github
classification: public
date: 2022-08-08 11:05:14
date_modified: 2022-08-08 11:05:14
id: 20220808110514
link: https://github.com/nektos/act
pinned: false
series: 
tags: [github, action, runner, local, ci-cd, pipeline]
title: act Cheatsheet
type: tech-note
uuid: 47e6d68e-00cc-4167-9b67-3a40df279584
---

```sh
# Run act with specific workflow, include a secrets file and specify container architecture:
act --workflows .github/workflows/azure_app_service.yml --secret-file .secrets --container-architecture linux/amd64

# Run act with a place to put an artifact:
act --workflows .github/workflows/azure_app_service.yml --secret-file .secrets --container-architecture linux/amd64 --artifact-server-path /tmp/act-artifacts
```