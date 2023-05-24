---
alias: connect-to-azuread-using-powershell
category: azure
classification: public
date: 2020-12-09 15:23:58
date_modified: null
id: 20201209152358
tags:
- azure-ad
- powershell
title: Connect to Azure AD in PowerShell
type: tech-note
uuid: c9c3add0-7a28-43e3-9cff-622b4ce0c883
---

> [!tip]
> Make sure you have run the `Install-Module AzureAD` command.

In PowerShell type `Connect-AzureAD`, and type in your credentials in the login box that pops-up.

```powershell
$ Connect-AzureAD

Account                           Environment TenantId                             TenantDomain           AccountType
-------                           ----------- --------                             ------------           -----------
jake.price@example.com AzureCloud  e1d6ec7d-132c-49c2-881f-8d398e59a311 example.com User
```