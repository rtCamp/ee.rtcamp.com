#### :warning:**Warning : Please, Do not try this beta version on your live/production server.**
After major efforts and wait for you, We are happy to announce beta release of EasyEngine (ee) Mail 2.1.0 


### **How to install EasyEngine (ee) beta on fresh server?**
####  **Prerequisite:**
Before install EasyEngine (ee), your system should satisfy our [[Prerequisite]] 

#### **Install EasyEngine (ee):**
```bash
wget -qO ee rt.cx/eebeta && sudo bash ee mail 
```
#### **Install all packages:**
```bash
ee stack install all
```
This will install and configure web server and mail server packages


#### **Install web server packages:**
```bash
ee stack install
# Another Way
ee stack install web
```
This will install and configure web server packages 

#### **Install mail server packages:**
```bash
ee stack install mail
```
This will install and configure web server packages

#### **Completing ViMbAdmin Setup:**
1. Point your browser to https://example.com:22222/vimbadmin
1. Copy security Salts
1. Now open terminal, open following file

 ```bash
 vim /var/www/22222/htdocs/vimbadmin/application/configs/application.ini
 ```
 and replaces following line with security copied security salts

 ```bash
 securitysalt                       = ""
 resources.auth.oss.rememberme.salt = ""
 defaults.mailbox.password_salt     = ""
 ```
1. Now on browser, add your Administrator id and password for ViMbAdmin and click on `activate my account`

Now on ViMbAdmin you can create mail boxes for domains.

Now to access webmail use this url: http://webmail.example.com


Let us know us your beta testing reviews on [![EasyEngine chat](https://badges.gitter.im/rtCamp/easyengine.png)](https://gitter.im/rtCamp/easyengine)
