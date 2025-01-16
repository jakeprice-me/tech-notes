---
aliases:
  - local-lan-certificate
category: openssl
classification: public
date: 2021-08-13T18:14:04
date_modified: 2021-08-13T18:14:04
draft: false
id: 20210813181404
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - certificate
  - certificate-authority
title: Local LAN Certificate
type: tech-note
---

## OpenSSL

Make sure `/etc/ssl/openssl.cnf` has the following:

```ini
# Add to [ req ]:
x509_extensions = v3_ca

# Add to file:
[ v3_ca ]
basicConstraints = critical,CA:TRUE
subjectKeyIdentifier = hash
authorityKeyIdentifier = keyid:always,issuer:always
```

## Root Certificate

```sh
# Create directory structure:
mkdir -p ~/onedrive/security/local-ca/{certificates,private-keys}

# Create root certificate using v3_ca extension:
openssl req \
    -x509 \
    -newkey rsa:4096 \
    -keyout ~/onedrive/security/local-ca/private-keys/local_root_ca_key.pem \
    -nodes \
    -days 10950 \
    -sha256 \
    -extensions v3_ca \
    -subj "/C=GB/ST=LAN/L=LAN/O=Local Certificate Authority/CN=Local Root CA" \
    -out ~/onedrive/security/local-ca/certificates/local_root_ca_cert.pem
```

## V3 Extension

Create `~/onedrive/security/local-ca/v3.ext`.

```ini
[req]
req_extensions = v3_req

[ v3_req ]
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

[alt_names]
DNS.1 = *.local.lan
DNS.2 = local.lan
```

## Wildcard Certificate

> [!tip]
> On MacOS you have to use `sudo` for the final certificate creation command otherwise you get an error with the `srl` file not being accessible.

```sh
# Create key:
openssl req \
    -new \
    -newkey rsa:4096 \
    -nodes \
    -keyout ~/onedrive/security/local-ca/private-keys/local_lan_key.pem \
    -subj "/C=GB/ST=LAN/L=LAN/O=Local LAN/CN=*.local.lan" \
    -out ~/onedrive/security/local-ca/certificates/local_lan_csr.pem

# Create certificate:
sudo openssl x509 \
    -req \
    -in ~/onedrive/security/local-ca/certificates/local_lan_csr.pem \
    -extfile ~/onedrive/security/local-ca/v3.ext \
    -extensions v3_req \
    -CA ~/onedrive/security/local-ca/certificates/local_root_ca_cert.pem \
    -CAkey ~/onedrive/security/local-ca/private-keys/local_root_ca_key.pem \
    -CAcreateserial \
    -out ~/onedrive/security/local-ca/certificates/local_lan_cert.pem \
    -days 365 \
    -sha256
```
