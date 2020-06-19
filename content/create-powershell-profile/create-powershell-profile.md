---
aliases:
  - create-powershell-profile
archive_links: 
category: powershell
classification: public
date: 2020-06-19T11:57:42
date_modified: 2020-06-19T11:57:42
draft: false
id: 20200619115742
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [powershell, profile, windows]
title: Create a PowerShell Profile
type: tech-note
---

```powershell
# Check if profile already exists:
Test-Path $profile

# Create a profile if above returns false:
New-Item -path $profile -type file –force

# Profile created at below path, ready for editing:
C:\Users\<username>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```
