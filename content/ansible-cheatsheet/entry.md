---
aliases:
  - ansible-cheatsheet
category: ansible
classification: public
date: 2021-01-16T13:07:43
date_modified: 2021-01-16T13:07:43
draft: false
id: 20210116130743
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - ansible
  - cheatsheet
title: Ansible Cheatsheet
type: tech-note
---

## Ansible Roles

```sh
# New Role:
ansible-galaxy role init <role-name>
```

## Ansible Playbooks

```sh
# Run Playbook with Extra Variables:
ansible-playbook --extra-vars host_group=<host-name> <playbook>.yml
```