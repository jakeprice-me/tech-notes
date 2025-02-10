---
aliases:
  - install-multiple-versions-of-a-program-on-macos-using-homebrew
category: macos
classification: public
date: 2024-10-18T10:14:03
date_modified: 2024-10-18T10:14:03
draft: false
id: 20241018101403
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - homebrew
  - macos
  - python
  - runtime
  - version
title: Install Multiple Versions of a Program on MacOS using Homebrew
type: tech-note
---

Homebrew makes it really simple, I mostly use this for installing multiple versions of Python without the added complication of using Docker.

Just install the version of the program/utility/tool you need by specifying it with an `@`.

```sh
brew install python@<version-number>

# For example:
brew install python@3.9
brew install python@3.11
```

You can then use each version like this:

```sh
/opt/homebrew/bin/python3.9
/opt/homebrew/bin/python3.11
```