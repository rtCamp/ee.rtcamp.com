# **EasyEngine** **(ee)**
## **Debug Module**
EasyEngine debug commands can be used to debug whole stack configuration or configuration for specific site.

1. [[Global options|https://github.com/rtCamp/easyengine/wiki/Debug-Module#global-options]]
1. [[Site options|https://github.com/rtCamp/easyengine/wiki/Debug-Module#site-options]]
1. [[Examples|https://github.com/rtCamp/easyengine/wiki/Debug-Module#examples]]

***
 
### **Global options**

These commands are used for server level debugging.
```bash
ee debug [Options]
Options :
         -i          # interactive debug.
         --nginx     # debug nginx.
         --rewrite   # debug nginx rewrite rules.
         --fpm       # debug FastCGI.
         --php       # debug php.
         --mysql     # debug mysql.
```
-**i** This option enables interactive debugging and stop the debugging once ctrl+c is pressed

 
--**nginx**   This option enables nginx `enable debug_connection` for ip_address enlisted in    /etc/easyengine/ee.conf. if ip_address is blank then its start debug_connection for 0.0.0.0/0 ip. 

--**rewrite** This option enable rewrite_log on in /etc/nginx/nginx.conf file

--**php** This option enable php-fpm slow log, xdebug profiling.

--**fpm** This option change PHP5-FPM log_level from notice to debug level.

--**mysql** This option enable mysql slow log.

***
### **Site options**

These commands are used for site level debugging.

```bash
ee debug [websitename] [Options]
Options :
         -i           # interactive debug.
         --nginx      # debug nginx.
         --rewrite    # debug nginx rewrite rules.
         --wp         # debug wordpress sites.
```
-**i** 
    This option enables interactive debugging and stop the debugging once ctrl+c is pressed

--**nginx**
    This option enables nginx error_log for example.com in debugging mode.

--**rewrite** 
    This option enable rewrite_log on for example.com

--**wp** 
    This option enable wp-content/debug.log logging [[Click here for more details|https://rtcamp.com/tutorials/wordpress/debugging/]] Also, installs developer plugin.

***

### Examples
Start Debugging

#### Global

```bash
ee debug 
ee debug --start
ee debug --nginx --rewrite --fpm --php --mysql  
```

To debug a specific part, you can use one or more command below:
```bash
ee debug  --php
ee debug  --nginx
ee debug  --rewrite
ee debug  --fpm
ee debug  --mysql
```

#### Site-wide

To start complete debugging for a site, please use either command below:
```bash
ee debug example.com
ee debug example.com --start
ee debug example.com --wp --nginx --rewrite  
```
To debug a specific part, you can use one or more command below:
```bash
ee debug example.com --wp
ee debug example.com --nginx
ee debug example.com --rewrite
```

***


### Trigger Xdebug Profiling

If you are using `--php` flag to analyse xdebug profiling information you may be surprised to see nothing in webgrind.

This is because easyengine has set xdebug to profile only on trigger. This is good for profiling live sites as xdebug profiling data take too much space.

Triggering is easy. You can use this browser extension to trigger profiling for [[Firefox|https://addons.mozilla.org/en-US/firefox/addon/the-easiest-xdebug/]] [[Chrome|https://chrome.google.com/extensions/detail/eadndfjplgieldjbigjakmdgkmoaaaoc]] [[Safari | https://github.com/benmatselby/xdebug-toggler]] [[Opera | http://addons.opera.com/extensions/details/xdebug-launcher/]]


    
    
   
   


