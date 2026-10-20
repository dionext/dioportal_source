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

### Quick for Ubuntu 24

Install Docker (on the VPS)

```
apt-get update
apt-get install -y git curl ca-certificates
curl -fsSL https://get.docker.com | sh
```

Verify:

```
docker --version
docker compose version
```

### Old 

Ubuntu [https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

#### Add Docker's official GPG key:

sudo apt-get update  
sudo apt-get install ca-certificates curl  
sudo install -m 0755 -d /etc/apt/keyrings  
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc  
sudo chmod a+r /etc/apt/keyrings/docker.asc

#### Add the repository to Apt sources:

echo \\  
"deb \[arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc\] https://download.docker.com/linux/ubuntu \\  
$(. /etc/os-release \&\& echo "$VERSION\_CODENAME") stable" | \\  
sudo tee /etc/apt/sources.list.d/docker.list \> /dev/null  
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

docker --version  
Docker version 26.0.0, build 2ae903e

#### docker compose

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

# UI and soft for UI

In order to connect to the physical desktop of the remote Linux host, it's necessary that a desktop environment is installed. This is necessary also for creating a NoMachine virtual desktop.  
A desktop environment is a set of programs running on top of the computer operating system and sharing a common graphical user interface. Most common Linux desktop environments are Unity 3D, GNOME 3, KDE's Plasma desktop (they all implement 3D hardware acceleration and use OpenGL)  and lightweight ones such as MATE desktop (a fork of GNOME 2), Xfce and LXDE.
When no desktop environment is installed, users connecting to the remote computer usually get a black screen. https://kb.nomachine.com/AR06N00891 

Xfce  is a free and open-source desktop environment for Linux and other Unix-like operating systems. Xfce aims to be fast and lightweight while still visually appealing and easy to use. The desktop environment is designed to embody the traditional Unix philosophy of modularity and re-usability, as well as adherence to standards; specifically, those defined at freedesktop.org.


## Ways to Remotely Connect to Ubuntu from Windows or Linux

### xrdp

xrdp is a free, open-source Remote Desktop Protocol (RDP) server for Linux that allows users to connect to Linux systems with a graphical desktop environment from RDP clients like the Microsoft Remote Desktop Connection app, enabling features like secure connections via TLS, two-way clipboard transfer, audio, and drive redirection. To use xrdp, you need to install the xrdp server and a desktop environment on the Linux machine, then open TCP port 3389 in the firewall and connect using an RDP client.  

https://help.reg.ru/support/servery-vps/oblachnyye-servery/ustanovka-programmnogo-obespecheniya/kak-podklyuchitsya-k-ubuntu-iz-windows-s-pomoshchyu-rdp#2 (ru)

Installing xrdp and Xfce on Ubuntu

sudo apt update
   
Open TCP port 3389:
   
sudo ufw allow 3389
  
Install xrdp:
  
sudo apt install xrdp

Install the xorgxrdp package:
   
sudo apt install xorgxrdp
   
Activate xrdp:
   
sudo systemctl enable xrdp
   
Check xrdp status:
   
sudo systemctl status xrdp

Install the Xfce graphical desktop environment:
 
sudo apt install xfce4

Run xrdp with the command:

sudo systemctl start xrdp

Connect to Ubuntu Desktop from Windows

### Alternatives 

Linux client (Remmina) ---> Linux Server (Ubuntu Desktop, Debian Desktop, Fedora Workstation)

x2go  https://wiki.x2go.org/doku.php 

X2Go is open source remote desktop software for Linux that uses a modified NX 3 protocol. X2Go gives remote access to a Linux system's graphical user interface. It can also be used to access Windows systems through a proxy.

Remmina

Remmina is a free and open source remote desktop client for POSIX-based computer operating systems. It supports the Remote Desktop Protocol (RDP), VNC, NX, XDMCP, SPICE, X2Go and SSH protocols and uses FreeRDP as foundation.

(Remmina is not directly available for Windows, as it is a Linux-based client. To use Remmina to connect to a Windows machine, you would need to run Remmina within the Windows Subsystem for Linux (WSL) and then set up a remote connection to your Windows PC)

AnyDesk  

AnyDesk is a remote desktop application distributed by AnyDesk Software GmbH. The proprietary software program provides platform-independent remote access to personal computers and other devices running the host application. It offers remote control, file transfer, and VPN functionality. AnyDesk is often used in technical support scams and other remote access scams.

NoMachine

NoMachine is a software for secure, high-performance remote desktop access, allowing users to connect to and control computers from anywhere, with a free version for personal use and paid enterprise products for businesses. It offers features like file transfer, multi-media streaming, remote printing, and collaboration, utilizing its proprietary NX technology to adapt to network conditions for a smooth experience. Users can connect via IP address or the subscription-based NoMachine Network service for easier access over the internet. 

X over SSH

"X over SSH" refers to X11 forwarding over SSH, a mechanism that allows you to run graphical applications on a remote server and display their graphical user interfaces (GUIs) on your local machine. This is achieved by securely tunneling the X11 protocol traffic through an SSH connection.
## Firefox
https://help.ubuntu.ru/wiki/firefox 
sudo apt-get update
sudo apt-get install firefox
