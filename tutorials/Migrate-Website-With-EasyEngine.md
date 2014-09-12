# **EasyEngine** **(ee)**
## **Site Migration**

1. [[Assumption|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#assumption]]
1. [[Export Database|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#export-database]]
1. [[Server Setup|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#server-setup]]
1. [[ Install Packages|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#install-packages]]
1. [[Website Creation|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#website-creation]]
1. [[Copy Webroot|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#copy-webroot]] 
1. [[Import Database|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#import-database]]
1. [[Test New Server|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#test-new-server]]

***
### **Assumption:**
**OLD SERVER IP:** 1.1.1.1

**NEW SERVER IP:** 2.2.2.2

**DOMAIN NAME:** example.com

### **Export Database:**
We need to run folloing command on OLD SERVER (1.1.1.1)
```bash
mysqldump -u root -p example.com > /tmp/example.com.sql
```

### **Server Setup:**
On new server you need to [[Install EasyEngine|Installation]]

### **Install Packages:**
```bash
ee stack install
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
Successfully installed all packages
Create your first WordPress site powered by NGINX using:
ee site create example.com --wp
```

_NOTE: By default EasyEngine set `easyengine:easyengine` as HTTP authentication_

_Refer: [[How to change HTTP Authentication|Secure-Module#changing-http-authentication-credentials]]_


### **Website Creation**
By default EasyEngine used `wp_` as WordPress table_prefix. 
If your old website used custom prefix then [[check this|https://github.com/rtCamp/easyengine/wiki/EasyEngine-Config-File#prefix]] how to force EasyEngine to ask WordPress table_prefix

```bash
ee site create example.com --wp
```
Sample Output : 
```bash
^_^[root@example.com:~]# ee site create example.com --wp
Creating example.com, please wait...
Creating symbolic link for example.com
Creating htdocs & logs directory
Downloading WordPress, please wait...
Setting up WordPress, please wait...
Updating WordPress permalink, please wait...
Installing Nginx Helper plugin, please wait...
Changing ownership of /var/www/example.com, please wait...
Git commit on /etc/nginx/, please wait...
Executing service nginx reload, please wait...

WordPress Admin Username: admin
WordPress Admin Password: CV1JtR0MfUdaDcQ

Successfully created new website: http://example.com
```
### **Copy Webroot**
Delete Webroot files on new server and copied it from old server.
```bash
rm -rf /var/www/example.com/htdocs/*
rsync -avz --progress root@1.1.1.1:/var/www/example.com/htdocs/* /var/www/example.com/htdocs/
``` 

### **Import Database**
Remember we [[export database|https://github.com/rtCamp/easyengine/wiki/Migrate-Website-With-EasyEngine#export-database]] on old server, now its time to import that database on new server.
```bash
rsync -avz --progress root@1.2.3.4:/tmp/example.com.sql /tmp
pv /tmp/example.com.sql | mysql example_com
```
### **Test New Server**

Lets test the site before pointing DNS.

You need to modify your local system `/etc/hosts` file
```bash
vim /etc/hosts

2.2.2.2 example.com www.example.com
```
Lets open example.com in your web-browser and  test if all looks good then update your DNS record.
