---
aliases:
  - typesense-cheatsheet
archive_links: 
category: typesense
classification: public
date: 2021-08-03T11:01:15
date_modified: 2024-05-22T10:19:56
draft: false
id: 20210803110115
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - search
  - typesense
  - cheatsheet
title: Typesense Cheatsheet
type: tech-note
---

```sh
# Run container:
docker run -p 8108:8108 -v/tmp:/data typesense/typesense:0.21.0 --data-dir /data --api-key=xyz

# Create collection:
curl --insecure --request POST 'http://localhost:8108/collections' --header 'content-type: application/json' --header "X-TYPESENSE-API-KEY: xyz" --data-binary '{
    "name": "log",
    "fields": [
        { "name": "id", "type": "string" },
        { "name": "uuid", "type": "string" },
        { "name": "title", "type": "string" },
        { "name": "date", "type": "string" },
        { "name": "tags", "type": "string[]" },
        { "name": "url", "type": "string" },
        { "name": "content", "type": "string" }
    ]
}' | jq '.'

# List collection:
curl --header "X-TYPESENSE-API-KEY: xyz" "http://localhost:8108/collections" | jq '.'

# Get Index:
wget --no-check-certificate https://log.ark.lan/index.json --output-document=log.json

# Convert to JSONL:
cat log.json | jq --compact-output '.[]' > log.jsonl

# Import document:
curl --insecure --header "X-TYPESENSE-API-KEY: xyz" --header 'content-type: application/json' --request POST "http://localhost:8108/collections/log/documents/import?action=create" --data-binary @log.jsonl | jq '.'

# Drop collection field:
curl --request PATCH \
  --url http://localhost:8108/collections/universal-search \
  --header 'X-TYPESENSE-API-KEY: xyz' \
  --data '{
	"fields": [
		{
			"name": "local_archive",
			"drop": true
		}
	]
}'

# Drop collection:
curl --header "X-TYPESENSE-API-KEY: xyz" --request DELETE "http://localhost:8108/collections/log" | jq '.'

# Search:
curl --header "X-TYPESENSE-API-KEY: xyz" "http://localhost:8108/collections/log/documents/search?q=<query>&query_by=title" | jq '.'
```

