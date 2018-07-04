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

#### 2、遇到问题

`Host 'xxx' is not allowed to connect to this MySQL server`

**解决方案**

* 登录mysql： `mysql -uroot -ppwd`
* 查看user表： `use mysql`
* `select host,user,password from user;`
* `update user set host = '%' where user = 'root';`
* 更新： `FLUSH PRIVILEGES;`