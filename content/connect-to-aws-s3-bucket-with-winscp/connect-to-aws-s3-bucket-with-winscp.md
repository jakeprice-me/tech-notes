---
aliases:
  - connect-to-aws-s3-bucket-with-winscp
archive_links: 
category: aws
classification: public
date: 2020-03-02T13:43:51
date_modified: 2020-03-02T13:43:51
draft: false
id: 20200302134351
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [s3, aws, winscp, bucket]
title: Connect to an AWS S3 Bucket with WinSCP
type: tech-note
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

