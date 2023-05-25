---
alias: resize-an-ec2-linux-file-system-on-aws
category: aws
classification: public
date: 2019-08-20 10:59:10
date_modified: null
id: 20190820105910
pinned: false
tags: [linux, aws, ec2, filesystem]
title: Resize an EC2 Linux File System on AWS
type: tech-note
uuid: efa775f0-991e-46eb-9730-966f37dc8dfe
---

If you need to resize an EC2 instance, or an additional mounted volume in AWS.

To unmount the drive, you may need to comment out the entry for it in `/etc/fstab` otherwise it'll be in use when it starts up. Do this, then restart, check it's not mounted and run `sudo e2fsck -f /dev/xvdh` then if all clean `sudo resize2fs /dev/xvdh` you can then check it's extended with `df -h`