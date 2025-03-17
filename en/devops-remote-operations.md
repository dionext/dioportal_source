---
title: "Working with remote OS and Synchronization"
description: "Working with remote OS"
keywords: "Rsync, WinSCP, SCP"
lang: "en"
permalink: "devops-remote-operations"
aliases:
  - "devops-remote-operations"
---


# Working with remote OS and Synchronization

## Setting up a secure protocol

See [Internet protocols](internet-protocols)

## Remote command execution

Entrance with ssh:

```bash
ssh root@192.168.1.10
```

```bash
ssh root@192.168.1.10 -p 22
```

if the server does not have our key, then the password to the server will be requested and the connection will be established, remembering this password

Remote command execution

```bash
ssh user@server ls /etc/
```

(to run command: ls /etc/)

[https://stackoverflow.com/questions/9270734/ssh-permissions-are-too-open-error](https://stackoverflow.com/questions/9270734/ssh-permissions-are-too-open-error)

```bash

chmod 600 ~/.ssh/id_rsa
```

### Executing batch

```bash

ssh -t root@$REMOTE_SERVER_ADDRESS << EOF
cd /mnt/$APP_NAME/app
docker build --tag=$APP_NAME:latest .
cd /mnt/$APP_NAME
docker-compose down
docker-compose up -d
EOF
```

[https://ubuntushell.com/disable-ssh-welcome-message](https://ubuntushell.com/disable-ssh-welcome-message) How to Disable SSH Welcome Message on Ubuntu

```
sudo vim /etc/pam.d/sshd
```

```
# session    optional     pam_motd.so  motd=/run/motd.dynamic
# session    optional     pam_motd.so noupdate
```

```
sudo systemctl restart ssh
```

## Transfer files to the server

### Rsync

(linux)

**rsync** is a utility for efficiently transferring and synchronizing files across computer systems. rsync has one with --progress parameter. The -a will keep permissions,etc, and -h will be human readable.

rsync -ah --progress source destination

```bash
rsync -rvzn --progress --delete -e 'ssh -p 22 -i /root/.ssh/id_rsa' /mnt/sourcepath/ root@servername:/mnt/targetpath/
```

### SCP

scp test.js root@192.168.1.10:/mnt

```bash

scp -P 22 file.tar.gz root@servername:/mnt/targetpath/
```

### WinSCP

```bash
winscp.com /command "open sftp://root:mypassword@servername/" "put sourcefile.txt /mnt/tagrepath/" "exit"
```

### Curl

Curl on Ubuntu documentation [https://manpages.ubuntu.com/manpages/focal/man1/curl.1.html](https://manpages.ubuntu.com/manpages/focal/man1/curl.1.html)

{#id19}Downloading files from outside

curl http://proft.me - get the contents of the main page  
curl -o index.html http://proft.me - get the contents of the main page into the file index.html

Example of usage socks5 proxy with curl

curl -v -x socks5://your\_user:your\_password@your\_server\_ip:1080 http://www.google.com/

## Synchronization

### Overview. Local First

[https://www.inkandswitch.com/local-first/](https://www.inkandswitch.com/local-first/) (By Martin Kleppmann and others)

[https://njoseph.me/mediawiki/LocalFirst](https://njoseph.me/mediawiki/LocalFirst)

**local-first software** - software that keeps your data locally as much as possible and only sends it over the network for synchronization or backup.

It is possible to transfer a file across devices using various technologies:

* Sending it back and forth by email;
* Passing a USB drive back and forth;
* Via a distributed file system such as a NAS server, NFS, FTP, or rsync;
* Using a cloud file storage service like Dropbox, Google Drive, or OneDrive;
* Using a version control system such as Git

### Syncthing

[https://syncthing.net/](https://syncthing.net/)

Syncthing is a **continuous file synchronization** program. It synchronizes files between two or more computers in real time, safely protected from prying eyes. Your data is your data alone and you deserve to choose where it is stored, whether it is shared with some third party, and how it's transmitted over the internet.
