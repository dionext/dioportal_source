---
title: "Internet protocols"
description: "Using Internet protocols"
keywords: "SSL, TLS, HTTPS, SSH"
lang: "en"
permalink: "internet-protocols"
aliases:
  - "internet-protocols"
---

# Internet protocols

## Overview

[https://en.wikipedia.org/wiki/Category:Internet\_protocols](https://en.wikipedia.org/wiki/Category:Internet_protocols)

## SSL, TLS, HTTPS

SSL, or Secure Sockets Layer, is an encryption-based Internet security protocol. It was first developed by Netscape in 1995 for the purpose of ensuring privacy, authentication, and data integrity in Internet communications. SSL is the predecessor to the modern TLS encryption used today. A website that implements SSL/TLS has "HTTPS" in its URL instead of "HTTP."
SSL is the direct predecessor of another protocol called TLS (Transport Layer Security). In 1999 the Internet Engineering Task Force (IETF) proposed an update to SSL. Since this update was being developed by the IETF and Netscape was no longer involved, the name was changed to TLS. The differences between the final version of SSL (3.0) and the first version of TLS are not drastic; the name change was applied to signify the change in ownership. [https://www.cloudflare.com/learning/ssl/what-is-ssl/](https://www.cloudflare.com/learning/ssl/what-is-ssl/)  
[https://en.wikipedia.org/wiki/Transport\_Layer\_Security](https://en.wikipedia.org/wiki/Transport_Layer_Security)

## SSH

The Secure Shell Protocol (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. Its most notable applications are remote login and command-line execution.

### Key generation

Key generation ssh-keygen [https://linux.die.net/man/1/ssh-keygen](https://linux.die.net/man/1/ssh-keygen) [https://www.ssh.com/academy/ssh/keygen](https://www.ssh.com/academy/ssh/keygen)

```bash
ssh-keygen -t rsa -q -N '' -f ~/.ssh/id_rsa
```

or with default

```bash
ssh-keygen
```

Key placement  
~/.ssh  
~/.ssh/id\_rsa.pub - public key. It is copied to the server where you need to gain access.  
~/.ssh/id\_rsa - private key. It cannot be shown to anyone.

There is an issue with ssh-keygen utility that comes with Windows 10 build 1909 and older that prevents it from working properly with newer SSH daemons (for example, the one that comes with Ubuntu 20.04 LTS and newer). The workaround is to use ECDSA-type key, not RSA-type key, for the SSH connection. You can generate an ECDSA SSH key and add it to SSH agent with the following commands:

```bash

ssh-keygen -t ecdsa -b 521
ssh-add id_ecdsa
```

remote server keys are saved in  
~/.ssh/known\_hosts.

### Copy keys to remote host

Linux

```bash
ssh-copy-id -i ~/.ssh/id_rsa root@192.168.1.10
```

или

```bash
ssh-copy-id -i /mnt/remotecontrol/ssh/id_rsa root@192.168.1.86
```

Windows
(ssh-copy-id does not work)  
In powershell

```bash
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh root@192.168.1.10 "cat >> .ssh/authorized_keys"
```

Copying manually: for the root user, the home directory ~/ will be /root/  
To see ".ssh" extension you need to enable showing hidden files (in WinSCP there is a link at the bottom of the panel) or ls -a

Add ~/.ssh/authorized\_keys to the end of the file. When manual and auto copying are combined, the keys may stick together. It is necessary to check the file and separate the keys with a line break

### Entrance with ssh and remote command execution

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

### Notes for Windows

If you want to use a tool other than Bash for Windows, you can install locally the shared Windows SSH clients included in the following packages: PuTTY; Git for Windows; MobaXterm; Cygwin

Fast generation with default settings from anywhere

```bash
ssh-keygen
```

in this case, the keys end up in the default folder C:\\Users\\\[User name\]\\.ssh

**~/.ssh/id\_rsa.pub** - public key. It is copied to the server where you need to gain access.  
**~/.ssh/id\_rsa** - private key. It cannot be shown to anyone.

If you want to use different keys for different servers, and therefore have different names or different key locations, then you need to study more fine-tuning. The simplest option only works if the key is in the default location and is called by default

## Digital certificates (Public key certificate)

[https://en.wikipedia.org/wiki/Public\_key\_certificate](https://en.wikipedia.org/wiki/Public_key_certificate)

[https://www.cloudflare.com/learning/ssl/what-is-ssl/](https://www.cloudflare.com/learning/ssl/what-is-ssl/)

There are several different types of SSL certificates. One certificate can apply to a single website or several websites, depending on the type:

* Single-domain: A single-domain SSL certificate applies to only one domain (a "domain" is the name of a website, like www.cloudflare.com).
* Wildcard: Like a single-domain certificate, a wildcard SSL certificate applies to only one domain. However, it also includes that domain's subdomains. For example, a wildcard certificate could cover www.cloudflare.com, blog.cloudflare.com, and developers.cloudflare.com, while a single-domain certificate could only cover the first.
* Multi-domain: As the name indicates, multi-domain SSL certificates can apply to multiple unrelated domains.

SSL certificates also come with different validation levels. A validation level is like a background check, and the level changes depending on the thoroughness of the check.

* Domain Validation: This is the least-stringent level of validation, and the cheapest. All a business has to do is prove they control the domain.
* Organization Validation: This is a more hands-on process: The CA directly contacts the person or business requesting the certificate. These certificates are more trustworthy for users.
* Extended Validation: This requires a full background check of an organization before the SSL certificate can be issued.

For resource owned by an individual - Domain Validation (DV) certificate. This certificate confirms ownership of the domain and.  
If the site is owned by a company, there may be several options:

* Business card website for a company or organization. The site does not collect any payment information. Exists for information purposes only. In this case, a certificate with the Domain Validation level of verification is suitable. It encrypts data, eliminates the "unsafe" stub in the browser, and that's it.
* Websites of banks, payment systems, chain hypermarkets or media outlets. The site collects money or data that gives access to money. Fraudsters can copy it to gain access to money. Therefore, you need a certificate with organizational verification - Extended Validation (EV). It can only be received by the real organization that owns the site; its name and type of activity will be indicated in the certificate. A green bar with the company name will appear in the browser bar.
* A small online store, a charity website, a forum. The site is of no interest to scammers, but clients may want to verify the existence of the organization. Here you need a certificate with organization verification - Organization Validation (OV). The name of the organization will be reflected in the certificate, and a green padlock will appear in the browser line.

### Let's Encrypt

Free DV certificates are issued by the **Let's Encrypt** trusted authority.

[https://letsencrypt.org/ru/getting-started/](https://letsencrypt.org/ru/getting-started/)

## Host Windows

Host files are text files that are used to map domain names to IP addresses, precisely what the DNS servers do. You can use them to streamline connecting to websites, and as such, sometimes you'll need to edit one.

C:\\windows\\system32\\drivers\\etc\\hosts

127\.0.0.1 testedomain.com  
192\.168.1.10 anothertesteddomain.com
