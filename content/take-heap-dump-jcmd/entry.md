---
aliases:
  - take-heap-dump-jcmd
category: java
classification: public
date: 2020-07-16T14:10:43
date_modified: 2020-07-16T14:10:43
draft: false
id: 20200716141043
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - heap-dump
  - java
  - jcmd
title: Take a heap-dump using jcmd
type: tech-note
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