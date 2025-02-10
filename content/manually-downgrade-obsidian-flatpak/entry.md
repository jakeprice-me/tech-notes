---
aliases:
  - manually-downgrade-obsidian-flatpak
category: obsidian
classification: public
date: 2024-12-13T16:25:48
date_modified: 2024-12-13T16:25:48
draft: false
id: 20241213162548
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - downgrade
  - flatpak
  - obsidian
  - plugin
title: Manually Downgrade Obsidian Flatpak
type: tech-note
---

Currently a number of plugins that I rely on to use SIFT (my personal knowledge-base) in Obsidian don't work with the latest versions of Obsidian that implement [deferred views](https://docs.obsidian.md/Plugins/Guides/Understanding+deferred+views).

The plugins in question are:

- / [Front Matter Title](https://github.com/snezhig/obsidian-front-matter-title)
	- Fully working now.
- ! [Custom File Explorer Sorting](https://github.com/SebastianMC/obsidian-custom-sort)
	- Partially working - works on desktop, but not on Android - see [GitHub issue](https://github.com/SebastianMC/obsidian-custom-sort/issues/169).
- ! [Folder Notes](https://github.com/LostPaul/obsidian-folder-notes)
	- Only works when manually re-enabled on every start, on desktop and Android - see [GitHub issue](https://github.com/LostPaul/obsidian-folder-notes/issues/168).

All three of these plugins have to work together for me to be able to use SIFT in the way I try to use it in Obsidian. Nothing much as of 2024-12-13, seems to be happening in terms of fixing the issues, so I've manually downgraded to Obsidian v1.6.7 on desktop and Android.

## Android

Find v1.6.7 in the Obsidian GitHub Releases [page](https://github.com/obsidianmd/obsidian-releases/releases) and download and install the [APK](https://github.com/obsidianmd/obsidian-releases/releases/download/v1.6.7/Obsidian-1.6.7.apk), as it's installed manually as an APK, Google Play Store won't be able to automatically update it (it'll try but fail).

## Desktop (Linux)

To do this, follow these instructions.

Uninstall Obsidian.

```sh
flatpak uninstall md.obsidian.Obsidian
rm -rf ~/.var/app/md.obsidian.Obsidian
```

Install Obsidian once again (this will install the latest version).

```sh
flatpak install flathub md.obsidian.Obsidian
```

Now downgrade to v1.6.7.

```sh
sudo flatpak update md.obsidian.Obsidian --commit=92f2aef19a97e3748401545a994d45dd05fdd73fd4bf582d06fa2bfa847acf0a
```

Before opening Obsidian, we need to disable Automatic Updates, otherwise on launch it'll just update to the latest version in the background.

Create this directory:

```sh
mkdir -p ~/.var/app/md.obsidian.Obsidian/config/obsidian
```

Then create this file:

```sh
echo '{"vaults":{"4e8b6c9b15bf6d7f":{"path":"/home/jprice/my/files/documents/SIFT/content","ts":1734105945438,"open":true}},"updateDisabled":true}' > ~/.var/app/md.obsidian.Obsidian/config/obsidian/obsidian.json
```

You can now open Obsidian, and you should see under "Settings > General > Automatic updates" that the setting is toggled off, and the version of Obsidian is v1.6.7