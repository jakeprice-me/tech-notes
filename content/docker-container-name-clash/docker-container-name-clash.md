---
aliases:
  - docker-container-name-clash
archive_links:
  - https://web.archive.org/web/20211128170228/https://stackoverflow.com/questions/55031169/docker-php-fpm-nginx-sometimes-files-not-found-on-php-file/55040196
category: docker
classification: public
date: 2022-06-01T16:38:01
date_modified: 2022-06-01T16:38:01
draft: false
id: 20220601163801
image: 
links:
  - https://stackoverflow.com/a/55040196/9625225
local_archive_links:
  - attachments/20220601163801.html
pinned: false
print: false
series: 
tags:
  - php
  - docker
  - caddy
title: Regular File Not Found Error PHP Container
type: tech-note
---

I was having an issue launching another PHP application on the same device with Docker Compose. 

> You are having this issue because you have more than one container with same hostname (php) in same network.

![](attachments/20220601163801.html)

As the above makes clear, it was because I had copied the `compose.yml` and used the same service name for the PHP container in Compose and the Caddyfile. Changing `php` to `<app-name>-php` in both Compose and Caddyfile fixed it.

#### Photos

##### Compose

```yaml
  php:
    image: php-with-extensions:7.4
    container_name: photos-01-php-fpm
```

##### Caddyfile

```
:8091 {
    root * /media/photos
    file_server
    php_fastcgi php:9000
}
```

#### List

##### Compose

```yaml
  php:
    image: php-with-extensions:7.4
    container_name: list-01-php-fpm
```

##### Caddyfile

```
:8098 {
    root * /var/www/html
    file_server
    php_fastcgi php:9000
}
```