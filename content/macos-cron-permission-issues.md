---
alias: macos-cron-permission-issues
archive_link: []
category: macos
classification: public
date: 2022-11-18 14:48:22
date_modified: 2023-05-11 09:40:21
id: 20221118144822
link: 
local_archive: 
pinned: false
series: 
tags: [cron, macos, permission, hugo]
title: macOS cron Permission Issues
type: tech-note
uuid: 0d14c4c9-fb77-4a5e-a3a1-f50e39bfc37f
---

I use macOS at work, and I have a number of cron jobs that I set to run. 

One of the jobs run's on a regular basis, and is supposed to delete the `public/` directory of a Hugo static site, and then rebuild the site. Trouble is it always fails to remove the directory because it doesn't have permissions to do it.

```sh
rm: /Users/jprice/drive/my/files/documents/log/public: Operation not permitted
```

It's a "simple" enough fix. To get around it you have to give `/usr/sbin/cron` _Full Disk Access_ in macOS. 

!!! note
	You'll need to run `Cmd-Shift-G` to bring up a "Go-To" box to get to the `/usr/sbin` directory.

To do that go to "System Settings > Privacy & Security > Full Disk Access", and click to the `+` to add `cron`. There's no command you can run to do this in one it seems ☹️ and you'll need admin permissions.