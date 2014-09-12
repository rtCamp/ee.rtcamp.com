Though EasyEngine is command line tool, there are plenty of web-based tools and scripts which can make server administration easy.

Till version 1.2, these tools were accessible with /ee/ URL prefix. As number of tools grew, we moved them to dedicated port 22222 for better management of growing list of admin tools and also for security

### **Admin Tools & Scripts**
- **/db folder**    : PhpMyAdmin, Adminer and Anemometer
- **/php folder**   : info.php file with phpinfo for production php fool and webgrind for xdebug profiling analysis
- **/fpm folder**   : status page for each fpm pool
- **/cache folder** : memcache, opcache and nginx-fastcgi cache viewer/cleaner


All these tools are hosted under as a PHP site at location /var/www/22222. We choose to name site itself as 22222 so it will easily standout from other sites.

You can add/remove other tools & scripts in /var/www/22222/htdocs. You can disable or even delete admin tools using ee site commands. But rest assured, they are secure as you can read below!

### **Port 22222 & Security**

You can open port 22222 (5-times two) on any IP or site hosted on your server. It uses HTTPs with a self-signed certificate. Your browser may complain about SSL certificate but you can ignore it. Your connection to server will be still encrypted.

If you prompted for username & password, default will be easyengine. You can change username and password by  `ee secure --auth` command.