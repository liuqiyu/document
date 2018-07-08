<img src="/assets/mysql.png" width="300" hegiht="100" align=center />


## 前言

MYSQL是最流行的关系型数据库管理系统。

## 目录

* [基本入门](#base)
 * [连接MYSQL](#connect)


<a name="base"></a>
## 基本入门

<a name="connect"></a>
### 连接MYSQL

我们先连接mysql服务器：

```json
mysql -u root -p
Enter password: *****
```

### 查看、创建删除数据库

* 查看数据库

```json
mysql> show databases;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| test               |
+--------------------+
4 rows in set (0.00 sec)
```

* 创建数据库

```json
mysql> create database test;

Query OK, 1 row affected (0.00 sec)

```



