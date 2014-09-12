# **EasyEngine (ee)**


### **Site Delete**
1. [[Delete website|https://github.com/rtCamp/easyengine/wiki/Delete-Website#delete-website]]
2. [[Delete website without prompt|https://github.com/rtCamp/easyengine/wiki/Delete-Website#delete-website-without-prompt]]
3. [[Delete website webroot only|https://github.com/rtCamp/easyengine/wiki/Delete-Website#delete-website-webroot-only]]
4. [[Delete website database only|https://github.com/rtCamp/easyengine/wiki/Delete-Website#delete-website-database-only]]

***

#### Delete website:
To delete site created with EasyEngine (ee) use
```bash
ee site delete example.com 
```
Sample output:
```bash
^_^[root@example.com:~]# ee site delete example.com 
 DB_NAME = example_com 
 DB_USER = example_com 
 DB_HOST = localhost
Are you sure to drop example_com database (y/n): y
Are you sure to remove example.com webroot (y/n): y
Are you sure to remove example.com NGINX configuration (y/n): y
Git commit on /etc/nginx/, please wait...
Executing service nginx reload, please wait...
``` 

#### Delete website without prompt:
```bash
ee site delete example.com --no-prompt 
```
Sample output:
```bash
^_^[root@example.com:~]# ee site delete example.com --no-prompt
DB_NAME = example_com 
DB_USER = example_com 
DB_HOST = localhost
Git commit on /etc/nginx/, please wait...
Executing service nginx reload, please wait...
```

#### Delete website webroot only:
```bash
ee site delete example.com --files
```

Sample output:
```bash
^_^[root@example.com:~]# ee site delete example.com --files
Are you sure to remove example2.com webroot (y/n): y
```

#### Delete website database only:
```bash
ee site delete example.com --db 
```
Sample output:
```bash
^_^[root@example.com:~]# ee site delete example.com --db
DB_NAME = example_com 
DB_USER = example_com 
DB_HOST = localhost
Are you sure to drop ex_com database (y/n): y
```
