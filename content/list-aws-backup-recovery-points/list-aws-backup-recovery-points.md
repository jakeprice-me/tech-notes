---
aliases:
  - list-aws-backup-recovery-points
archive_links: 
category: aws
classification: public
date: 2019-10-22T14:38:50
date_modified: 2019-10-22T14:38:50
draft: false
id: 20191022143850
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [aws, backup, cli]
title: List AWS Backup Recovery Points Using AWS CLI
type: tech-note
---

To see the number of recovery points for a specific resource you first need to get the resource ARN for that resource.

For example, if you want to check recovery points for an RDS database, you can retrieve it by running the below command:

``` sh
aws rds describe-db-instances --region eu-west-2 --query 'DBInstances[].DBInstanceArn'
```

This will return the below output, containing the resource ARN's for each RDS database in the specified region.

``` json
[
    "arn:aws:rds:eu-west-2:<account-id>:db:<db-name>",
    "arn:aws:rds:eu-west-2:<account-id>:db:<db-name>",
    "arn:aws:rds:eu-west-2:<account-id>:db:<db-name>",
    "arn:aws:rds:eu-west-2:<account-id>:db:<db-name>"
]
```

We can now use these to list all recovery points that exist for a resource we pick. If we tell AWS CLI to output in `text` and pipe the results to `wc -l` we will get a line count, and because `text` output through AWS CLI doesn't include any column headers, the result we get back will be the actual number of recovery points that exist for the specified resource.

``` sh
aws backup list-recovery-points-by-resource --resource-arn arn:aws:rds:eu-west-2:<account-id>:db:<db-name> --region eu-west-2 --output text | wc -l
```

As below:

``` sh
jprice@DESKTOP-IVR4GBM [14:55:59] ~ $ > aws backup list-recovery-points-by-resource --resource-arn arn:aws:rds:eu-west-2:<account-id>:db:<db-name> --region eu-west-2 --output text | wc -l
4
```