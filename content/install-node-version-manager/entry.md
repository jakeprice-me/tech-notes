---
aliases:
  - install-node-version-manager
category: cli
classification: public
date: 2020-07-05T16:05:06
date_modified: 2020-07-05T16:05:06
draft: false
id: 20200705160506
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - nvm
  - npm
  - node
  - javascript
title: Install Node Version Manager
type: tech-note
---

Grab the script.

``` bash
wget --quiet https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh --output-document /tmp/nvm_install.sh
```

Make the script executable, check it's safe, and if happy then run it.

``` bash
chmod u+x /tmp/nvm_install.sh
bash /tmp/nvm_install.sh
```

Restart your terminal session, or just `source ~/.bashrc`.

Now, check the available versions to install using `nvm`.

``` bash
$ nvm ls-remote | grep "Latest LTS"
...
         v4.9.1   (Latest LTS: Argon)
        v6.17.1   (Latest LTS: Boron)
        v8.17.0   (Latest LTS: Carbon)
       v10.21.0   (Latest LTS: Dubnium)
       v12.18.2   (Latest LTS: Erbium)
```

Install the required version, in this case the latest LTS version.

``` bash
nvm install v12.18.2
```

Check the version of node.

``` bash
$ node -v
v12.15.0
```

`nvm` should switch to the most recently installed version. You can tell `nvm` to use another version you have installed though.

``` bash
nvm use v12.15.0
```

Check any versions you have installed.

``` bash
nvm ls
```

You can default any version downloaded.

``` bash
nvm alias default v12.15.0
```

