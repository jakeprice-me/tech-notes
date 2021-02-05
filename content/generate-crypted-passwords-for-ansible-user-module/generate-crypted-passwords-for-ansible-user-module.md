---
aliases:
  - generate-crypted-passwords-for-ansible-user-module
archive_links: 
category: ansible
classification: public
date: 2021-02-05T14:19:32
date_modified: 2021-02-05T14:19:32
draft: false
id: 20210205141932
image: 
links:
  - https://www.lisenet.com/2019/ansible-generate-crypted-passwords-for-the-user-module/
local_archive_links: 
pinned: false
print: false
series: 
tags: [ansible, user, module, crypted, vault, password, credentials]
title: Generate Crypted Passwords for the Ansible User Module
type: tech-note
---

[Local Source](20210205141932.html)

[Ansible: Generate Crypted Passwords for the User Module | Lisenet.com :: Linux | Security | Networking](https://www.lisenet.com/2019/ansible-generate-crypted-passwords-for-the-user-module/)
---

The user module can be used to create user accounts and set passwords.

## The Problem

How to use the user module to set passwords for Linux accounts? This is something that took me a while to figure out. Luckily, there is a reference to Ansible FAQ in `ansible-doc`.

## The Solution: Hashing Filters

The answer is taken from Ansible FAQ. To get a sha512 password hash with random salt, we can use the following:

```python
{{ 'password' | password_hash('sha512') }}
```

Let us store the plaintext password in Ansible vault:

```shell
$ ansible-vault view my_vault.yml
Vault password:
my_password: myPlaintextPassword
```

Our playbook that uses the vault file `my_vault.yml` will look something like this:

```yaml
---
- name: Create New Users
  hosts: all
  become: true
  gather_facts: false
  vars_files:
    - my_vault.yml
  tasks:
    - name: Create Users
      user:
        name: "{{ item }}"
        password: "{{ my_password | password_hash('sha512') }}"
        shell: /bin/bash
      loop:
        - alice
        - vincent
```

Note that while the playbook does the job, it’s not idempotent. The password hash will be generated every time the playbook is run, and the `/etc/shadow` file will be updated.

To make the playbook idempotent, set `update_password: on_create`. This will only set the password for newly created users.

```yaml
---
- name: Create New Users
  hosts: all
  become: true
  gather_facts: false
  vars_files:
    - my_vault.yml
  tasks:
    - name: Create Users
      user:
        name: "{{ item }}"
        password: "{{ my_password | password_hash('sha512') }}"
        shell: /bin/bash
        update_password: on_create
      loop:
        - alice
        - vincent
```