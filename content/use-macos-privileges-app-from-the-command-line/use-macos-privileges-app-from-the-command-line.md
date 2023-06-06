---
aliases:
  - use-macos-privileges-app-from-the-command-line
archive_links: 
category: macos
classification: public
date: 2023-06-06T12:07:53
date_modified: 2023-06-06T12:07:53
draft: false
id: 20230606120753
image: 
links:
  - https://github.com/SAP/macOS-enterprise-privileges/wiki/Frequently-Asked-Questions#how-do-i-use-privilegesapp-in-a-script-or-from-the-command-line
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - admin
  - sudo
  - privilege
  - cli
  - github
title: Use MacOS Privileges App from the Command Line
type: tech-note
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
