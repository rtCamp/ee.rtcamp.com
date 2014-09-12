### EE Stack Services

All EasyEngine services can be operated using following commands:

1. [[Start NGINX, PHP, MySQL & Postfix service|Stack-Services#start-nginx-php-mysql--postfix-service]]
1. [[Stop NGINX, PHP, MySQL & Postfix service|Stack-Services#stop-nginx-php-mysql--postfix-service]]
1. [[Reload NGINX, PHP, MySQL & Postfix service|Stack-Services#reload-nginx-php-mysql--postfix-service]]
1. [[Restart NGINX, PHP, MySQL & Postfix service|Stack-Services#restart-nginx-php-mysql--postfix-service]]

***

#### Start NGINX, PHP, MySQL & Postfix service
```bash
ee stack start
# Deprecated way
ee system start
```
Sample output:

```bash
^_^[root@example.com:~]# ee stack start
Executing service nginx start, please wait...
Executing service php5-fpm start, please wait...
Executing service mysql start, please wait...
Executing service postfix start, please wait...
```
#### Stop NGINX, PHP, MySQL & Postfix service
```bash
ee stack stop
# Deprecated way
ee system stop
```
Sample output:

```bash
^_^[root@example.com:~]# ee stack stop
Executing service nginx stop, please wait...
Executing service php5-fpm stop, please wait...
Executing service mysql stop, please wait...
Executing service postfix stop, please wait...
```
#### Reload NGINX, PHP, MySQL & Postfix service
```bash
ee stack reload
# Deprecated way
ee system reload
```
Sample output:

```bash
^_^[root@example.com:~]# ee stack reload
Executing service nginx reload, please wait...
Executing service php5-fpm reload, please wait...
Executing service mysql reload, please wait...
Executing service postfix reload, please wait...
```
#### Restart NGINX, PHP, MySQL & Postfix service
```bash
ee stack restart
# Deprecated way
ee system restart
```
Sample output:

```bash
^_^[root@example.com:~]# ee stack restart
Executing service nginx restart, please wait...
Executing service php5-fpm restart, please wait...
Executing service mysql restart, please wait...
Executing service postfix restart, please wait...
```
