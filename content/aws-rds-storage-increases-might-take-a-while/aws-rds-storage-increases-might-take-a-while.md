---
aliases:
  - aws-rds-storage-increases-might-take-a-while
category: aws
classification: public
date: 2020-10-13T12:45:24
date_modified: 2020-10-13T12:45:24
draft: false
id: 20201013124524
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [rds, terraform, aws, storage, capacity, disk, drive]
title: RDS Storage Increases Might Take a While
type: tech-note
---

An increase to the storage of a big RDS instance at work took 38 minutes to complete via Terraform. It was an increase from 300 GiB to 500 GiB.

This is something to bare in mind. Apparently there's always potential for RDS database storage increases to take a good while, as detailed here: [Troubleshoot an Amazon RDS DB Instance That Is Stuck in the Modifying State When Trying to Increase the Allocated Storage](https://aws.amazon.com/premiumsupport/knowledge-center/rds-stuck-modifying/)

