---
aliases:
  - jira-jql-statements
category: jira
classification: public
date: 2023-06-21T12:18:19
date_modified: 2023-06-21T12:18:19
draft: false
id: 20230621121822
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - jira
  - jql
  - issue
  - ticket
title: Jira JQL Statements
type: tech-note
---

Some handy Jira JQL queries:

```sql
-- Display my unresolved, open tickets by priority:
assignee = currentUser() AND resolution = Unresolved AND status != Done ORDER BY priority DESC

-- Display my unresolved, open tickets by last updated:
assignee = currentUser() AND resolution = Unresolved AND status != Done ORDER BY updated DESC
```
