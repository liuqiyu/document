# 阿里云服务器安装Mysql

##### 1、MYSQL安装

```json
安装rpm包
rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm

安装mysql
yum -y install mysql-community-server

加入开机启动
systemctl enable mysqld

启动MySQL服务进程
systemctl start mysqld

配置root用户密码
mysql_secure_installation

```
![](/assets/1138059-20170614201554493-1071737203.png)

```json
开启一个新的shell窗口，链接数据库
mysql -u root -p
```