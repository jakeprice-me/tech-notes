---
aliases:
  - list-red-hat-amis-aws-cli
archive_links: 
category: aws
classification: public
date: 2019-07-17T16:10:12
date_modified: 2019-07-17T16:10:12
draft: false
id: 20190717161012
link: 
local_archive: 
pinned: false
print: false
series: 
tags: [redhat, aws, ami, cli]
title: List Red Hat AMIs using AWS CLI
type: tech-note
---

``` sh
aws ec2 describe-images --owners 309956199498 --query 'sort_by(Images, &CreationDate)[*].[CreationDate,Name,ImageId]' --filters "Name=name,Values=RHEL-8*" --region <region> --output table
```

Make sure you leave the `owners` as is (or update it for another distro). But you can change `filters` and `region` as required.