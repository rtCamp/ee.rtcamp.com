# **EasyEngine** **(ee)**
### **Purge Mail Packages**
```bash
ee stack purge mail
````
This command will purge all mail server packages.

Sample output:
```bash
^_^[root@example.com:~]# ee stack purge mail
purge Dovecot package, please wait...
Reading package lists...
Building dependency tree...
Reading state information...
The following packages will be REMOVED:
  dovecot-core* dovecot-imapd* dovecot-lmtpd* dovecot-managesieved*
  dovecot-mysql* dovecot-pop3d* dovecot-sieve*
0 upgraded, 0 newly installed, 7 to remove and 59 not upgraded.
After this operation, 11.7 MB disk space will be freed.
[...]
.
.
[...]
Processing triggers for man-db (2.6.7.1-1) ...
Removing Roundcube dependencies, please wait...
Removing Roundcube, please wait...
Removing unwanted packages, please wait...
Reading package lists...
[...]
.
.
[...]
Removing libunix-syslog-perl (1.1-2build5) ...
Removing pax (1:20120606-2+deb7u1) ...
Removing re2c (0.13.5-1build2) ...
Removing spamc (3.4.0-1ubuntu1) ...
Removing librpm3 (4.11.1-3) ...
Removing librpmio3 (4.11.1-3) ...
Removing liblua5.2-0:amd64 (5.2.3-1) ...
Removing libnss3:amd64 (2:3.15.4-1ubuntu7) ...
Removing libnss3-nssdb (2:3.15.4-1ubuntu7) ...
Removing libnspr4:amd64 (2:4.10.2-1ubuntu1.1) ...
Processing triggers for man-db (2.6.7.1-1) ...
Processing triggers for libc-bin (2.19-0ubuntu6) ...
Successfully purged mail server packages
```
