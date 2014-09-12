# **EasyEngine** **(ee)**
### **Install Web Packages**

1. [[Install Web packages|https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-web-packages]]
1. [[Install NGINX |https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-nginx]] 
1. [[Install PHP | https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-php]]
1. [[Install MySQL |https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-mysql]]
1. [[Install Postfix |https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-postfix]]
1. [[Install WP-CLI |https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-wp-cli]]
1. [[Install Adminer|https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-adminer]]
1. [[Install phpMyAdmin|https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-phpmyadmin]]
1. [[Install Utilities|https://github.com/rtCamp/easyengine/wiki/Web-Packages-Install#install-utilities]]

***
#### Install web packages:
```bash
ee stack install
# Another way
ee stack install web
```
Sample output:
```bash
^_^[root@example.com:~]# ee stack install
Adding rtCamp NGINX launchpad repository, please wait...
Adding Ondrej PHP5 launchpad repository, please wait...
Executing apt-get update, please wait...
Installing nginx-custom, please wait...
Reading package lists...
Building dependency tree...
Reading state information...
The following extra packages will be installed:
  libxslt1.1 nginx-common
The following NEW packages will be installed:
  libxslt1.1 nginx-common nginx-custom
0 upgraded, 3 newly installed, 0 to remove and 78 not upgraded.
Need to get 595 kB of archives.
After this operation, 1,692 kB of additional disk space will be used.
[...]
.
.
.
[...]
Setting up NGINX, please wait...
Generating SSL private key
Generating a certificate signing request (CSR)
Removing pass phrase from SSL private key
Generating SSL certificate
Setting up PHP5, please wait...
Setting up MySQL, please wait...
Executing service nginx restart, please wait...
Executing service php5-fpm restart, please wait...
Executing service mysql restart, please wait...
Git commit on /etc/nginx/, please wait...
Git commit on /etc/php5/, please wait...
Git commit on /etc/mysql/, please wait...
Git commit on /etc/postfix, please wait...
Downloading Adminer, please wait...
Downloading phpMyAdmin, please wait...
Downloading WP-CLI, please wait...
Installing phpMemcachedAdmin, please wait...
Downloading nginx FastCGI cleanup script, please wait...
Downloading OPcache, please wait...
Cloning Webgrind, please wait...
Cloning Anemometer, please wait...
Successfully installed web packages
Create your first WordPress site powered by NGINX using:
ee site create example.com --wp
```
Above command install all the require packages, now you can create your site using [[Site Module]]

_NOTE: By default EasyEngine set `easyengine:easyengine` as HTTP authentication_

_Refer: [[How to change HTTP Authentication|Secure-Module#changing-http-authentication-credentials]]_

If you are thinking installing all packages is not suitable for you, can install single packages by using following commands:

#### **[[Install NGINX|http://nginx.org/]]**
```bash
ee stack install nginx
# Deprecated way
ee system install nginx
```
_NOTE: By default EasyEngine set `easyengine:easyengine` as HTTP authentication_

_Refer: [[How to change HTTP Authentication|Secure-Module#changing-http-authentication-credentials]]_

#### **[[Install PHP|https://php.net/]]**
```bash
ee stack install php
# Deprecated way
ee system install php
```

#### **[[Install MySQL|http://www.mysql.com/]]**

```bash
ee stack install mysql
# Deprecated way
ee system install mysql
```
#### **[[Install Postfix|http://www.postfix.org/]]**

```bash
ee stack install postfix
# Deprecated way
ee system install postfix
```
#### **[[Install WP-CLI|https://github.com/wp-cli/wp-cli]]**

```bash
ee stack install wpcli
# Deprecated way
ee system install wpcli
```
#### **[[Install Adminer|http://www.adminer.org/]]**

```bash
ee stack install adminer
# Deprecated way
ee system install adminer
```
#### **[[Install phpMyAdmin|http://www.phpmyadmin.net/]]**
```bash
ee stack install phpMyAdmin
# Deprecated way
ee system install phpmyadmin
```
#### **[[Install Utilities|https://github.com/rtCamp/easyengine/wiki/Stack-Install#install-utilities]]**

Below command installs phpMemcachedAdmin, FastCGI cleanup script, OPcache, Webgrind, Anemometer.
```bash
ee stack install utils
# Deprecated way
ee system install utils
```