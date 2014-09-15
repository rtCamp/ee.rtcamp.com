# **EasyEngine** **(ee)**

1. **[[Basic (--basic) to FastCGI (--wpfc)|https://github.com/rtCamp/easyengine/wiki/Change-WordPress-Cache#basic---basic-to-fastcgi---wpfc]]**
1. **[[Super Cache (--wpsc) to FastCGI (--wpfc)|https://github.com/rtCamp/easyengine/wiki/Change-WordPress-Cache#super-cache---wpsc-to-fastcgi---wpfc]]**
1. **[[W3 Total Cache (--w3tc) to FastCGI (--wpfc)|https://github.com/rtCamp/easyengine/wiki/Change-WordPress-Cache#w3-total-cache---w3tc-to-fastcgi---wpfc]]**

### **Basic (--basic) to FastCGI (--wpfc)**
```bash
ee site edit example.com
```
**Change following settings:**

**Old value:**
```bash
# WPSINGLE BASIC NGINX CONFIGURATION
include common/php.conf;
```

**New value:**
```bash
# WPSINGLE FAST CGI NGINX CONFIGURATION
include common/wpfc.conf;
```

Your new configuration look like [[this|https://github.com/rtCamp/easyengine/blob/stable/templates/nginx/wp/wpfc.conf]]

**Install Plugins:**

1. Nginx Helper
1. W3 Total Cache

How to configure above plugin : [[Click Here|https://github.com/rtCamp/easyengine/wiki/EE-WPSINGLE#configure-plugins-1]]

### **Super Cache (--wpsc) to FastCGI (--wpfc)**
```bash
ee site edit example.com
```
**Change following settings:**

**Old value:**
```bash
# WPSINGLE WP SUPER CACHE NGINX CONFIGURATION
include common/wpsc.conf;
```

**New value:**
```bash
# WPSINGLE FAST CGI NGINX CONFIGURATION
include common/wpfc.conf;
```

Your new configuration look like [[this|https://github.com/rtCamp/easyengine/blob/stable/templates/nginx/wp/wpfc.conf]]

**Install Plugins:**

1. Nginx Helper
1. W3 Total Cache

How to configure above plugin : [[Click Here|https://github.com/rtCamp/easyengine/wiki/EE-WPSINGLE#configure-plugins-1]]
### **W3 Total Cache (--w3tc) to FastCGI (--wpfc)**
```bash
ee site edit example.com
```
**Change following settings:**

**Old value:**
```bash
# WPSINGLE W3 TOTAL CACHE NGINX CONFIGURATION
include common/w3tc.conf;
```

**New value:**
```bash
# WPSINGLE FAST CGI NGINX CONFIGURATION
include common/wpfc.conf;
```

Your new configuration look like [[this|https://github.com/rtCamp/easyengine/blob/stable/templates/nginx/wp/wpfc.conf]]

**Install Plugins:**

1. Nginx Helper
1. W3 Total Cache

How to configure above plugin : [[Click Here|https://github.com/rtCamp/easyengine/wiki/EE-WPSINGLE#configure-plugins-1]]