---
aliases:
  - speed-up-powershell-invoke-webrequest
archive_links: 
category: powershell
classification: public
date: 2020-08-14T15:18:44
date_modified: 2020-08-14T15:18:44
draft: false
id: 20200814151844
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [windows, powershell]
title: Speed Up PowerShell Invoke-WebRequest
type: tech-note
---

If you don't disable the progress bar when downloading a file using `Invoke-WebRequest` on Windows PowerShell, it will take significantly longer to download. 

To disable it run the below:

```powershell
$ProgressPreference = 'SilentlyContinue'
Invoke-WebRequest <params>
```

The `$ProgressPreference` variable will only last as long as the current PowerShell session.