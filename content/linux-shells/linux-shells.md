---
aliases:
  - linux-shells
archive_links:
  - https://web.archive.org/web/20230714131325/https://unix.stackexchange.com/questions/170493/login-non-login-and-interactive-non-interactive-shells/170499
category: linux
classification: public
date: 2020-07-14T21:15:25
date_modified: 2024-09-23T22:17:48
draft: false
id: 20200714211525
image: 
links:
  - https://unix.stackexchange.com/questions/170493/login-non-login-and-interactive-non-interactive-shells/170499#170499
local_archive_links:
  - attachments/20200714211525.html
pinned: false
print: false
series: 
tags:
  - bash
  - shell
  - linux
  - stack-exchange
title: Linux Shell
type: tech-note
---

> - **login** shell: A login shell logs you into the system as a specific user, necessary for this is a username and password. When you hit ctrl+alt+F1 to login into a virtual terminal you get after successful login: a login shell (that is interactive). Sourced files:
>     
>     - `/etc/profile` and `~/.profile` for Bourne compatible shells (and `/etc/profile.d/*`)
>     - `~/.bash_profile` for bash
>     - `/etc/zprofile` and `~/.zprofile` for zsh
>     - `/etc/csh.login` and `~/.login` for csh
> - **non-login** shell: A shell that is executed without logging in, necessary for this is a current logged in user. When you open a graphic terminal in gnome it is a non-login (interactive) shell. Sourced files:
>     
>     - `/etc/bashrc` and `~/.bashrc` for bash
> - **interactive** shell: A shell (login or non-login) where you can interactively type or interrupt commands. For example a gnome terminal (non-login) or a virtual terminal (login). In an interactive shell the prompt variable must be set (`$PS1`). Sourced files:
>     
>     - `/etc/profile` and `~/.profile`
>     - `/etc/bashrc` or `/etc/bash.bashrc` for bash
> - **non-interactive** shell: A (sub)shell that is probably run from an automated process you will see neither input nor output when the calling process don't handle it. That shell is normally a non-login shell, because the calling user has logged in already. A shell running a script is always a non-interactive shell, but the script can emulate an interactive shell by prompting the user to input values. Sourced files:
>     
>     - `/etc/bashrc` or `/etc/bash.bashrc` for bash (but, mostly you see this at the beginning of the script: `[ -z "$PS1" ] && return`. That means don't do anything if it's a non-interactive shell).
>     - depending on shell; some of them read the file in the `$ENV` variable.
>
> — [bash - login/non-login and interactive/non-interactive shells - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/170493/login-non-login-and-interactive-non-interactive-shells/170499#170499)

