---
aliases:
  - install-gnome-and-vnc-server-on-fedora
category: fedora
classification: public
date: 2024-01-01T11:14:27
date_modified: 2024-01-01T11:14:27
draft: false
id: 20240101111427
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - fedora
  - vnc
  - gnome
  - desktop-environment
title: Install GNOME and VNC Server on Fedora
type: tech-note
---

Install a VNC Server.

```sh
sudo dnf -y install tigervnc-server 
```

Add a rule to firewalld.

```sh
sudo firewall-cmd --add-service=vnc-server
sudo firewall-cmd --runtime-to-permanent 
```

As the user you're configuring a VNC session for, set a VNC password.

```sh
vncpasswd
```

Add a VNC configuration file to `~/.vnc/config`.

```ini
session=gnome
securitytypes=vncauth,tlsvnc
geometry=1920x1080
```

Then edit the main VNC server configuration file `/etc/tigervnc/vncserver.users`.

```sh
sudo vim /etc/tigervnc/vncserver.users 
```

Add your user and assign to the first display.

```ini
:1=fedora
```

Now start the server.

```sh
sudo systemctl enable --now vncserver@:1
```

You can now access the server on port `5901` in your VNC client of choice.
