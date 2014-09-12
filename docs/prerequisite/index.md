# **EasyEngine** **(ee)**

1. [[Linux Distribution|https://github.com/rtCamp/easyengine/wiki/Prerequisite#linux-distribution]]
1. [[Update Packages|https://github.com/rtCamp/easyengine/wiki/Prerequisite#update-packages]]
1. [[ Setup FQDN|https://github.com/rtCamp/easyengine/wiki/Prerequisite#setup-fqdn]]
1. [[Install wget command|https://github.com/rtCamp/easyengine/wiki/Prerequisite#install-wget-command]]

***

## Linux Distribution:
EasyEngine (ee) supports following Linux Distribution:

<a href="http://www.ubuntu.com/">[[https://cloud.githubusercontent.com/assets/7354660/3778800/e9e849ac-1979-11e4-972c-9d9c3b0c6166.png|width=40px|align=right|float]] 12.04.x 14.04.x </a>

<a href="http://www.debian.org/">[[https://cloud.githubusercontent.com/assets/7354660/3778706/1fe44b7a-1978-11e4-8a31-bbb72707e9cb.png|width=40px|align=right|float]] 6.x 7.x</a>
## Update Packages:
```bash
apt-get update && apt-get upgrade && apt-get dist-upgrade
```

## Setup FQDN:
EasyEngine (ee) used `hostname -f` command output to detect your server hostname.

For the hostname, use your FQDN such as example.com 
**Important:** replace every instance of example.com with your own domain in all commands and configuration files. Don't forget to save your files after editing.
```bash
echo example.com > /etc/hostname
service hostname restart
```

**How to test hostname is set properly:**
```bash
^_^[root@example.com:~]# hostname -f
example.com
```

## Install wget command:
Most of Linux distribution comes with `wget` command but some customised Linux like minimal Ubuntu/Debian not have `wget` command pre-installed.
Ref: [[#292|https://github.com/rtCamp/easyengine/issues/292]]

**How to install wget command:**
```bash
apt-get install wget
```

_Note: Recomened RAM for Mail server package installation is minimum 1GB_

