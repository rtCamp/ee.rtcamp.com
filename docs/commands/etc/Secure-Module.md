# **EasyEngine (ee)**
## **Secure**
EasyEngine (ee) manages security for webserver through these ways.  Editing these security parameters is provided in version 2.0.0

1. [[Changing HTTP Authentication credentials|https://github.com/rtCamp/easyengine/wiki/Secure-Module#changing-http-authentication-credentials]]
1. [[Changing admin Port|https://github.com/rtCamp/easyengine/wiki/Secure-Module#changing-admin-port]]
1. [[Whitelisting IP's|https://github.com/rtCamp/easyengine/wiki/Secure-Module#whitelisting-ips]]

***
### **Changing HTTP authentication credentials**
HTTP authentication credentials can be changed with this command.
```bash
ee secure --auth
```
This will prompt you to enter username and password, if you don't enter anything it will set default username and password as easyengine.

```bash
Provide HTTP authentication user name [easyengine]: user
Provide HTTP authentication password [easyengine]: 
Executing service nginx reload, please wait...
```

***

### **Changing Admin Port**

EasyEngine (ee)  provides access to its web utilities through registered port 22222, it can be customized using

```bash
ee secure --port
```
This command will ask you to enter the port you want to setup for accessing web utilities of EasyEngine (ee).

```bash
EasyEngine admin port [22222]: 55555  
Executing service nginx reload, please wait...
```

***


### **Whitelisting IP's**
EasyEngine (ee) can whitelist IP's, which can be done using
```bash
ee secure --ip
```
The list of IP addresses, should be provided in comma seperated format for whitelisting them. By default 127.0.0.1 will be the whitelisted IP address. 

```bash
Enter the comma separated IP addresses to white list [127.0.0.1]: 1.2.3.4, 2.3.6.4,2.3.9.8
Executing service nginx reload, please wait...
```