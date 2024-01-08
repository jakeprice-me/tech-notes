---
aliases:
  - install-jellyfin-app-on-samsung-smart-tv-running-tizen
archive_links:
  - https://web.archive.org/web/20231126220409/https://developer.samsung.com/smarttv/develop/getting-started/using-sdk/tv-device.html
category: samsung
classification: public
date: 2023-12-07T17:23:20
date_modified: 2023-12-07T17:23:20
id: 20231207172320
link: 
local_archive: attachments/20231207172320.html
pinned: false
series: 
tags:
  - samsung
  - tizen
  - jellyfin
  - app
title: Install Jellyfin App on Samsung Smart TV running Tizen
type: tech-note
---

Initially I tried to follow the instructions [here](https://github.com/jeppevinkel/jellyfin-tizen-builds) but ran into multiple issues just trying to install the Tizen SDK (tried both Fedora and Windows with various issues).

Then I discovered [Georift/install-jellyfin-tizen](https://github.com/Georift/install-jellyfin-tizen) and after facing the issue decribed [here](https://github.com/Georift/install-jellyfin-tizen/issues/9) using the below command I was able to install Jellyfin directly onto my Samsung Smart TV (from 2016).

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
