---
aliases:
  - install-jellyfin-app-on-samsung-smart-tv-running-tizen
category: samsung
classification: public
date: 2023-12-07T17:23:20
date_modified: 2024-05-14T22:46:56
draft: false
id: 20231207172320
image: 
links: 
local_archive_links:
  - attachments/20231207172320.html
pinned: false
print: false
series: 
tags:
  - samsung
  - tizen
  - jellyfin
  - app
title: Install Jellyfin App on Samsung Smart TV running Tizen
type: tech-note
---

> [!important]
> As of 2024-08-17, see [[jellyfin-on-tizen-issue]] Jellyfin on Tizen no longer consistently works on my old Samsung TV, probably because of an expired root certificate on the TV itself.

> [!important]
> As of 2042-05-14, the latest release of the Tizen app for 10.9.0, does not go past a grey screen with a top-bar showing the time on the right side. So the current version installed to the TV is https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/download/2024-05-04-1137/Jellyfin.wgt
> 
> It's easy enough to delete, install and revert - and seeing as though 10.9.0 is only a few days old, I may try again a month from now.

Initially I tried to follow the instructions [here](https://github.com/jeppevinkel/jellyfin-tizen-builds) but ran into multiple issues just trying to install the Tizen SDK (tried both Fedora and Windows with various issues).

Then I discovered [Georift/install-jellyfin-tizen](https://github.com/Georift/install-jellyfin-tizen) and after facing the issue decribed [here](https://github.com/Georift/install-jellyfin-tizen/issues/9) using the below command I was able to install Jellyfin directly onto my Samsung Smart TV (from 2016).

## Installation

Before I did this I had to enable Developer Mode on the TV itself, which is as simple as going to the Apps screen, typing in `12345` on the control, and then toggling Developer Mode on, and entering the IP of the device you'll be connecting from. Also described [here](https://developer.samsung.com/smarttv/develop/getting-started/using-sdk/tv-device.html#Connecting-the-TV-and-SDK) with pictures.

Once you've done that and restarted the TV (turn it off and then on - there's no restart button), you can simply run this from your device, making sure to enter the IP address of the TV.

```sh
docker run -it --ulimit nofile=122880:122880 -m 3G --rm georift/install-jellyfin-tizen <tv-ip-address>
```

I've included the output below. It took 45 seconds to complete.

```
        Thanks to https://github.com/jeppevinkel for providing the pre-packaged jellyfin-tizen builds!
        These builds can be found at https://github.com/jeppevinkel/jellyfin-tizen-builds


Attempting to connect to Samsung TV at IP address 10.19.90.136
* Server is not running. Start it now on port 26099 *
* Server has started successfully *
connecting to 10.19.90.136:26101 ...
connected to 10.19.90.136:26101
Attempting to get the TV name...
Found TV name: UE49KU6670
Attempting to install jellyfin-tizen-builds version:
https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/tag/2023-11-29
Jellyfin.wgt                                        100%[===================================================================================================================>]  42.65M  20.1MB/s    in 2.1s
Transferring the package...
Transferred the package: /home/developer/Jellyfin.wgt -> /opt/usr/apps/tmp
Installing the package...
--------------------
Platform log view
--------------------
install AprZAARz4r.Jellyfin
package_path /opt/usr/apps/tmp/Jellyfin.wgt
app_id[AprZAARz4r.Jellyfin] install start
was_install_app return WAS_TRUE
app_id[AprZAARz4r.Jellyfin] install completed
spend time for wascmd is [19119]ms
cmd_ret:0
Installed the package: Id(AprZAARz4r.Jellyfin)
Tizen application is successfully installed.
Total time: 00:00:45.782
```

## Upgrade

To upgrade run the same command for the install, but delete the app from the TV first.

## Downgrade

Once again, delete the app first, then clone `git@github.com:Georift/install-jellyfin-tizen.git` and update the `entrypoint.sh` as follows.

```sh
# COMMENT BELOW OUT:
#echo "Attempting to install jellyfin-tizen-builds version:"
#curl -v location: https://github.com/jeppevinkel/jellyfin-tizen-#builds/releases/latest 2>&1 | \
#	grep "< location:" | \
#	sed -e 's/< location: //g'

# CHANGE THIS TO LINK TO THE DOWNGRADED RELEASE
wget -q --show-progress https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/download/2024-05-04-1137/Jellyfin.wgt
```

Then build the `Dockerfile` from within the repository.

```sh
docker build --tag local/install-jellyfin-tizen .
```

Then run the Docker command again with your local image.

```sh
docker run -it --ulimit nofile=122880:122880 -m 3G --rm local/install-jellyfin-tizen <tv-ip-address>
```
