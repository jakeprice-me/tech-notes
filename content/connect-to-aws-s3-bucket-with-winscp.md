---
alias: connect-to-aws-s3-bucket-with-winscp
category: aws
classification: public
date: 2020-03-02 13:43:51
date_modified: null
id: 20200302134351
pinned: false
tags:
- s3
- aws
- winscp
- bucket
title: Connect to an AWS S3 Bucket with WinSCP
type: tech-note
uuid: d4b91bfc-8944-4da6-aa95-544ba8ea7b49
---

On the initial "Site Login" screen that opens when WinSCP is launched, fill in the below details:

```yaml
File protocol: Amazon S3
Host name: s3.amazonaws.com
Access key ID: <access-key>
Secret access key: <secret-access-key>
```

Then click on `Advanced`, navigate to `Environments > Directories` and fill in the remote directory (which is the S3 bucket name).

```yaml
Remote directory: /<bucket-name>
```