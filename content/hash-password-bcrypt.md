---
alias: hash-password-bcrypt
category: cli
classification: public
date: 2023-01-11 08:49:41
date_modified: 2023-01-11 08:49:41
id: 20230111084941
link: https://unix.stackexchange.com/a/419855/331627
link_archive: 
pinned: false
series: 
tags: [bcrypt, hash, password, caddy-security]
title: Hash a Password using bcrypt
type: tech-note
uuid: 7ec82f91-6c72-4eea-90ad-34fb48578438
---

It's surprisingly not that straightforward to find a tool to create a bcrypt hashed password.

```sh
htpasswd -bnBC 10 "" <password> | tr -d ':\n' | sed 's/$2y/$2a/'
```

To do it with a password prompt:

```sh
htpasswd -nBC 10 jprice | tr -d ':\n' | sed 's/$2y/$2a/'
```

More on [StackExchange](https://unix.stackexchange.com/a/419855/331627)