---
aliases:
  - tabler-icon-fonts-are-not-opentype-spec-compliant
category: firefox
classification: public
date: 2023-08-11T10:02:33
date_modified: 2023-08-11T10:02:33
draft: false
id: 20230811100233
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - firefox
  - font
  - icon
title: Tabler Icon Fonts are not OpenType spec compliant
type: tech-note
---

Only an issue on Firefox for Android Nightly, but I have to set `gfx.downloadable_fonts.otl_validation` to `false` when using the latest Tabler Icons otherwise they are not displayed, and return errors in the remote console like this:

```log
downloadable font: GSUB: Bad ligature offset 3218 for ligature 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: GSUB: Failed to parse ligature set 18 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: Layout: Failed to parse lookup subtable 3 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: Layout: Failed to parse subtable 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: Layout: Failed to parse lookup 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: GSUB: Failed to parse lookup list table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: GSUB: Failed to parse table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: rejected by sanitizer (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:1) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff2?v2.1.2
downloadable font: GSUB: Bad ligature offset 3218 for ligature 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: GSUB: Failed to parse ligature set 18 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: Layout: Failed to parse lookup subtable 3 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: Layout: Failed to parse subtable 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: Layout: Failed to parse lookup 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: GSUB: Failed to parse lookup list table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: GSUB: Failed to parse table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: rejected by sanitizer (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:2) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.woff?
downloadable font: GSUB: Bad ligature offset 3218 for ligature 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: GSUB: Failed to parse ligature set 18 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: Layout: Failed to parse lookup subtable 3 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: Layout: Failed to parse subtable 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: Layout: Failed to parse lookup 0 (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: GSUB: Failed to parse lookup list table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: GSUB: Failed to parse table (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2
downloadable font: rejected by sanitizer (font-family: "tabler-icons" style:normal weight:400 stretch:100 src index:3) source: https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.1.2/fonts/tabler-icons.ttf?v2.1.2 
```

There's an open GitHub issue about the problem [here](https://github.com/tabler/tabler-icons/issues/476) but no fix yet.