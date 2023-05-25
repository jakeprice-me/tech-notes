---
alias: speed-up-powershell-invoke-webrequest
category: powershell
classification: public
date: 2020-08-14 15:18:44
date_modified: null
id: 20200814151844
pinned: false
tags: [windows, powershell]
title: Speed Up PowerShell Invoke-WebRequest
type: tech-note
uuid: ac8a218b-2e69-4ce7-a2c2-00d0d2b80cb8
---

If you don't disable the progress bar when downloading a file using `Invoke-WebRequest` on Windows PowerShell, it will take significantly longer to download. 

To disable it run the below:

```powershell
$ProgressPreference = 'SilentlyContinue'
Invoke-WebRequest <params>
```

The `$ProgressPreference` variable will only last as long as the current PowerShell session.