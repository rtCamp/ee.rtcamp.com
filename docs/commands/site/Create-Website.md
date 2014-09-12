# **EasyEngine** **(ee)**
### **Create Website**
1. [[HTML Website|Create-Website#html-website]]
1. [[PHP Website|Create-Website#php-website]]
1. [[PHP+MySQL Website|Create-Website#phpmysql-website]]
1. [[WordPress Website|Create-Website#wordpress-site]]

***

##### **HTML Website**

```bash
ee site create example.com
# Another way  
ee site create example.com --html
```

Sample Output:
```bash
^_^[root@example.com:~]# ee site create example.com
Creating example.com, please wait...
Creating symbolic link for example.com
Creating htdocs & logs directory
Changing ownership of /var/www/example.com, please wait...
Git commit on /etc/nginx/, please wait...
Successfully Created New Website: http://example.com
```


##### PHP Website

```bash
ee site create example.com --php
```

Sample Output:
```bash
^_^[root@example.com:~]# ee site create example.com
Creating example.com, please wait...
Creating symbolic link for example.com
Creating htdocs & logs directory
Changing ownership of /var/www/example.com, please wait...
Git commit on /etc/nginx/, please wait...
Successfully Created New Website: http://example.com
```


##### PHP+MySQL Website

```bash
ee site create example.com --mysql
```
Sample Output:
```bash
^_^[root@example.com:~]# ee site create example.com
Creating example.com, please wait...
Creating symbolic link for example.com
Creating htdocs & logs directory
Changing ownership of /var/www/example.com, please wait...
Git commit on /etc/nginx/, please wait...
Successfully Created New Website: http://example.com
```

_NOTE: You can find MySQL database details at `/var/www/example.com/ee-config.php`_

#### WordPress Site

EasyEngine can create wordpress sites with or without cache configuration. EasyEngine also can create WordPress multisites. This section covers ee site creation with wordpress.

Lets create example.com in various ways.

##### [[Standard WordPress Sites|EE WPSINGLE]]

```bash
ee site create example.com --wp                  # install wordpress without any page caching
ee site create example.com --w3tc                # install wordpress with w3-total-cache plugin 
ee site create example.com --wpsc                # install wordpress with wp-super-cache plugin 
ee site create example.com --wpfc                # install wordpress + nginx fastcgi_cache
```

_NOTE: You can find sample output of above command [[here|EE WPSINGLE]]_
##### [[WordPress Multisite with subdirectory|EE-WPSUBDIRECTORY]]

```bash
ee site create example.com --wpsubdir            # install wpmu-subdirectory without any page caching
ee site create example.com --wpsubdir --w3tc     # install wpmu-subdirectory with w3-total-cache plugin 
ee site create example.com --wpsubdir --wpsc     # install wpmu-subdirectory with wp-super-cache plugin 
ee site create example.com --wpsubdir --wpfc     # install wpmu-subdirectory + nginx fastcgi_cache
```
_NOTE: You can find sample output of above command [[here|EE-WPSUBDIRECTORY]]_

##### [[WordPress Multisite with subdomain|EE-WPSUBDOMAIN]] 

```bash
ee site create example.com --wpsubdom            # install wpmu-subdomain without any page caching
ee site create example.com --wpsubdom --w3tc     # install wpmu-subdomain with w3-total-cache plugin 
ee site create example.com --wpsubdom --wpsc     # install wpmu-subdomain with wp-super-cache plugin 
ee site create example.com --wpsubdom --wpfc     # install wpmu-subdomain + nginx fastcgi_cache
```
_NOTE: You can find sample output of above command [[here|EE-WPSUBDOMAIN]]_

### Cheatsheet - Site creation


|                    |  Single Site  | 	Multisite w/ Subdir  |	Multisite w/ Subdom  |
|--------------------|---------------|-----------------------|-----------------------|
| **NO Cache**       |  	  --wp     |	    --wpsubdir       |	     --wpsubdom      |
| **WP Super Cache** |	  --wpsc     |	  --wpsubdir --wpsc  |  	--wpsubdom --wpsc  |
| **W3 Total Cache** |    --w3tc     |	  --wpsubdir --w3tc  |  	--wpsubdom --w3tc  |
| **Nginx cache**    |    --wpfc     |    --wpsubdir --wpfc  |  	--wpsubdom --wpfc  |


***