---
aliases:
  - disable-cross-origin-request-blocking-firefox
archive_links: 
category: firefox
classification: public
date: 2020-09-25T17:50:47
date_modified: 2020-09-25T17:50:47
draft: false
id: 20200925175047
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [cors, firefox, javascript]
title: Disable Cross-Origin Request Blocking on Firefox
type: tech-note
---

When testing something that uses JavaScript locally, you may come across an error like this:

```text
Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at file://///wsl$/fedoraremix/home/jprice/my/documents/code/cloud-operations/aws-environment-details-webapp/js/data/aws-environments.json?_=1601052634622. (Reason: CORS request not http).
```

It's only an issue when running locally, but a quick and easy way to resolve it can be found in `about:config` on Firefox. The following preference should be set to `false`.

> [!warning]
> Make sure you set it back to `true` once you have finished testing.

```ini
security.fileuri.strict_origin_policy: false
```

