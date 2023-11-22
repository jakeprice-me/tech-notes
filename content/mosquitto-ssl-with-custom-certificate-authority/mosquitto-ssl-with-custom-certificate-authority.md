---
aliases:
  - mosquitto-ssl-with-custom-certificate-authority
archive_links: https://web.archive.org/web/20230911045315/http://www.steves-internet-guide.com/mosquitto-tls/
category: smart-home
classification: public
date: 2023-11-22T12:02:20
date_modified: 2023-11-27T09:55:21
draft: false
id: 20231122120220
image: 
links:
  - http://www.steves-internet-guide.com/mosquitto-tls/
local_archive_links:
  - attachments/20231122120220.html
pinned: false
print: false
series: 
tags:
  - mosquitto
  - mqtt
  - self-signed
  - certificate-authority
title: Mosquitto SSL with Custom Certificate Authority
type: tech-note
---

It's easy enough to use a custom certificate authority when enabling SSL with Mosquitto, but as with all things `openssl` I'll never remember it by heart! 

> [!note]
> To clarify this process does not enable client authentication, you still authenticate with username and password.

So I run the following `openssl` commands.

## Certificate Authority

```sh
# Create a certificate directory:
mkdir certs && cd certs

# Create the CA key file:
$ openssl genrsa -out ca.key 2048

# Generate CA certificate:
$ openssl req -new -x509 -days 3650 -key ca.key -out ca.crt
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:GB
State or Province Name (full name) []:
Locality Name (eg, city) [Default City]:
Organization Name (eg, company) [Default Company Ltd]:Mosquitto
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your servers hostname) []:
Email Address []:
```

## Server Certificate

### Configuration File

Create a file `san.cnf` so we can specify SAN (Subject Alternative Names) on the certificate.

```ini
[req]
req_extensions = v3_req
distinguished_name = req_distinguished_name

[req_distinguished_name]

[v3_req]
subjectAltName = @alt_names

[alt_names]
DNS.1 = mosquitto.int.price.gb.net
DNS.2 = mqtt.int.price.gb.net
```

### Generate Server Certificate

```sh
# Generate server certificate key:
$ openssl genrsa -out server.key 2048

# Generate server certificate signing request:
$ openssl req -new -out server.csr -key server.key
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:GB
State or Province Name (full name) []:
Locality Name (eg, city) [Default City]:
Organization Name (eg, company) [Default Company Ltd]:
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your servers hostname) []:<mosquitto-server-url>
Email Address []:

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:

# Generate server certificate:
$ openssl x509 -req -in server.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out server.crt -days 3650 -extfile san_config.cnf -extensions v3_req
```

### Check the Certificate

Make sure the certificate looks as expected.

```sh
openssl x509 -in server.crt -text -noout
```

### Copy Certificate

Then make sure you copy `ca.crt`, `server.crt` and `server.key` to your Mosquitto certificate directory, and specify the certificates and key file in `mosquitto.conf`.

```sh
cp ca.crt server.crt server.key ../mosquitto/config/certs
```

### Use Certificate

Add the certificate to the Mosquitto configuration file, and then restart Mosquitto.

```ini
cafile /mosquitto/config/certs/ca.crt
certfile /mosquitto/config/certs/server.crt
keyfile /mosquitto/config/certs/server.key
```

## Connecting to Mosquitto Server

When connecting to the Mosquitto server you'll need to provide the CA file along with the username and password. Here's a few examples for various different services I use.

### Examples
#### CLI

```sh
docker run \
	-it \
	--volume $PWD:/home/ \
	eclipse-mosquitto:latest \
	mosquitto_sub \
	--cafile /home/certs/ca.crt \
	-h <mosquitto-server-url> \
	-t <topic-name> \
	-u <username> \
	-P <password>
```
#### Frigate

```yaml
mqtt:
  host: <mosquitto-server-url>
  port: 8883
  user: <username>
  password: <password>
  tls_ca_certs: /config/certs/ca.crt
  tls_insecure: false
```

#### Zigbee2MQTT

```yaml
mqtt:
  server: mqtts://<mosquitto-server-url>
  user: <username>
  password: <password>
  ca: /app/data/certs/ca.crt
```
