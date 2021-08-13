---
aliases:
  - openssl-on-macos-configuration
archive_links: 
category: openssl
classification: public
date: 2021-08-13T16:11:21
date_modified: 2021-08-13T16:11:21
draft: false
id: 20210813161121
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [openssl, macos]
title: OpenSSL on MacOS
type: tech-note
---

`/etc/ssl/openssl.cnf` should have the below by default on Fedora at least, but on MacOS it doesn't and has to be added.

```ini
[ v3_ca ]
basicConstraints = critical,CA:TRUE
subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid:always,issuer:always
```

Also, append:

```ini
x509_extensions = v3_ca
```

To the end of `[ req ]`.