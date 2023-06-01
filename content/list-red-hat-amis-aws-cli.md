---
alias: list-red-hat-amis-aws-cli
category: aws
classification: public
date: 2019-07-17 16:10:12
date_modified: 2019-07-17 16:10:12
id: 20190717161012
link: 
pinned: false
series: 
tags: [redhat, aws, ami, cli]
title: List Red Hat AMIs using AWS CLI
type: tech-note
uuid: 3fee5dd8-4a3b-4d43-b3dc-500f0ecafd4d
---

``` sh
aws ec2 describe-images --owners 309956199498 --query 'sort_by(Images, &CreationDate)[*].[CreationDate,Name,ImageId]' --filters "Name=name,Values=RHEL-8*" --region <region> --output table
```

Make sure you leave the `owners` as is (or update it for another distro). But you can change `filters` and `region` as required.