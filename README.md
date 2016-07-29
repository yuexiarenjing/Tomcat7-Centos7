# Tomcat7-Centos7

Tomcat7
```
http://tomcat.apache.org/download-70.cgi
```

Download
```
cd /usr/local
wget  tomcat_url
tar -zxv -f apache-tomcat-7.0.29.tar.gz
rm -rf apache-tomcat-7.0.29.tar.gz
mv apache-tomcat-7.0.29 tomcat 
```

Startup
```
/usr/local/tomcat/bin/startup.sh
```

Config firewall to allow 8080 port
```
firewall-cmd --zone=public --add-port=8080/tcp --permanent
firewall-cmd --reload
```

shell Script for reboot configuration
```
#!/bin/bash
# Program:
#       Startup tomcat7 and config firewall to allow 8080/tcp.
# History:
# 2016/07/29    ZhangWei        First release
PATH=/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:~/bin
export PATH

firewall-cmd --zone=public --add-port=8080/tcp --permanent
firewall-cmd --reload

/usr/local/tomcat/bin/startup.sh
```
