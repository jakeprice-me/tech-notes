---
aliases:
  - code-server-port-change-ignored
category: self-hosted
classification: public
date: 2022-02-08T13:13:24
date_modified: 2022-02-08T13:13:24
draft: false
id: 20220208131324
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - bind
  - code-server
  - docker
  - mount
  - port
title: Code Server Port Bind Issue
type: tech-note
---

If you want to change the port [Code Server](https://github.com/coder/code-server) uses, it's hard-coded into the `/etc/services.d/code-server/run` script, as a value for the `--bind-addr` flag.

```sh
#!/usr/bin/with-contenv bash

if [ -n "${PASSWORD}" ] || [ -n "${HASHED_PASSWORD}" ]; then
    AUTH="password"
else
    AUTH="none"
    echo "starting with no password"
fi

if [ -z ${PROXY_DOMAIN+x} ]; then
    PROXY_DOMAIN_ARG=""
else
    PROXY_DOMAIN_ARG="--proxy-domain=${PROXY_DOMAIN}"
fi

exec \
    s6-setuidgid abc \
        /app/code-server/bin/code-server \
            --bind-addr 0.0.0.0:8088 \
            --user-data-dir /config/data \
            --extensions-dir /config/extensions \
            --disable-telemetry \
            --auth "${AUTH}" \
            "${PROXY_DOMAIN_ARG}" \
            "${DEFAULT_WORKSPACE:-/config/workspace}"
```

I mount the file in Docker Compose so I can override `--bind-addr`:

```yml
    volumes:
      - ./run:/etc/services.d/code-server/run
```