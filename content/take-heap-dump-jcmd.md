---
alias: take-heap-dump-jcmd
category: java
classification: public
date: 2020-07-16 14:10:43
date_modified: 2020-07-16 14:10:43
id: 20200716141043
link: 
link_archive: 
pinned: false
series: 
tags: [jcmd, heap-dump, java, digi]
title: Take a heap-dump using jcmd
type: tech-note
uuid: 76d1b1cb-906a-45cb-9dab-89f0b56730b1
---

Take a heap-dump using `jcmd`:

```sh
jcmd <pid> GC.heap_dump <file-path>

$ > jcmd 11024 GC.heap_dump /tmp/202007161407_heap_dump
11024:
Heap dump file created
```

You can get the pid by just running:

```sh
$ > jcmd
14298 sun.tools.jcmd.JCmd
12124 org.apache.catalina.startup.Bootstrap start
```
