---
aliases:
  - mosquitto-mqtt-testing-cheatsheet
category: mosquitto
classification: public
date: 2023-08-15T09:41:46
date_modified: 2023-08-15T09:41:46
draft: false
id: 20230815094146
image: 
links:
  - https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-the-mosquitto-mqtt-messaging-broker-on-debian-10
local_archive_links:
  - attachments/mosquitto-mqtt-testing-cheatsheet.html
pinned: false
print: false
series: 
tags:
  - home-assistant
  - messaging
  - mosquitto
  - mqtt
  - publish
  - subscription
  - topic
title: Mosquitto/MQTT Testing Cheatsheet
type: tech-note
---

```sh
# Create a topic called test:
docker run --network home-assistant-01 -it eclipse-mosquitto:latest mosquitto_sub -h <mosquitto-hostname> -t test

# Create a topic called test whilst providing credentials:
docker run --network home-assistant-01 -it eclipse-mosquitto:latest mosquitto_sub -h <mosquitto-hostname> -t test -u admin -P "<mosquitto-password>"

# Send a message to the test topic:
docker run --network home-assistant-01 -it eclipse-mosquitto:latest mosquitto_pub -h <mosquitto-hostname> -t test -m "hello"

# Send a message to the test topic with credentials:
docker run --network home-assistant-01 -it eclipse-mosquitto:latest mosquitto_pub -h <mosquitto-hostname> -t test -m "hello" -u admin -P "<mosquitto-password>"

# Add a password for a user to the passwd file:
docker exec -it ha_mosquitto-01 mosquitto_passwd -c /mosquitto/config/mosquitto.passwd admin
```