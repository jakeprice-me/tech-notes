---
aliases:
  - inconsolata-wsltty-windows-10
archive_links: 
category: windows
classification: public
date: 2020-08-01T14:19:31
date_modified: 2020-08-01T14:19:31
draft: false
id: 20200801141931
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [wsltty, inconsolata, fonts]
title: Inconsolata on wsltty on Windows 10
type: tech-note
---

When installing my favourite monospace font on Windows 10 at work It is really blurry, because when downloaded from [Inconsolata](https://www.levien.com/type/myfonts/inconsolata.html) it only seems to include `Medium` as a useable font style, and it looks horrible on wsltty.

I've found if I download from [fonts/ofl/inconsolata/static at master · google/fonts · GitHub](https://github.com/google/fonts/tree/master/ofl/inconsolata/static), specifically:

- Inconsolata Light/Medium/Regular/SemiBold 

Then in wsltty set the font to `Inconsolata`, select `Regular` for the font style, and size `13`. It's perfect, and readable again without the blurriness of medium.

I expect I could probably also just download from Google Fonts directly and accomplish the same thing.

I've placed them on my work OneDrive account for backup as well.