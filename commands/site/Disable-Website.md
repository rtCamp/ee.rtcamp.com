# **EasyEngine (ee)**
### **Disable website:**

```bash
ee site disable example.com
```
Sample output:
```bash
^_^[root@example.com:~]# ee site disable example.com 
Removing symbolic link for example.com
Executing service nginx reload, please wait...
Git commit on /etc/nginx/, please wait...
```

Above command will remove symbolic link example.com in `/etc/nginx/sites-enabled/example.com` to `/etc/nginx/sites-available/example.com`
