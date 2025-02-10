---
aliases:
  - why-use-packer
category: packer
classification: public
date: 2021-02-28T11:15:14
date_modified: 2021-02-28T11:15:14
draft: false
id: 20210228111514
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - ami
  - ansible
  - configuration
  - devops
  - image
  - packer
title: Why Packer?
type: tech-note
---

This is a good comment from Reddit on why you should use Packer.

> Packer puts the config work into the image prior to deployment. This allows for ec2s or VMs to start much faster in time-critical situations. Sometimes installing packages on first boot can take a long time for networking and internet access to be ready. Then each vm has to do this configuration on each deploy. Putting config first you only pay the price to configure once, then you can deploy many times.
>
> Doing config first also removes dependencies from deployment. The starting VMs don't need access to external repos (or the internet), etc. So it's easier to lock them down.
>
> Baking images with packer also allows you to ensure all VMs are configured exactly the same (same package versions, CLI versions, etc) because they are created from the same image. Occasionally configuring after will run into issues with incomplete config runs so 2 VMs may be different even when they should be the same.
>
> — TheRealKingGordon [Why Packer?](https://www.reddit.com/r/devops/comments/ko3cwq/why_packer/gho2u06?utm_source=share&utm_medium=web2x&context=3)