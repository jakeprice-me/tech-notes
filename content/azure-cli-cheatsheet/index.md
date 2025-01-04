---
aliases:
  - azure-cli-cheatsheet
category: azure
classification: public
date: 2022-07-27T16:36:06
date_modified: 2022-07-27T16:36:06
draft: false
id: 20220727163606
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [azure, command-line, cheatsheet]
title: Azure CLI Cheatsheet
type: tech-note
---

```sh
# List resource group names or id's:
az group list | jq '.[].name'

# List resource group name and id:
az group list | jq '.[]|{name,id}'

# List postgres database sku's in uk south region:
az postgres server list-skus --location uksouth | jq '.[]|.serviceLevelObjectives|.[]|{id,edition,vCore}'

# Tail App Service Slot logs:
az webapp log tail --resource-group dev --name dev-01 --slot development --provider http

# Restart App Service Slot:
az webapp restart --resource-group dev --name dev-01 --slot development 

# Find VM image offers:
az vm image list-offers --publisher Canonical --location uksouth --output table

# Find VM image skus based of an offer:
az vm image list-skus --publisher Canonical --offer 0001-com-ubuntu-server-jammy --location uksouth --output table
```

