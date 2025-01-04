---
aliases:
  - caddy-certificate-renewal-no-memory-of-presenting-a-dns-record
category: caddy
classification: public
date: 2024-10-17T22:13:32
date_modified: 2024-10-17T22:13:32
draft: false
id: 20241017221332
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - caddy
  - certificate
  - https
  - error
  - namecheap
  - dns
  - txt
  - validation
title: Caddy Certificate Renewal - No memory of presenting a DNS record
type: tech-note
---

I've just experienced an issue with Caddy that I've not seen before.

I was puzzled for a good hour as to what was going on and why the below errors were showing in the logs when Caddy tried to renew the certificate. I couldn't find anything that helped on Google either, and as a result ChatGPT was of absolutely no use whatsoever!

I eventually found a long list of TXT records in my DNS records on Namecheap which were annoyingly hidden below a "Show more" button in the Namecheap console (should have used `dig`!) which is how I figured out what was happening. 

I didn't spend too much time figuring out *why* this was happening as I just wanted it to work, so forgive me if my conclusion is wrong, but it seems like Caddy was attempting to create a new TXT record and then losing track of it, or hitting up against some Namecheap API rate limit, and it was doing this over and over again as it tried, but then failed to renew the certificate.

I deleted the TXT records in the Namecheap console (well over 20 of them) hoping that this would "reset" things, and then restarted Caddy and it sailed through the certificate renewal this time.

```sh
reverse-proxy  | {"level":"info","ts":1729199457.906333,"logger":"tls.obtain","msg":"obtaining certificate","identifier":"REDACTED"}
reverse-proxy  | {"level":"info","ts":1729199458.7305727,"logger":"http.acme_client","msg":"trying to solve challenge","identifier":"REDACTED","challenge_type":"dns-01","ca":"https://acme-staging-v02.api.letsencrypt.org/directory"}
reverse-proxy  | {"level":"error","ts":1729199459.2351894,"logger":"http.acme_client","msg":"cleaning up solver","identifier":"REDACTED","challenge_type":"dns-01","error":"no memory of presenting a DNS record for \"_acme-challenge.REDACTED\" (usually OK if presenting also failed)"}
reverse-proxy  | {"level":"error","ts":1729199459.3755682,"logger":"tls.obtain","msg":"could not get certificate from issuer","identifier":"REDACTED","issuer":"acme-v02.api.letsencrypt.org-directory","error":"[REDACTED] solving challenges: presenting for challenge: adding temporary record for zone \"REDACTED.\": expected element type <ApiResponse> but have <html> (order=https://acme-staging-v02.api.letsencrypt.org/acme/order/REDACTED) (ca=https://acme-staging-v02.api.letsencrypt.org/directory)"}
```

It's also worth mentioning that I also saw the below `caddy_legacy_user_removed` error a few times in the logs whilst this was happening. There is little online about what may cause this error too, so it may have been related to the above, but I wanted to include it for anybody that may experience it in the future.

```
reverse-proxy  | {"level":"error","ts":1729202159.135929,"logger":"tls.obtain","msg":"could not get certificate from issuer","identifier":"REDACTED","issuer":"acme.zerossl.com-v2-DV90","error":"account pre-registration callback: failed getting EAB credentials: HTTP 422: caddy_legacy_user_removed (code 2977)"}
```
