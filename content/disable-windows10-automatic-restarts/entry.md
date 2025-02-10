---
aliases:
  - disable-windows10-automatic-restarts
category: windows
classification: public
date: 2020-10-23T22:00:29
date_modified: 2024-09-23T22:12:05
draft: false
id: 20201023220029
image: 
links:
  - https://answers.microsoft.com/en-us/windows/forum/all/disable-windows-10-automatic-restart-after-updates/16f1826d-a796-4de8-ac99-1d625420d265?auth=1
local_archive_links:
  - attachments/disable-windows10-automatic-restarts.html
pinned: false
print: false
series: 
tags:
  - updates
  - windows-10
title: Disable Windows 10 Automatic Restarts after Updates
type: tech-note
---

> 1. Click on the `Start` button and type `gpedit.msc`, press Enter.
> 2. In the Local Group Policy Editor, go to `Computer Configuration -> > Administrative Templates -> Windows Components -> Windows Update`
> 3. Double-click on `No auto-restart with automatic installations of scheduled > updates`.
> 4. Select `Enabled`, and then click `OK`.
> 5. Close the local group policy editor. 
>
> — [Source](https://answers.microsoft.com/en-us/windows/forum/all/disable-windows-10-automatic-restart-after-updates/16f1826d-a796-4de8-ac99-1d625420d265?auth=1)