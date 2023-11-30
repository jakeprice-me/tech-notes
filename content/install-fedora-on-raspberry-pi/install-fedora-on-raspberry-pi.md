---
aliases:
  - install-fedora-on-raspberry-pi
archive_links: 
category: raspberry-pi
classification: public
date: 2023-11-30T10:54:37
date_modified: 2023-11-30T10:54:37
draft: false
id: 20231130105437
image: 
links:
  - https://docs.fedoraproject.org/en-US/quick-docs/raspberry-pi/
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - fedora
  - raspberry-pi
  - rpi3
  - rpi4
title: Install Fedora on Raspberry Pi
type: tech-note
---

> [!warning]
> I've abandoned running Fedora on my Raspberry Pi's. Even on a 4B, for me it just runs slow, takes significantly longer to start up, and often fails to even boot on initial setup. I've gone back to Raspberry Pi OS (Lite), which always works and runs really well. 

Here's how to download an install Fedora to a Raspberry Pi, from a Fedora device.

First, download the latest version of [Fedora Server](https://fedoraproject.org/server/download) specifying the `raw.xz` image.

Then install Arm Image Installer.

```sh
sudo dnf install -y arm-image-installer
```

Get the device id of the microSD card.

```sh
lsblk
```

Specify the required values, and run the command.

```sh
sudo arm-image-installer \
	--image=<path-to-image>/Fedora-Server-39-1.5.aarch64.raw.xz \
	--target=<rpi3 or rpi4> \
	--media=/dev/<device> \
	--resizefs

# Example
sudo arm-image-installer \
      --image=/home/jprice/Downloads/Fedora-Server-39-1.5.aarch64.raw.xz \
      --target=rpi3 \
      --media=/dev/sdb \
      --resizefs
```

Follow any prompts, and once the command runs (might take around 10 minutes) you can eject the microSD card, insert it into your Raspberry Pi and wait. 

After a reboot or two, you'll be able to configure the image and set the language, timezone, a user, and then it will be good to go, for me it takes about 10 to 15 minutes to get to the configuration prompt.

I ended up also having to extend the root partition to fill the full microSD card.

```sh
sudo xfs_growfs /dev/mapper/fedora--server-root
```
