---
alias: disable-cross-origin-request-blocking-firefox
archive_link: []
category: firefox
classification: public
date: 2020-09-25 17:50:47
date_modified: 2020-09-25 17:50:47
id: 20200925175047
link: 
local_archive: 
pinned: false
series: 
tags: [cors, firefox, javascript]
title: Disable Cross-Origin Request Blocking on Firefox
type: tech-note
uuid: 1ad98537-3304-4ea5-999b-d36d4d53dab1
---

When testing something that uses JavaScript locally, you may come across an error like this:

```text
Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at file://///wsl$/fedoraremix/home/jprice/my/documents/code/cloud-operations/aws-environment-details-webapp/js/data/aws-environments.json?_=1601052634622. (Reason: CORS request not http).
```

It's only an issue when running locally, but a quick and easy way to resolve it can be found in `about:config` on Firefox. The following preference should be set to `false`.

!!! warning
	Make sure you set it back to `true` once you have finished testing.

```ini
security.fileuri.strict_origin_policy: false
```