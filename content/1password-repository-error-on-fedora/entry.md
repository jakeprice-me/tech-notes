---
aliases:
  - 1password-repository-error-on-fedora
category: fedora
classification: public
date: 2025-02-19T09:44:49
date_modified: 2025-02-19T09:44:49
draft: false
id: 20250219094449
image: 
links: https://discussion.fedoraproject.org/t/import-gpg-key-for-rpm-ostree-repositories/78663/
local_archive_links: attachments/1password_repository_error_on_fedora.html
pinned: false
print: false
series: 
tags:
  - fedora
  - dnf
  - yum
  - repository
  - 1password
  - key
  - signature
title: 1Password Repository Error on Fedora
type: tech-note
---

After a new install of Fedora (v41), I was getting an annoying error after installing 1Password, following the instructions [here](https://support.1password.com/install-linux/#fedora-or-red-hat-enterprise-linux).

The error is shown below.

```sh
Failed to search for file: cannot update repo '1password': repomd.xml GPG signature verification error: Signing key not found
```

I found [this page]() with the following solution:

> This sounds ridiculous-- but I was able to get the 1password repo file to work by just removing the quotes around the gpgfile value.

So I updated `/etc/yum.repos.d/1password.repo` to remove the quotes surrounding `gpgkey` and... it worked! Weird.

```sh
$ cat /etc/yum.repos.d/1password.repo
[1password]
name=1Password Stable Channel
baseurl=https://downloads.1password.com/linux/rpm/stable/$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://downloads.1password.com/linux/keys/1password.asc
```
