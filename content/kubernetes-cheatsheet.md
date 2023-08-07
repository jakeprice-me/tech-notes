---
alias: kubernetes-cheatsheet
archive_link: []
category: kubernetes
classification: public
date: 2021-12-07 11:18:37
date_modified: 2021-12-07 11:18:37
id: 20211207111837
link: 
local_archive: 
pinned: false
series: 
tags: [cheatsheat, kubernetes, orchestration]
title: Kubernetes Cheatsheat
type: tech-note
uuid: 55604f03-789e-4730-9a76-5b665394f4f6
---

## Download & Install Kubernetes

### Create Repository

Create a new repository file:

```sh
sudo vim /etc/yum.repos.d/kubernetes.repo
```

And insert the below:

```ini
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
```

### Install kubectl

```sh
sudo dnf install kubectl
```