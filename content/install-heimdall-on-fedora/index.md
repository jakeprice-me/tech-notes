---
aliases:
  - install-heimdall-on-fedora
category: android
classification: public
date: 2022-12-19T13:08:30
date_modified: 2024-09-23T19:06:06
draft: false
id: 20221219130830
image: 
links:
  - https://github.com/Benjamin-Dobell/Heimdall/wiki/Build-instructions-(Linux)#fedora
local_archive_links:
  - attachments/20221219130830.html
pinned: false
print: false
series: 
tags:
  - android
  - heimdall
  - linux
  - odin
  - samsung
  - flash
  - image
  - firmware
  - github
title: Install Heimdall on Fedora
type: tech-note
---

> [!warning]
> Doing this is all well and good, but it's impossible to use - because there's no documentation on how to map the partitions to the files you should upload! Unfortunately Odin on Windows remains the simplest way to flash firmware for Samsung devices.

## Prerequisites

```sh
sudo dnf groupinstall "Development Tools"
sudo dnf install libusb1-devel qt-devel libtool
sudo dnf install cmake glibc libusb zlib gcc qt5-qtbase-devel
```

## Build

```sh
git clone git@github.com:Benjamin-Dobell/Heimdall.git
cd Heimdall
mkdir -p build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make
sudo cp bin/* /usr/local/bin
```

## Run

Start Heimdall by running `heimdall` or `heimdall-frontend` from the terminal.

