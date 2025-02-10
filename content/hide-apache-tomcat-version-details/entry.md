---
aliases:
  - hide-apache-tomcat-version-details
category: tomcat
classification: public
date: 2020-10-10T11:57:30
date_modified: 2020-10-10T11:57:30
draft: false
id: 20201010115730
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - apache
  - security
  - tomcat
  - version
title: Hide Tomcat Version Details on 404 Page
type: tech-note
---

It's important to hide the version of Tomcat that is being used to ensure the baddies are unsure!

Create a new set of directories under the Tomcat `lib` directory:

```sh
mkdir -p /opt/apache/tomcat/lib/org/apache/catalina/util
```

Then create a new file under the newly created `util` directory called `ServerInfo.properties`, and copy the below into it:

```ini
server.info=
```

The `server.info` property takes a string, but it's better to have no information on version at all, so the above hides it completely.

Then restart Tomcat, and if you enter a bad request the version will not be included.