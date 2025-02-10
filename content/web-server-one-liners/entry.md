---
aliases:
  - web-server-one-liners
category: cli
classification: public
date: 2020-12-25T21:58:32
date_modified: 2020-12-25T21:58:32
draft: false
id: 20201225215832
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - android
  - php
  - python
  - termux
  - web-server
title: Web Server One Liners
type: tech-note
---

Some very handy one line commands for starting a web server for testing and development.

Run the command in the directory you wish to serve, or where provided, supply a flag for the directory.

Most of these should also work on Android via Termux (if the language can be installed).

```sh
php -S localhost:8000
python -m http.server 8000
```

After starting the web server, you can access content at [127.0.0.1:8000](http://127.0.0.1:8000).