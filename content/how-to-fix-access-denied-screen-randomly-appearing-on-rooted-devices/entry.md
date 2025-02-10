---
aliases:
  - how-to-fix-access-denied-screen-randomly-appearing-on-rooted-devices
category: android
classification: public
date: 2022-12-19T17:41:41
date_modified: 2022-12-19T17:41:41
draft: false
id: 20221219174141
image: 
links:
  - https://forum.xda-developers.com/t/how-to-fix-access-denied-screen-randomly-appearing-on-rooted-devices.4503767/
local_archive_links:
  - attachments/how-to-fix-access-denied-screen-randomly-appearing-on-rooted-devices.html
pinned: false
print: false
series: 
tags:
  - android
  - galaxy
  - root
  - samsung
title: How to fix Access denied screen randomly appearing on rooted devices
type: tech-note
---

> A couple of days ago my S21 Ultra running G998BXXS5CVIF automatically opened an "Access denied" screen. It was impossible to show which app cause it as it disappeared once you got to the app switcher menu.  
>   
> 
> **Access denied**  
> Unauthorized changes have been made to your phone. To get help, contact Customer Service.
>   
> I could force the screen by rebooting or by changing the device's language. Using:  
> 
> Code:
> 
> ```
> dumpsys activity activities | grep "mFocused"
> ```
> 
> via adb showed it was `com.android.samsung.dkey` which opened an activity of `com.samsung.android.carkey` (`com.samsung.android.dkey/com.samsung.android.carkey.ccc.ui.IntegrityCheckFailDialogActivity`)  
>   
> Apparently there was a Samsung Wallet Digital Key update (probably v1.0.08.11) which causes it after a reboot as well as randomly every couple of hours. Disabling "Appear on top" for Samsung Wallet Digital Key fixed it for me.  
>   
> Uninstalling the update isn't a good permanent solution and you can't disable the app without root (meaning you probably don't want to disable it as it maybe could cause other issues). It can affect any device that has a tripped Know. Even formerly rooted devices running stock with a locked bootloader.