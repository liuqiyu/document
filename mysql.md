<img src="/assets/mysql.png" width="300" hegiht="100" align=center />


## 前言

MYSQL是最流行的关系型数据库管理系统。

## 目录

* [基本入门](#base)
 * [连接MYSQL](#connect)
 * [查看、选择、创建、删除数据库](#operationDatabase)
 * [mysql数据类型](#datatype)
 * [数据表操作](#operationTables)
 * [数据操作](#operationData)
  * [插入数据](#insertData)
  * [查询数据](#selectData)
 
<a name="base"></a>
## 基本入门

<a name="connect"></a>
#### 连接MYSQL

我们先连接mysql服务器：

```json
mysql -u root -p
Enter password: *****
```

<a name="operationDatabase"></a>
#### 查看、选择、创建、删除数据库

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

* 选择数据库

```json
mysql> use mysql;

Database changed
```

* 创建数据库

```json
mysql> create database test;

Query OK, 1 row affected (0.00 sec)
```

* 删除数据库

```json
mysql> drop database test;

Query OK, 0 rows affected (0.00 sec)
```

<a name="datatype"></a>
#### MYSQL 数据类型

MySql支持多种类型，大致可以分为三类： 数值、日期/时间和字符串类型。

<a name="operationTables"></a>
#### 数据表操作

<a name="createTable"></a>
* 创建数据库

```json
mysql> CREATE TABLE IF NOT EXISTS `runoob_tbl`(
   `runoob_id` INT UNSIGNED AUTO_INCREMENT,
   `runoob_title` VARCHAR(100) NOT NULL,
   `runoob_author` VARCHAR(40) NOT NULL,
   `submission_date` DATE,
   PRIMARY KEY ( `runoob_id` )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

* 删除数据库

```json
mysql> DROP TABLE runoob_tbl;
```

<a name="operationData"></a>
#### 数据操作

<a name="insertData"></a>
* 插入数据

```json
insert into arms (name, img_src, type_id, descript, remarks) values ('碎 片手雷', 'www', 8, '手雷手雷', '哈哈，炸死你');

Query OK, 1 row affected (0.00 sec)
```

<a name="selectData"></a>
* 查询数据

```json
select * from arms;
```




