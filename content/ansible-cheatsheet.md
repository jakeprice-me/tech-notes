---
alias: ansible-cheatsheet
archive_links: []
category: ansible
classification: public
date: 2021-01-16 13:07:43
date_modified: 2021-01-16 13:07:43
id: 20210116130743
link: 
local_archive: 
pinned: false
series: 
tags: [ansible, cheatsheet]
title: Ansible Cheatsheet
type: tech-note
uuid: 5ac82d2b-905d-4697-8cda-12b598d2a193
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