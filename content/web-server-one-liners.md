---
alias: web-server-one-liners
archive_link: []
category: cli
classification: public
date: 2020-12-25 21:58:32
date_modified: 2020-12-25 21:58:32
id: 20201225215832
link: 
local_archive: 
pinned: false
series: 
tags: [web-server, python, php, android, termux]
title: Web Server One Liners
type: tech-note
uuid: 59b3e23e-73cd-4414-9972-f1ed90dfc040
---

Some very handy one line commands for starting a web server for testing and development.

Run the command in the directory you wish to serve, or where provided, supply a flag for the directory.

Most of these should also work on Android via Termux (if the language can be installed).

```sh
php -S localhost:8000
python -m http.server 8000
```

After starting the web server, you can access content at [127.0.0.1:8000](http://127.0.0.1:8000).