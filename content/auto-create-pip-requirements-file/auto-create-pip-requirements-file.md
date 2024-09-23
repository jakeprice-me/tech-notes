---
aliases:
  - auto-create-pip-requirements-file
archive_links:
  - https://web.archive.org/web/20240905092206/https://stackoverflow.com/questions/31684375/automatically-create-file-requirements-txt
category: python
classification: public
date: 2022-01-29T14:30:03
date_modified: 2024-09-23T21:39:32
draft: false
id: 20220129143003
image: 
links:
  - https://stackoverflow.com/questions/31684375/automatically-create-requirements-txt
local_archive_links:
  - attachments/20220129143003.html
pinned: false
print: false
series: 
tags:
  - python
  - pip
  - requirements
  - dependencies
title: Automatically create a Pip requirements.txt
type: tech-note
---

> You can use the following code to generate a requirements.txt file:
> 
>     pip install pipreqs
>     
>     pipreqs /path/to/project
>     
> 
> more info related to pipreqs can be found [here](https://github.com/bndr/pipreqs).
> 
> Sometimes you come across `pip freeze`, but this saves all packages in the environment including those that you don't use in your current project.

Simply run the below in a Python directory and it will create a `requirements.txt` populated with current dependencies.

```sh
pipreqs --force .
```

You can then install all those dependencies by pointing `pip` to the file.

```sh
pip install -r requirements.txt
```