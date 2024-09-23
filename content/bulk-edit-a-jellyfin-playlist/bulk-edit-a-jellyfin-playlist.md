---
aliases:
  - bulk-edit-a-jellyfin-playlist
archive_links: 
category: self-hosted
classification: public
date: 2024-09-23T08:56:46
date_modified: 2024-09-23T08:56:46
draft: false
id: 20240923085646
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - jellyfin
  - music
  - playlist
  - self-hosted
  - xml
title: Bulk Edit a Jellyfin Playlist
type: tech-note
---
You can't seem to bulk edit Jellyfin playlists from the GUI at the moment, and I was wondering how I could quickly remove a lot of songs from one.

I discovered that the playlists are stored in XML files, and you can simple edit the underlying file and then rescan all your libaries and the playlist will then "re-sync" with the XML file. 

The playlists are stored in: `config/data/playlists/<playlist-name>/playlist.xml`.

Once edited, go into the Administration Dashboard, and click "Scan All Libaries", once the scan completes the playlist should reflect what's in the XML file.
