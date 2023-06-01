---
alias: setup-samba-fileshare-on-debian
category: samba
classification: public
date: 2020-11-24 21:48:52
date_modified: 2020-11-24 21:48:52
id: 20201124214852
link: 
pinned: false
series: 
tags: [debian, samba, file-server, smb]
title: Setup a Samba Fileshare on Debian
type: tech-note
uuid: 83b5248d-6beb-4c4e-accf-1d8a89fd045c
---

I use the commands below to setup a Samba network share on my local server.

```sh
# Install Samba:
sudo apt install --assume-yes samba

# Say no to any prompts about WINS.

# Add Samba user:
sudo adduser jprice

# Set the password for the user:
sudo smbpasswd -a jprice

# Create the fileshare directory:
sudo mkdir --parents /srv/my
sudo chown --recursive jprice:jprice /srv/my

# Add config to /etc/samba/smb.conf:
[my]
    comment = My File Share
    path = /srv/my
    read only = no
    browsable = yes

# Restart Samba:
sudo systemctl restart smbd

# Add a firewall rule:
sudo ufw allow samba

# Restart Samba
sudo systemctl restart smbd
```

You can then connect as below.

```sh
smb://<ip-address>/my
```