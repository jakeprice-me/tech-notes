---
alias: code-server-port-change-ignored
category: self-hosted
classification: public
date: 2022-02-08 13:13:24
date_modified: 2022-02-08 13:13:24
id: 20220208131324
link: 
link_archive: 
pinned: false
series: 
tags: [code-server, port, bind, mount, docker]
title: Code Server Port Bind Issue
type: tech-note
uuid: 26caed21-38f4-4ead-9645-4f3330334870
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