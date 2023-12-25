---
aliases:
  - quick-caddy-reload
archive_links: 
category: caddy
classification: public
date: 2023-12-25T23:14:43
date_modified: 2023-12-25T23:14:43
draft: false
id: 20231225231443
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - caddy
  - docker
  - reload
title: Quick Caddy Reload
type: tech-note
---

You can reload your Caddyfile with no downtime (need to confirm that), and without restarting Caddy by running `caddy reload`.

I only ever run Caddy from a Docker container, in which case I just run the below.

```sh
docker exec --workdir /etc/caddy --interactive --tty <caddy-container-name> caddy reload
```

I always just used to stop and start Caddy... Quick though that is, it pays to read the docs!
