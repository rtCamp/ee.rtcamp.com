# **EasyEngine (ee)**


1. [[Get Version | https://github.com/rtCamp/easyengine/wiki/Other-commands#display-easyengine-version ]]
1. [[Get Help | https://github.com/rtCamp/easyengine/wiki/Other-commands#easyengine-help ]]
1. [[Get Information about NGINX, PHP and MySQL | https://github.com/rtCamp/easyengine/wiki/Other-commands#display-nginx-information ]]



### **Display EasyEngine Version**
```bash 
ee version 
```
Sample output:
```bash
^_^[root@example.com:~]# ee version
EasyEngine (ee) version: 2.0.1
```

### **EasyEngine Help**
```bash
ee help
```
### **Display NGINX Information**
```bash
ee info nginx
```
Sample output:
```bash
^_^[root@example.com:~]# ee info nginx
NGINX (1.6.0):
user				         www-data
worker_processes		     auto
worker_connections		     4096
keepalive_timeout		     30
fastcgi_read_timeout		 300
client_max_body_size		 100m
allow				         127.0.0.1 192.168.33.1 
```
### **Display PHP Information**
```bash
ee info php
```
Sample output:
```bash
^_^[root@example.com:~]# ee info php
PHP (5.5.15RC1):
user				             www-data
expose_php			             Off
memory_limit			         128M
post_max_size			         100M
upload_max_filesize		         100M
max_execution_time		         300

Information about www.conf
ping.path			             /ping
pm.status_path			         /status
process_manager			         ondemand
pm.max_requests			         500
pm.max_children			         100
pm.start_servers		         20
pm.min_spare_servers		     10
pm.max_spare_servers		     30
request_terminate_timeout	     300
xdebug.profiler_enable_trigger	 off
listen					 	     127.0.0.1:9000

Information about debug.conf
ping.path			             /ping
pm.status_path			         /status
process_manager			         ondemand
pm.max_requests			         500
pm.max_children			         100
pm.start_servers		         20
pm.min_spare_servers		     10
pm.max_spare_servers		     30
request_terminate_timeout	     300
xdebug.profiler_enable_trigger	 on
listen					 	     127.0.0.1:9001
```
### **Display MySQL Information**
```bash
ee info mysql
```
Sample output:
```bash
^_^[root@example.com:~]# ee info mysql
MySQL (5.5.37):
user				             root
port				             3306
wait_timeout			         30
interactive_timeout		         60
max_used_connections		     5/151
datadir				             /var/lib/mysql/
socket				             /var/run/mysqld/mysqld.sock
```
 
### **Display Complete Information**
Display Complete Information using command
```bash
ee info
```



