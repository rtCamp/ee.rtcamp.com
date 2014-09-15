# **EasyEngine (ee)**
## **Update**
### **How to update EasyEngine (ee)?**


To update the EasyEngine, please set following line in your `~/.bashrc`

```bash
alias eeupdate="wget -qO eeup http://rt.cx/eeup && sudo bash eeup"
```

Lets source the ~/.bashrc
```bash
source ~/.bashrc
```


Now Update EasyEngine using command:
```bash
eeupdate
```

***

Latest release of EasyEngine requires hostname as [FQDN](http://en.wikipedia.org/wiki/Fully_qualified_domain_name) . If not set then EasyEngine ask you to set hostname as FQDN.
 
 ```bash
 Enter hostname [FQDN]:example.com
 ```