---
aliases:
  - stop-and-start-docker-compose-if-youve-edited-your-compose-file
archive_links:
  - https://web.archive.org/web/20240917202528/https://docs.docker.com/reference/cli/docker/compose/restart/
category: docker
classification: public
date: 2024-01-05T17:23:26
date_modified: 2024-09-23T16:47:04
draft: false
id: 20240105172326
image: 
links:
  - https://docs.docker.com/engine/reference/commandline/compose_restart/
local_archive_links:
  - attachments/20240105172326.html
pinned: false
print: false
series: 
tags:
  - docker-compose
  - restart
  - docker
  - compose
title: Stop & Start Docker Compose if You've Edited Your Compose File
type: tech-note
---

I can never remember this, so for my future self, if you change your `compose.yaml` file, and then only `docker compose restart`, those changes *will not be picked up*. You *must* `docker compose stop && docker compose up -d` instead.

> If you make changes to your `compose.yml` configuration, *these changes are not reflected after running this command*. For example, changes to environment variables (which are added after a container is built, but before the container's command is executed) are not updated after restarting.
> 
> — [docker compose restart | Docker Docs](https://docs.docker.com/engine/reference/commandline/compose_restart/)
