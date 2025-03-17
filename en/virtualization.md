---
title: "Virtualization"
description: ""
keywords: ""
lang: "en"
permalink: "virtualization"
aliases:
  - "virtualization"
---

# Virtualization

## Docker

See [Docker](docker)

## VMware

[https://www.vmware.com/](https://www.vmware.com/)

Local Virtual Machines. VMware Workstation Player Easily run multiple operating systems as virtual machines on your Windows or Linux PC with VMware Workstation Player.

VMware Workstation Player, formerly VMware Player, is a virtualization software package for x64 computers running Microsoft Windows or Linux, supplied free of charge by VMware, Inc. VMware Player can run existing virtual appliances and create its own virtual machines (which require that an operating system be installed to be functional). It uses the same virtualization core as VMware Workstation, a similar program with more features, which is not free of charge. VMware Player is available for personal non-commercial use, or for distribution or other use by written agreement. VMware, Inc. does not formally support Player, but there is an active community website for discussing and resolving issues, as well as a knowledge base [https://en.wikipedia.org/wiki/VMware\_Workstation\_Player](https://en.wikipedia.org/wiki/VMware_Workstation_Player)

### VMware ESXi

(often compared with Proxmox)

VMware ESXi (formerly ESX) is an enterprise-class, type-1 hypervisor developed by VMware, a subsidiary of Broadcom, for deploying and serving virtual computers. As a type-1 hypervisor, ESXi is not a software application that is installed on an operating system (OS); instead, it includes and integrates vital OS components, such as a kernel.

## VirtualBox

[https://www.virtualbox.org/](https://www.virtualbox.org/)

Oracle VM VirtualBox (formerly Sun VirtualBox, Sun xVM VirtualBox and InnoTek VirtualBox) is a hosted hypervisor for x86 virtualization developed by Oracle Corporation. VirtualBox was originally created by InnoTek Systemberatung GmbH, which was acquired by Sun Microsystems in 2008, which was in turn acquired by Oracle in 2010. VirtualBox may be installed on Microsoft Windows, macOS, Linux, Solaris and OpenSolaris. There are also ports to FreeBSD and Genode. It supports the creation and management of guest virtual machines running Windows, Linux, BSD, OS/2, Solaris, Haiku, and OSx86, as well as limited virtualization of macOS guests on Apple hardware. For some guest operating systems, a "Guest Additions" package of device drivers and system applications is available, which typically improves performance, especially that of graphics, and allows changing the resolution of the guest OS automatically when the window of the virtual machine on the host OS is resized. [https://en.wikipedia.org/wiki/VirtualBox](https://en.wikipedia.org/wiki/VirtualBox)

### Tips

To set the screen resolution you need to install add-ons. After installing a guest operating system in a virtual machine, the first thing you need to do is install the virtual machine software - "Guest OS Additions for VirtualBox"

Disc enlargement  
It's better to do it through a menu item rather than through a script. Because the script may give a format mismatch error.  
After enlarging the disk, you need to expand the disk using OS tools (In Windows, this is through Computer Management)

Example of script

```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" modifyhd "path\VM_Name" 
--resize 70000
```

Cloning activated Windows. [https://superuser.com/questions/472951/make-a-clone-of-virtualbox-machine-that-doesnt-cause-windows-re-activation-afte](https://superuser.com/questions/472951/make-a-clone-of-virtualbox-machine-that-doesnt-cause-windows-re-activation-afte)  
Normally the trigger for this is a change of MAC address, but VBox allows you to keep that the same (the VMs are never running at the same time, so having the same MAC address is not a problem). Apparently, the secret is to set an extra property called the hardwareuuid: VBoxManage modifyvm --hardwareuuid Once this is set, any cloned VMs will inherit it. No more activation!

## Proxmox Virtual Environment (Proxmox VE)

[https://www.proxmox.com/en/](https://www.proxmox.com/en/)

Proxmox Virtual Environment (Proxmox VE or PVE) is a hyper-converged infrastructure open-source software. It is a hosted hypervisor that can run operating systems including Linux and Windows on x64 hardware. It is a Debian-based Linux distribution with a modified Ubuntu LTS kernel and allows deployment and management of virtual machines and containers. Two types of virtualization are supported: container-based with LXC (starting from version 4.0 replacing OpenVZ used in version up to 3.4, included), and full virtualization with KVM.\[11\] It includes a web-based management interface. There is also a mobile application available for controlling PVE environments. [https://en.wikipedia.org/wiki/Proxmox\_Virtual\_Environment](https://en.wikipedia.org/wiki/Proxmox_Virtual_Environment)

Management of virtual machines and administration of the server itself are performed via the web interface or through the standard Linux command line interface.  
Many options are available for the created virtual machines: the hypervisor used, the storage type (image file or LVM), the type of emulated disk subsystem (IDE, SCSI or VirtIO), the type of emulated network card, the number of available processors, and others.

Installation and system requirements [https://pve.proxmox.com/pve-docs/chapter-pve-installation.html](https://pve.proxmox.com/pve-docs/chapter-pve-installation.html)

## Other Virtualization Platforms

**OpenVZ**(Open Virtuozzo) is an operating-system-level virtualization technology for Linux. It allows a physical server to run multiple isolated operating system instances, called containers, virtual private servers (VPSs), or virtual environments (VEs). OpenVZ is similar to Solaris Containers and LXC

Kernel-based Virtual Machine (**KVM** ) is a free and open-source virtualization module in the Linux kernel that allows the kernel to function as a hypervisor. It was merged into the mainline Linux kernel in version 2.6.20, which was released on February 5, 2007. KVM requires a processor with hardware virtualization extensions, such as Intel VT or AMD-V. KVM has also been ported to other operating systems such as FreeBSD and illumos in the form of loadable kernel modules [https://en.wikipedia.org/wiki/Kernel-based\_Virtual\_Machine](https://en.wikipedia.org/wiki/Kernel-based_Virtual_Machine)

Comparison of platform virtualization software [https://en.wikipedia.org/wiki/Comparison\_of\_platform\_virtualization\_software](https://en.wikipedia.org/wiki/Comparison_of_platform_virtualization_software)
