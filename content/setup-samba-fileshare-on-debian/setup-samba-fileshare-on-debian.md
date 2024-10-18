---
aliases:
  - setup-samba-fileshare-on-debian
category: samba
classification: public
date: 2020-11-24T21:48:52
date_modified: 2020-11-24T21:48:52
draft: false
id: 20201124214852
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [debian, samba, file-server, smb]
title: Setup a Samba Fileshare on Debian
type: tech-note
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

