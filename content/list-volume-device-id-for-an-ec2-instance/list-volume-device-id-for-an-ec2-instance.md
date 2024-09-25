---
aliases:
  - list-volume-device-id-for-an-ec2-instance
archive_links: 
category: aws
classification: public
date: 2019-12-24T13:18:00
date_modified: 2019-12-24T13:18:00
draft: false
id: 20191224131800
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [aws-cli, ec2, ebs]
title: List Volume Device ID for an EC2 Instance
type: tech-note
---

List the ID of a volume attached to an EC2 instance, using the AWS CLI.

``` sh
$ aws ec2 describe-volumes --filters "Name=attachment.instance-id,Values=<instance-id>" --query "Volumes[].Attachments[].{DeviceName:Device}" --region <region> --output text
```

