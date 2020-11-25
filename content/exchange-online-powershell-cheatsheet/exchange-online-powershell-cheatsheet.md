---
aliases:
  - exchange-online-powershell-cheatsheet
archive_links: 
category: powershell
classification: public
date: 2020-11-25T17:21:11
date_modified: 2020-11-25T17:21:11
draft: false
id: 20201125172111
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [exchange, azure, office, powershell]
title: Exchange Online PowerShell
type: tech-note
---

## Connect to Exchange Online PowerShell

```powershell
# Install module:
Install-Module -Name ExchangeOnlineManagement -RequiredVersion 2.0.3 -Confirm:$false

# Load the EXO V2 module:
Import-Module ExchangeOnlineManagement

# Connect to Exchange Online PowerShell:
Connect-ExchangeOnline -UserPrincipalName jake.price@example.com -ShowProgress $true
```

## Helpful Commands:

```powershell
# Remove user's photo:
Remove-UserPhoto -Identity <user>@example.com -Confirm:$false
```
