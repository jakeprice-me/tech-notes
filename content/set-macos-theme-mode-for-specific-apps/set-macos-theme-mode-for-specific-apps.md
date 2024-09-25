---
aliases:
  - set-macos-theme-mode-for-specific-apps
archive_links: 
category: macos
classification: public
date: 2022-11-28T15:13:34
date_modified: 2022-11-28T15:13:34
draft: false
id: 20221128151334
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [macos, theme, dark-mode]
title: Set macOS Theme for Specific Apps
type: tech-note
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

