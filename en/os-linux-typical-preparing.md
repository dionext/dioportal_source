---
title: "Typical operating system preparation after creating a new server"
description: ""
keywords: ""
lang: "en"
permalink: "os-linux-typical-preparing"
aliases:
  - "os-linux-typical-preparing"
---

# Typical operating system preparation after creating a new server

(Ubuntu 22.04)

## Initial

apt-get update

apt-get install ntfs-3g (для корректного монтирования NTFS)

apt-get install mc

apt-get install screen

timedatectl

timedatectl set-timezone Europe/Moscow

## SSH

### SSH Key generation

Key generation

```bash
ssh-keygen
```

Key placement  
~/.ssh  
~/.ssh/id\_rsa.pub - public key. It is copied to the server where you need to gain access.  
~/.ssh/id\_rsa - private key. It cannot be shown to anyone.

### SSH Settings

[https://ubuntushell.com/disable-ssh-welcome-message](https://ubuntushell.com/disable-ssh-welcome-message) How to Disable SSH Welcome Message on Ubuntu

```
nano /etc/pam.d/sshd
```

```
# session    optional     pam_motd.so  motd=/run/motd.dynamic
# session    optional     pam_motd.so noupdate
```

```
sudo systemctl restart ssh
```

test ssh

ssh -t root@$REMOTE\_SERVER\_ADDRESS

## Adding a Hard Drive in Linux

[http://www.linuxlib.ru/iron/hddadd.htm](http://www.linuxlib.ru/iron/hddadd.htm) [http://mydebianblog.blogspot.ru/2008/09/linux.html](http://mydebianblog.blogspot.ru/2008/09/linux.html)

[https://pve.proxmox.com/wiki/Resize\_disks](https://pve.proxmox.com/wiki/Resize_disks)

view information about all physical and virtual disks

```bash
fdisk -l
```

view information about the first physical or virtual disk

```bash
fdisk -l /dev/sda
```

find your new drive. it can be for example /dev/vdb /dev/vdc /dev/sda4 - this must be taken into account in further commands

```bash
fdisk /dev/vdc
```

Create a new partition with n. Then select the partition type by entering the p command. Leave the remaining parameters unchanged by simply pressing Enter. To save your changes, enter the w command.

formats the vdc1 partition into ext4 format

```bash
mkfs.ext4 /dev/vdc1
```

create the mount folder

```bash
mkdir /mnt/disk2
```

```bash
mount -o barrier=0 /dev/vdc1 /mnt/disk2
```

```bash
echo "/dev/vdc1 /mnt/disk2 ext4 barrier=0 0 1" >> /etc/fstab
```

Check the disk names in the system, for example, with the lsblk command

## Docker

Ubuntu [https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Add Docker's official GPG key:

sudo apt-get update  
sudo apt-get install ca-certificates curl  
sudo install -m 0755 -d /etc/apt/keyrings  
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc  
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:

echo \\  
"deb \[arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc\] https://download.docker.com/linux/ubuntu \\  
$(. /etc/os-release \&\& echo "$VERSION\_CODENAME") stable" | \\  
sudo tee /etc/apt/sources.list.d/docker.list \> /dev/null  
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

docker --version  
Docker version 26.0.0, build 2ae903e

## docker compose

apt install docker-compose

docker-compose --version  
docker-compose version 1.29.2, build unknown

### Portainer (CE - community edition)

{#id28}Deployment Single

[https://docs.portainer.io/start/install-ce/server/docker/linux](https://docs.portainer.io/start/install-ce/server/docker/linux)

docker volume create portainer\_data

docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer\_data:/data portainer/portainer-ce:latest

#### Update to latest version

[https://docs.portainer.io/start/upgrade/docker](https://docs.portainer.io/start/upgrade/docker)

```
docker stop portainer 
```

```
docker rm portainer 
```

```
docker pull portainer/portainer-ce:latest 
```

```
docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

Creating folders (for example)

sudo mkdir -p /mnt/devops/monitoring
