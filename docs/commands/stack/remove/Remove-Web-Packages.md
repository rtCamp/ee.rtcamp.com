# **EasyEngine** **(ee)**
### **Remove web Packages**

1. [[Remove Web Packages|https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-Web-packages]]
1. [[Remove NGINX | https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-nginx]] 
1. [[Remove PHP | https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-php]]
1. [[Remove MySQL |https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-mysql]]
1. [[Remove Postfix |https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-postfix]]
1. [[Remove WP-CLI |https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-wp-cli]]
1. [[Remove Adminer|https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-adminer]]
1. [[Remove phpMyAdmin|https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-phpmyadmin]]
1. [[Remove Utilities|https://github.com/rtCamp/easyengine/wiki/Remove-Web-Packages#remove-utilities]]

***
#### **Remove Web packages**
```bash 
ee stack remove
# Another way
ee system remove web
```
Sample output:
```bash
^_^[root@example.com:~]# ee stack remove
remove nginx-custom package, please wait...
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
Successfully removed all packages
```
Above command removes all packages installed by `ee stack install`

If you are thinking removing all packages is not suitable for you, can remove single packages by using following commands:

#### **[[Remove NGINX|http://nginx.org/]]**
```bash
ee stack remove nginx
# Deprecated way
ee system remove nginx
```

#### **[[Remove PHP|https://php.net/]]**
```bash
ee stack remove php
# Deprecated way
ee system remove php
```

#### **[[Remove MySQL|http://www.mysql.com/]]**
```bash
ee stack remove mysql
# Deprecated way
ee system remove mysql
```
#### **[[Remove Postfix|http://www.postfix.org/]]**
```bash
ee stack remove postfix
# Deprecated way
ee system remove postfix
```
#### **[[Remove WP-CLI|https://github.com/wp-cli/wp-cli]]**

```bash
ee stack remove wpcli
# Deprecated way
ee system remove wpcli
```
#### **[[Remove Adminer|http://www.adminer.org/]]**

```bash
ee stack remove adminer
# Deprecated way
ee system remove adminer
```
#### **[[Remove phpMyAdmin|http://www.phpmyadmin.net/]]**
```bash
ee stack remove phpMyAdmin
# Deprecated way
ee system remove phpmyadmin
```
#### **[[Remove Utilities|https://github.com/rtCamp/easyengine/wiki/Stack-Remove#remove-utilities]]**

Below command remove phpMemcachedAdmin, FastCGI cleanup script, OPcache, Webgrind, Anemometer.
```bash
ee stack remove utils
# Deprecated way
ee system remove utils
```