# **EasyEngine** **(ee)**

## **Prerequisite**
Before install EasyEngine (ee), your system should satisfy our [[Prerequisite]]
## **Installation**
```bash
wget -qO ee rt.cx/ee && sudo bash ee
```
* If your hostname is not [FQDN](http://en.wikipedia.org/wiki/Fully_qualified_domain_name) then EasyEngine ask you to set hostname as FQDN,

 ```bash
 Enter hostname [FQDN]:example.com
 ```
* Above command furthur asks for your name and email address, which will be set as your git username and email address to maintain track of configuration files. Also the same email address is used while creating WordPress website.

 ```bash
 Enter your name [root]: Mitesh Shah
 Enter your email address [root@example.com]: Mr.Miteshah@gmail.com
 ```




Sample output:
```bash
^_^[root@example.com:~]# wget -qO ee rt.cx/ee && sudo bash ee
Executing apt-get update, please wait...
Creating EasyEngine (ee) log directory, please wait...
Installing required packages, please wait...
Reading package lists...
Building dependency tree...
Reading state information...
coreutils is already the newest version.
curl is already the newest version.
ed is already the newest version.
tar is already the newest version.
wget is already the newest version.
The following extra packages will be installed:
[...]
.
.
.
[...]
Cloning EasyEngine (ee) stable branch, please wait...
Installing EasyEngine (ee), please wait...
Enter hostname [FQDN]: example.com

EasyEngine (ee) required your name & email address
to track changes you made under the Git version control
EasyEngine (ee) will be able to send you daily reports & alerts in upcoming version
EasyEngine (ee) will NEVER send your information across

For EasyEngine (ee) auto completion, run the following command
source /etc/bash_completion.d/ee

EasyEngine (ee) installed successfully
EasyEngine (ee) help: https://rtcamp.com/easyengine/docs/
```
For EasyEngine (ee) auto completion, run the following command:
```bash
source /etc/bash_completion.d/ee
```


