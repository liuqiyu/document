# 阿里云服务器安装Mysql

##### 1、MYSQL安装

```json
rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm

yum -y install mysql-community-server

systemctl enable mysqld

systemctl start mysqld


mysql_secure_installation

```

![](/assets/1138059-20170614201554493-1071737203.png)