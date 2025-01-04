---
aliases:
  - access-android-directories-using-cli
category: android
classification: public
date: 2020-09-06T15:26:26
date_modified: 2020-09-06T15:26:26
draft: false
id: 20200906152626
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [android, gvfs, samsung, galaxy-s20, mtp]
title: Access Android Phone Directories On CLI
type: tech-note
---

Using the GUI, especially Nautilus to copy photos off an Android phone can be really slow, this process makes it much more reliable.

Firstly, find out where the device is mounted.

```sh
mount | grep  'gvfsd-fuse'
```

That'll return something like the below:

```sh
gvfsd-fuse on /run/user/1000/gvfs type fuse.gvfsd-fuse (rw,nosuid,nodev,relatime,user_id=1000,group_id=1000)
```

You can then `cd` all the way in to that directory.

```sh
cd /run/user/1000/gvfs/mtp:host=SAMSUNG_SAMSUNG_Android_RF8N30TLG3M/Phone
```

