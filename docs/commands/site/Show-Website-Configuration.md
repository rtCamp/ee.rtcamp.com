# **EasyEngine (ee)**
### **Show Website Configuration:**

Nginx configuration for the website can be viewed with

```bash
ee site show example.com
```
Sample output:
```bash
^_^[root@example.com:~]# ee site show example.com 
Display NGINX configuration for example.com
# WPSINGLE FAST CGI NGINX CONFIGURATION

server {

	server_name example.com www.example.com;

	access_log   /var/log/nginx/example.com.access.log rt_cache;
	error_log    /var/log/nginx/example.com.error.log;

	root /var/www/example.com/htdocs;
	index index.php index.htm index.html;

	include common/wpfc.conf;
	include common/wpcommon.conf;
	include common/locations.conf;

}

```
above command will show the output of /etc/nginx/sites-available/example.com file.