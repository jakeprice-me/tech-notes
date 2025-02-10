---
aliases:
  - manage-ec2-keypairs-aws-cli
category: aws
classification: public
date: 2020-08-26T15:25:49
date_modified: 2020-08-26T15:25:49
draft: false
id: 20200826152549
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - aws
  - command-line
  - ec2
  - keys
  - ssh
title: Manage EC2 KeyPairs with the AWS CLI
type: tech-note
---

## Create a Key Pair

The below will create a keypair and save it to your SSH folder.

```sh
aws ec2 create-key-pair --profile "<profile>" --region "<region>" --query "KeyMaterial" --output "text" --key-name "<key_name>" > ~/.ssh/<key_name>
```

## Delete a Key Pair

```sh
aws ec2 create-key-pair --profile "<profile>" --region "<region>" --key-name "<key_name>"
```