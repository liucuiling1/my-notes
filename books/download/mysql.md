#### 一、mysql安装

登录：mysql -u root -p   
密码：123456

(1) show databases;查看库   
(2) use mysql;切换到所使用的库   
(3) show tables;查看库中所含有的表   
(4) create database auth;创建auth库   
(5) use auth;切换到auth库   

删除   
（1）drop table auth;删除auth库  
（2）drop table auth.users;删除auth库中users表   

创建表：    
（1）创建tb_users表格
```
  mysql> create table tb_users (
    -> name varchar(20),
    -> age int ,
    -> passworld varchar(32) comment'密码是32位',
    -> birthday date comment '生日 日期类');
```
修改：    
在表t1的name列后添加一列为图片路径：
alter table t1 add pic_url varchar(100) comment '图片路径' after name;   

删除：     
alter table t1 drop sno;

#### 二、mysql语法

SQL： DML 和 DDL

1、查询和更新指令构成了 SQL 的 DML 部分

* select - 从数据库表中获取数据
* update - 更新数据库表中的数据
* delete - 从数据库表中删除数据
* insert into - 向数据库表中插入数据

2、SQL 中最重要的 DDL 语句:

* create database - 创建新数据库
* alter database  - 修改数据库
* create table - 创建新表
* alter table  - 变更（改变）数据库表
* drop table - 删除表
* create index - 创建索引（搜索键）
* drop index- 删除索引

3、select
```
select * from userInfo  ---获取userInfo表数据
```

4、distinct 
```
SELECT DISTINCT Company FROM Orders   ---如需从 Company" 列中仅选取唯一不同的值
```

5、where
```
SELECT 列名称 FROM 表名称 WHERE 列 运算符 值 （如果是数值，请不要使用引号)
SELECT * FROM Persons WHERE City=‘Beijing’ ---选取居住在城市 "Beijing" 中的人
```

6：and
```
SELECT * FROM Persons WHERE FirstName='Thomas' AND LastName=‘Carter’
```

7、or
```
SELECT * FROM Persons WHERE firstname='Thomas' OR lastname='Carter'
```

8、and ，or 结合
```
SELECT * FROM Persons WHERE (FirstName='Thomas' OR FirstName='William’) AND LastName='Carter'
```

9、排序：order by
```
SELECT Company, OrderNumber FROM Orders ORDER BY Company
```

10、插入：insert
```
INSERT INTO 表名称 VALUES (值1, 值2,….)
INSERT INTO table_name (列1, 列2,...) VALUES (值1, 值2,….)
```

11、修改: update
```
UPDATE 表名称 SET 列名称 = 新值 WHERE 列名称 = 某值
```

12、删除: delete
```
DELETE FROM 表名称 WHERE 列名称 = 值
```

13、数据库muysql出现？？？时；
```
 ALTER TABLE `表名` CHANGE `列名` `列名` VARCHAR(45) CHARACTER SET UTF8 NOT NULL;
```

