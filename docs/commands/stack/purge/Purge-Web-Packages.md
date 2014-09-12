# **EasyEngine** **(ee)**
### **Purge Web Packages**

1. [[Purge Web packages|https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-Web-packages]]
1. [[Purge NGINX | https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-nginx]] 
1. [[Purge PHP | https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-php]]
1. [[Purge MySQL |https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-mysql]]
1. [[Purge Postfix |https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-postfix]]
1. [[Purge WP-CLI |https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-wp-cli]]
1. [[Purge Adminer|https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-adminer]]
1. [[Purge phpMyAdmin|https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-phpmyadmin]]
1. [[Purge Utilities|https://github.com/rtCamp/easyengine/wiki/Purge-Web-Packages#purge-utilities]]

***
#### Purge Web packages

```bash 
ee stack purge
# Another way
ee stack purge web
```
Sample output:
```bash
^_^[root@example.com:~]# ee stack purge
purge nginx-custom package, please wait...
Reading package lists...
Building dependency tree...
Reading state information...
The following package was automatically installed and is no longer required:
  libxslt1.1
Use 'apt-get autoremove' to remove it.
The following packages will be REMOVED:
[...]
.
.
.
[...]
Removing Adminer, please wait...
Removing phpMyAdmin, please wait...
Removing WP-CLI, please wait...
Remove EasyEngine (ee) admin utilities, please wait...
Removing unwanted packages, please wait...
[...]
.
.
.
[...]
Successfully purged all packages
```
Above command removes all packages installed by `ee stack install`

If you are thinking removing all packages is not suitable for you, can remove single packages by using following commands:

#### **[[Purge NGINX|http://nginx.org/]]**
```bash
ee stack purge nginx
# Deprecated way
ee system purge nginx
```

#### **[[Purge PHP|https://php.net/]]**
```bash
ee stack purge php
# Deprecated way
ee system purge php
```
#### **[[Purge MySQL|http://www.mysql.com/]]**
```bash
ee stack purge mysql
# Deprecated way
ee system purge mysql
```
#### **[[Purge Postfix|http://www.postfix.org/]]**
```bash
ee stack purge postfix
# Deprecated way
ee system purge postfix
```
#### **[[Purge WP-CLI|https://github.com/wp-cli/wp-cli]]**

```bash
ee stack purge wpcli
# Deprecated way
ee system purge wpcli
```
#### **[[Purge Adminer|http://www.adminer.org/]]**

```bash
ee stack purge adminer
# Deprecated way
ee system purge adminer
```
#### **[[Purge phpMyAdmin|http://www.phpmyadmin.net/]]**
```bash
ee stack purge phpMyAdmin
# Deprecated way
ee system purge phpmyadmin
```
#### **[[Purge Utilities|https://github.com/rtCamp/easyengine/wiki/Stack-Purge#purge-utilities]]**

Below command remove phpMemcachedAdmin, FastCGI cleanup script, OPcache, Webgrind, Anemometer.
```bash
ee stack purge utils
# Deprecated way
ee system purge utils
```