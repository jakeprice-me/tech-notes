---
aliases:
  - miniflux-api
category: api
classification: public
date: 2024-06-22T09:08:55
date_modified: 2024-06-23T18:19:25
draft: false
id: 20240622090855
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - api
  - curl
  - miniflux
  - rss
title: Miniflux API
type: tech-note
---

```sh
# Feeds in a 
category:
curl --request GET \
  --url https://miniflux/v1/categories/31/feeds \
  --header "Content-Type: application/json" \
  --header "X-Auth-Token: <api-token>"

# Add feed URL to category (subscribe to feed):
curl --request POST \
  --url https://miniflux/v1/feeds \
  --header "Content-Type: application/json" \
  --header "X-Auth-Token: <api-token>" \
  --data '{ "feed_url": "<feed-url>", "category_id": 31 }'

# Mark entries as read:
curl --request PUT \
 --url https://miniflux/v1/entries \
 --header "Content-Type: application/json" \
 --header "X-Auth-Token: <api-token>" \
 --data '{ "entry_ids": [248337, 248338], "status": "read" }'
```