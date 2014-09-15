# **EasyEngine** **(ee)**
## **FAQ**

#### **What is EasyEngine (ee)?**
EasyEngine is a linux shell-script used to manage sites that run WordPress or PHP on the nginx web-server a popular alternative to Apache.

#### **How to fix: `/usr/local/sbin/ee: Permission denied`**
EasyEngine keep its executable in folder `/usr/local/sbin/ee` . The executables in this folder are accessible by either root user or using sudo, so you need to execute:
```bash
sudo ee stack install
```

#### **How to access EasyEngine admin tools?**
EasyEngine admin tools can be accessed using 2222 port. `https://example.com:22222`.

#### **How to access phpMyAdmin installed with EasyEngine?**
phpMyadmin is listed under db section in EasyEngine admin tools. So to access phpMyadmin use `https://example.com:22222/db/pma/`

#### **How to use other port than 22222?**

To modify the port use command `ee secure --port` and modify port there.

form better and faster than Apache, particularly when the number of concurrent site visitors is on the rise.

#### **Where to find MySQL username & Password?**

Suppose you have run `ee stack install`. MySQL username and password are stored in `.my.cnf` file. The Location of file depends on which user runs `ee stack install`. i.e  `root@vagrant-ubuntu-trusty-32:~# sudo ee stack install` command creates file in home directory of sudo user i.e here in `/home/harshad/.my.cnf` and  `root@vagrant-ubuntu-trusty-32:~# ee stack install` run with root user creates file at `/root/.my.cnf` location.  

#### **Does EasyEngine work with shared hosting?**

No. Shared hosting services do not allow root or sudo access, which is required to install EasyEngine.

####  **How to force EasyEngine to ask for permission before installing any package?**

Open the following file in your favorite text editor and set `apt-get-assume-yes=true`

`vim /etc/easyengine/ee.conf`

#### **How to fix "E: There are problems and -y was used without --force-yes" ?**
Open the  file `/etc/easyengine/ee.conf` in your favorite text editor and set `gpg-keys-fix=true`

####  **Where to check EasyEngine(ee) logs?**

EasyEngine maintains logs in directory `/var/log/easyengine` 

- install logs in `install.log` file

- error logs in `error.log` file 

- command logs in `ee.log`


####  **Can I get to know the various subcommands for every command in EasyEngine?**

Yes. Simply press the tab key on your keyboard after typing the command.
For example, if you want to know the subcommands related to 'site', type this:

`ee site`

and then press the tab key on your keyboard.

#### **What should be done if the tab key does not suggest available subcommands?**

Run this command to fix this:

`source /etc/bash_completion.d/ee`

####  **How to change mysql host from localhost to another host?**

Open the following file in your favorite text editor and set 'mysqlhost=rtcamp.com'

`vim /etc/easyengine/ee.conf`


#### **How to set a custom database name for website?**

Open the following file in your favorite text editor

`vim /etc/easyengine/ee.conf`

and set

`db-name = true`

in mysql section.


####  **How to create a custom database user for website?**

Open the following file in your favorite text editor and set `db-user = true`

`vim /etc/easyengine/ee.conf`


####  **How to change the wordpress database table prefix?**

Open the  file `vim /etc/easyengine/ee.conf` in your favorite text editor and set `prefix = true` in wordpress section. Now after this, when you create any wordpress site it is going to ask you database table prefix.

####  **How to change wordpress admin username?**

Open the following file in your favorite text editor and set `user = rtcamp`

`vim /etc/easyengine/ee.conf`

This will be the username for wordpress sites you create in future.


####  **How to set custom WordPress admin password rather than random?**

Open the following file in your favorite text editor and set `password = mypass`

`vim /etc/easyengine/ee.conf`

####  **How to change wordpress email?**

Open the following file in your favorite text and editor set `email = yourmail@example.com`

`vim /etc/easyengine/ee.conf`

#### **How to set default page or site when any site on server is disabled?**
 
Edit default site config

``` ee site edit default ```

Add following line after ``` server { ``` line:


``` listen   80 default_server; ```

Then enable default site 
```ee site enable default```

This will make sure nginx’s default site (the one you see when you type site’s IP address in browser) shows up for any non existent domain.

If you see “Welcome to nginx!” page after this, you can edit that default page content by editing html file – ``` /usr/share/nginx/www/index.html ``` 


#### **Resolving ViMbAdmin Memcache glitch**
If you are facing this error:
```bash
Fatal error: session_start(): Failed to initialize storage module: memcache
```
Then two resolve this:
```bash
vim /var/www/22222/htdocs/vimbadmin/application/configs/application.ini +624
````

and comment this line:
```bash
;resources.session.save_path = APPLICATION_PATH "/../var/session"
```

#### Unable to Install mail server, getting error `Found installed Dovecot Packages server, exit status= 1`

In EasyEngine we have taken precaution that, it will not touch your current mail server setup either, it is installed by EasyEngine or manully installed by you self.

Still if you want to reinstall current mail server setup assuming that it was installed by EasyEngine, then use following commands:

```bash
ee stack purge mail
ee stack install mail
```