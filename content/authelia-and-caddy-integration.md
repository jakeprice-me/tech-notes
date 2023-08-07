---
alias: authelia-and-caddy-integration
archive_link: []
category: authelia
classification: public
date: 2023-01-11 19:46:11
date_modified: 2023-01-11 19:46:11
id: 20230111194611
link: 
local_archive: 
pinned: false
series: 
tags: [authelia, caddy, security, login, authentication]
title: Authelia & Caddy Integration
type: tech-note
uuid: 30d3326a-5158-4feb-9b1d-0b6cd0d5e395
---

[TOC]

## Helpful Links

- [Authelia Tutorial - Protect your Docker Traefik stack with Private MFA | SHB](https://www.smarthomebeginner.com/docker-authelia-tutorial/)
- [Caddy - Integration - Authelia](https://www.authelia.com/integration/proxies/caddy/)
- [Docker - Integration - Authelia](https://www.authelia.com/integration/deployment/docker/)
- [Forwarded Headers - Integration - Authelia](https://www.authelia.com/integration/proxies/fowarded-headers/)
- [authelia/config.template.yml at master · authelia/authelia](https://github.com/authelia/authelia/blob/master/config.template.yml)
- [forward_auth (Caddyfile directive) — Caddy Documentation](https://caddyserver.com/docs/caddyfile/directives/forward_auth#authelia)
- [reverse_proxy (Caddyfile directive) — Caddy Documentation](https://caddyserver.com/docs/caddyfile/directives/reverse_proxy#trusted_proxies)

## Enable Authelia on a Caddy Site

```
handle @log {
    forward_auth localhost:9091 {
        uri /api/verify?rd=https://auth.int.ppn.sh
        copy_headers Remote-User Remote-Groups Remote-Name Remote-Email
    }
    reverse_proxy 10.19.90.20
}
```

## File Based User Database

```yaml
users:
  usera:
    disabled: false
    displayname: <display-name>
    password: <hashed-password>
    email: <email>
    groups:
      - admins
  userb:
    disabled: false
    displayname: <display-name>
    password: <hashed-password>
    email: <email>
    groups:
      - admins
```

## Hash a Password

```sh
docker exec -it auth-01 authelia hash-password <password>
```