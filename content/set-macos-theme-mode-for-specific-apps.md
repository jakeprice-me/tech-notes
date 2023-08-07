---
alias: set-macos-theme-mode-for-specific-apps
archive_link: []
category: macos
classification: public
date: 2022-11-28 15:13:34
date_modified: 2022-11-28 15:13:34
id: 20221128151334
link: 
local_archive: 
pinned: false
series: 
tags: [macos, theme, dark-mode]
title: Set macOS Theme for Specific Apps
type: tech-note
uuid: 2d1477a9-e206-401b-a073-9a3efdbc6c6e
---

```sh
osascript -e 'id of app "Outlook"'

com.microsoft.Outlook

# Exclude from dark mode:
defaults write <Bundle-Identifier> NSRequiresAquaSystemAppearance -bool yes

# Dark mode on:
defaults write com.microsoft.Outlook NSRequiresAquaSystemAppearance -bool no

# Reset mode:
defaults delete <Bundle-Identifier> NSRequiresAquaSystemAppearance
```