# EasyEngine (ee)

Note: This is only for testing purpose, not recommended for production server.

## Installation of HHVM:
For installation of HHVM please follow this guide:
https://github.com/facebook/hhvm/wiki/Prebuilt%20Packages%20for%20HHVM

## Post installation:
We need to configure our web server to use HHVM,
```bash
sudo /usr/share/hhvm/install_fastcgi.sh
```

## Configuring HHVM:
### Editing server.ini:
Open server.ini file:
```bash
vim /etc/hhvm/server.ini
```
If HHVM crashed then site must use PHP-FPM as fallback, so change HHVM server port from 9000 to 8000
```bash
hhvm.server.port = 8000
```

### Editing php.ini
Open php.ini file:
```bash
vim /etc/hhvm/php.ini
```
 Add following towards end of file:
```bash
hhvm.log.header = true
hhvm.log.natives_stack_trace = true
```

### Editing hhvm.conf:
Note: This editing is not required, as we are not using this file, but if have included hhvm.conf in your previous site then you also need to change HHVM port here.
```bash
vim /etc/nginx/hhvm.conf
```

and change HHVM port from 9000 to 8000:
```bash
fastcgi_pass   127.0.0.1:8000;
```

## Configuring FastCGI:
Open fastcgi.conf file:
```bash
vim /etc/nginx/conf.d/fastcgi.conf
```
and add following line towards end of file:
```bash
fastcgi_keep_conn on;
```

## Use HHVM and adding PHP5-FPM as fallback:
Open Upstream.conf file:
```bash
vim /etc/nginx/conf.d/upstream.conf
```

and make sure it look like this:
```bash
# Common upstream settings

upstream php {
	# server unix:/run/php5-fpm.sock;
	server 127.0.0.1:8000;
    server 127.0.0.1:9000 backup;
}

upstream debug {
	# Debug Pool
	server 127.0.0.1:9001;
}
```

## Restart Services:
```bash
service hhvm restart
php5-fpm -t && service php5-fpm restart
nginx -t && service nginx restart
```

## Testing:
1. Using web browser:
Just point your browser to https://example.com:22222/php/info.php, if you are seeing `HipHop` then, your server is using HHVM, otherwise it is using FPM
1. Using CURL:
Use following command to test from command line:
```bash
curl -I example.com
```

If you are able to see line like this:
```bash
X-Powered-By: HHVM/3.2.0
```
then your site is using HHVM, otherwise FPM


***

* We also like to know to your experience for HHVM with EE, for that you can comment here: [#180](https://github.com/rtCamp/easyengine/issues/180)   .
* If your configuration is better that us or you feel like we are missing something you can use our HHVM support checlist [#199](https://github.com/rtCamp/easyengine/issues/199) 
