---
title: sqlite
time: 2022-12-17 17:15:00
tab: 
---

sqlite
==

[toc]
- [sqlite](#sqlite)
- [1.安装](#1安装)
- [2.语法](#2语法)
  - [2.1.创建数据库](#21创建数据库)
  - [2.2.创建表](#22创建表)
  - [2.3.删除表](#23删除表)
  - [2.4.增加表内容](#24增加表内容)
  - [2.5.查表格内容](#25查表格内容)
  - [2.6.修改表内容](#26修改表内容)
  - [2.7.删除表格内容](#27删除表格内容)
  - [2.8.一些运算符](#28一些运算符)
  - [2.9.部分总结](#29部分总结)
- [3.第三方软件使用](#3第三方软件使用)



# 1.安装

官网：https://www.sqlite.org/

windows：

![image-20221217172157618](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221217172157618.png)

下载所需要的部分（第三个必下），解压后的文件放到想放的地方

![image-20221217172341064](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221217172341064.png)

再设置环境变量那里的Path项中加入你上述文件所存放的路径

![image-20221217172607603](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221217172607603.png)



# 2.语法

由于不会一直使用命令行的形式运用sqlite，故只记录些许命令

**注释**：两个连续的“-”开始注释直至行末

语句以关键字开始，以“;”结尾

| 存储类  | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| NULL    | 值是一个 NULL 值。                                           |
| INTEGER | 值是一个带符号的整数，根据值的大小存储在 1、2、3、4、6 或 8 字节中。 |
| REAL    | 值是一个浮点值，存储为 8 字节的 IEEE 浮点数字。              |
| TEXT    | 值是一个文本字符串，使用数据库编码（UTF-8、UTF-16BE 或 UTF-16LE）存储。 |
| BLOB    | 值是一个 blob 数据，完全根据它的输入存储。                   |



## 2.1.创建数据库

```sqlite
.open Databasename.db
```

可以用该命令创建新的数据库，如果该数据库存在，则直接打开，一个数据库即一个文件，不需要直接删除即可

![image-20230107143852125](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143852125.png)



## 2.2.创建表

```sqlite
CREATE TABLE database_name.table_name(
   column1 datatype  PRIMARY KEY(one or more columns),
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
);
```

如：

![image-20230107143539817](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143539817.png)

可以用".tables"来验证是否创建成功

![image-20230107143555281](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143555281.png)



## 2.3.删除表

```sqlite
DROP TABLE database_name.table_name;
```



## 2.4.增加表内容

```sqlite
INSERT INTO TABLE_NAME [(column1, column2, column3,...columnN)]  
VALUES (value1, value2, value3,...valueN);
```

如果全部要添加，那么就可以不写列名

![image-20230107143449947](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143449947.png)



## 2.5.查表格内容

```sqlite
SELECT column1, column2, columnN FROM table_name; --查询该表中指定列内容
SELECT * FROM table_name; --查询整个表
SELECT * FROM table_name WHERE [condition]; --根据需要添加条件查询表格内容

SELECT column1, column2, columnN FROM table_name WHERE [condition1] AND [condition2]...AND [conditionN];
SELECT column1, column2, columnN FROM table_nameWHERE [condition1] OR [condition2]...OR [conditionN]
--用 OR 与 AND 可以连接多个条件，实现复杂的查询
```

如：

![image-20230107143612110](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143612110.png)



## 2.6.修改表内容

```sqlite
UPDATE table_name
SET column1 = value1, column2 = value2...., columnN = valueN
WHERE [condition];
--可以使用 AND 或 OR 运算符来结合多个数量的条件
```

如：

![image-20230107143659225](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143659225.png)



## 2.7.删除表格内容

```sqlite
DELETE FROM table_name WHERE [condition];
```

如：

![image-20230107143727786](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107143727786.png)



## 2.8.一些运算符

数值计算：

| 运算符 | 描述                                    | 实例              |
| :----- | :-------------------------------------- | :---------------- |
| +      | 加法 - 把运算符两边的值相加             | a + b 将得到 30   |
| -      | 减法 - 左操作数减去右操作数             | a - b 将得到 -10  |
| *      | 乘法 - 把运算符两边的值相乘             | a * b 将得到 200  |
| /      | 除法 - 左操作数除以右操作数             | b / a 将得到 2    |
| %      | 取模 - 左操作数除以右操作数后得到的余数 | b % a will give 0 |



逻辑运算符：

| 运算符 | 描述                                                         | 实例              |
| :----- | :----------------------------------------------------------- | :---------------- |
| ==     | 检查两个操作数的值是否相等，如果相等则条件为真。             | (a == b) 不为真。 |
| =      | 检查两个操作数的值是否相等，如果相等则条件为真。             | (a = b) 不为真。  |
| !=     | 检查两个操作数的值是否相等，如果不相等则条件为真。           | (a != b) 为真。   |
| <>     | 检查两个操作数的值是否相等，如果不相等则条件为真。           | (a <> b) 为真。   |
| >      | 检查左操作数的值是否大于右操作数的值，如果是则条件为真。     | (a > b) 不为真。  |
| <      | 检查左操作数的值是否小于右操作数的值，如果是则条件为真。     | (a < b) 为真。    |
| >=     | 检查左操作数的值是否大于等于右操作数的值，如果是则条件为真。 | (a >= b) 不为真。 |
| <=     | 检查左操作数的值是否小于等于右操作数的值，如果是则条件为真。 | (a <= b) 为真。   |
| !<     | 检查左操作数的值是否不小于右操作数的值，如果是则条件为真。   | (a !< b) 为假。   |
| !>     | 检查左操作数的值是否不大于右操作数的值，如果是则条件为真。   | (a !> b) 为真。   |



## 2.9.部分总结

对表格的增删改查语句各类数据库基本一致，一般称作sql语句，所以在以后学习其它数据库也会有一定帮助

其它语法详见：[SQLite 教程 | 菜鸟教程 (runoob.com)](https://www.runoob.com/sqlite/sqlite-tutorial.html)



# 3.第三方软件使用

在vscode中使用插件对sqlite数据库进行访问

![image-20230107201446766](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20230107201446766.png)

