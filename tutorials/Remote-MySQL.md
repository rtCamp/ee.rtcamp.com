# **EasyEngine** **(ee)**

## **Remote MySQL Server Setup:**
1. [[Allow Remote Access|https://github.com/rtCamp/easyengine/wiki/Remote-MySQL#allow-remote-access]]
1. [[Grant Remote Access|https://github.com/rtCamp/easyengine/wiki/Remote-MySQL#grant-remote-access]]

## **EasyEngine Server Setup:**
1. [[Provide Remote MySQL Credential|https://github.com/rtCamp/easyengine/wiki/Remote-MySQL#provide-remote-mysql-credential]]
1. [[Provide MySQL Grant Host Information|https://github.com/rtCamp/easyengine/wiki/Remote-MySQL#provide-mysql-grant-host-information]]
1. [[Install MySQL Client|https://github.com/rtCamp/easyengine/wiki/Remote-MySQL#install-mysql-client]]

### **Allow Remote Access:**
If you would like to access remote MySQL server from EasyEngine, You have to adjust some settings on remote MySQL server. 

```bash
vim /etc/mysql/my.cnf

# skip-networking 
bind-address = <PUBLIC_IP_OF_EASYENGINE_SERVER>
```

**Now restart MySQL server:**
```bash
service mysql restart
```

### **Grant Remote Access:**

```bash
mysql -u root -p

mysql > grant all privileges on *.* to 'root'@'<PUBLIC_IP_OF_EASYENGINE_SERVER>'  IDENTIFIED BY 'REMOTE_MySQL_PASSWORD' with grant option;
mysql> flush privileges;
```

### **Provide Remote MySQL Credential:**
For MySQL credential EasyEngine used `~/.my.cnf` file.
We need to add remote MySQL server details in `~/.my.cnf` file

```bash
vim ~/.my.cnf

[client]
host=<REMOTE_MYSQL_HOST>
user=<REMOTE_MYSQL_USER>
password=<REMOTE_MYSQL_PASSWORD>
```

### **Provide MySQL Grant Host Information:**

```bash
vim /etc/easyengine/ee.conf

[mysql]
    grant-host=<PUBLIC_IP_OF_EASYENGINE_SERVER>
```

### **Install MySQL Client:**
```bash
apt-get update
apt-get install mysql-client
```

### Notes:
We used following variables:

1. REMOTE_MYSQL_HOST = Remote MySQL server IP address/FQDN
1. REMOTE_MYSQL_USER = Remote MySQL server username
1. REMOTE_MYSQL_PASSWORD = Remote MySQL server password
1. PUBLIC_IP_OF_EASYENGINE_SERVER = EasyEngine server public IP address/FQDN
1. REMOTE_MySQL_PASSWORD = Remote MySQL password for root user

If your EasyEngine server don't have static public IP address then 
`PUBLIC_IP_OF_EASYENGINE_SERVER = %`

Now you can create any website with EasyEngine and now EasyEngine used your remote MySQL server for database creation.