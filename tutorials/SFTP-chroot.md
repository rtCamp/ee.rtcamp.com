# **EasyEngine (ee)**

1. **[[Setup User/Group|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-usergroup]]**
1. **[[Setup Chroot Directory|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-chroot-directory]]**
1. **[[Setup SFTP Chroot|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-sftp-chroot]]**

### **Setup User/Group:**
* **[[Setup User|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-user]]**
* **[[Change User Shell|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#change-user-shell]]**
* **[[Setup Group|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-group]]**
* **[[Setup Permissions|https://github.com/rtCamp/easyengine/wiki/SFTP-chroot#setup-permission]]**

#### Setup User:
```bash
^_^[root@example.com:~]# adduser user
Adding user `user' ...
Adding new group `user' (1002) ...
Adding new user `user' (1002) with group `user' ...
Creating home directory `/home/user' ...
Copying files from `/etc/skel' ...
Enter new UNIX password: 
Retype new UNIX password: 
passwd: password updated successfully
Changing the user information for user
Enter the new value, or press ENTER for the default
	Full Name []: user
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] Y
```

#### Change User Shell
```bash
^_^[root@example.com:~]# chsh -s /usr/sbin/nologin user
```

#### **Setup Group:**
```bash
^_^[root@example.com:~]# usermod -G www-data user
^_^[root@example.com:~]# id user
uid=1002(user) gid=1002(user) groups=1002(user),33(www-data)
```

### **Setup Permission:**
```bash
^_^[root@example.com:~]# chown root:root /home/
^_^[root@example.com:~]# chown root:root /home/user

^_^[root@example.com:~]# chmod g+s /var/www/example.com/htdocs/wp-content/themes
^_^[root@example.com:~]# chmod 775 /var/www/example.com/htdocs/wp-content/themes
```

### Setup Chroot Directory:
```bash
^_^[root@example.com:~]# mkdir -p /home/user/themes
^_^[root@example.com:~]# mount --bind /var/www/example.com/htdocs/wp-content/themes /home/user/themes
```
**NOTE:** After system reboot, above mount point is removed, you have to add above command in your `/etc/rc.local` file.

#### Setup SFTP Chroot:
```bash
^_^[root@example.com:~]# vim /etc/ssh/sshd_config +/Subsystem
#Subsystem sftp /usr/lib/openssh/sftp-server
Subsystem sftp internal-sftp

# Appened following code at EOF
Match group user
X11Forwarding no
ChrootDirectory %h
AllowTcpForwarding no
ForceCommand internal-sftp
```
**Restart SSH Service**
```bash
^_^[root@example.com:~]# service ssh restart
ssh stop/waiting
ssh start/running, process 31242
```

