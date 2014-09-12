# **EasyEngine (ee)**
### **Enable website:**

```bash
ee site enable example.com
```
Sample output:
```bash
^_^[root@example.com:~]# ee site enable example.com 
Creating symbolic link for example.com
Executing service nginx reload, please wait...
Git commit on /etc/nginx/, please wait...
```

Above command create the symbolic link from `/etc/nginx/sites-available/example.com` to `/etc/nginx/sites-enabled/example.com` so that site can accessible in browser.
