---
alias: use-macos-privileges-app-from-the-command-line
archive_link: []
category: macos
classification: public
date: 2023-06-06 12:07:53
date_modified: 2023-06-06 12:07:53
id: 20230606120753
link: https://github.com/SAP/macOS-enterprise-privileges/wiki/Frequently-Asked-Questions#how-do-i-use-privilegesapp-in-a-script-or-from-the-command-line
local_archive: 
pinned: false
series: 
tags: [admin, sudo, privileges, cli]
title: Use MacOS Privileges App from the Command Line
type: tech-note
uuid: a71c5a70-e4ea-4c7f-8a34-fc54dfe0b2cc
---

In most places I've worked where I've had a MacBook, you can use the [Privileges](https://github.com/SAP/macOS-enterprise-privileges) application to allow you to elevate your permissions to administrator for a set period of time. It's a great option, and works really well. Turns out you can also use it from the command line, which makes it much quicker to toggle.

```sh
# Check your current privileges:
/Applications/Privileges.app/Contents/Resources/PrivilegesCLI --status

# Enable admin:
/Applications/Privileges.app/Contents/Resources/PrivilegesCLI --add

# Disable admin:
/Applications/Privileges.app/Contents/Resources/PrivilegesCLI --remove
``` 
