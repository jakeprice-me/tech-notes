---
aliases:
  - install-stable-diffusion
archive_links:
  - https://web.archive.org/web/20220926150717/https://github.com/invoke-ai/InvokeAI/blob/main/docs/installation/INSTALL_LINUX.md
category: miscellaneous
classification: public
date: 2022-09-12T22:01:25
date_modified: 2024-09-23T20:57:04
draft: false
id: 20220912220125
image: 
links:
  - https://github.com/lstein/stable-diffusion/blob/main/docs/installation/INSTALL_LINUX.md
local_archive_links:
  - attachments/20220912220125.html
pinned: false
print: false
series: 
tags:
  - stable-diffusion
  - nvidia
  - gpu
  - cuda
  - conda
  - ai
  - art
  - machine-learning
  - github
title: Install InvokeAI Stable Diffusion Fork
type: tech-note
---

Follow steps [here](https://github.com/lstein/stable-diffusion/blob/main/docs/installation/INSTALL_LINUX.md) but it's easier to run the Anaconda install with the `-b` flag as below.

```sh
$ ./Anaconda3-2022.05-Linux-x86_64.sh -b
```

Furthermore, with Anaconda we don't want it to be activated on login, so disable that with the below command:

```sh
$ conda config --set auto_activate_base false
```

