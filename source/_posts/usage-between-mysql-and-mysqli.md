---
title: usage-between-mysql-and-mysqli
date: 2019-04-27 15:13:54
tags:
---

#### 创建数据库连接：
##### Mysqli用法：
```php
$conn = new mysqli($servername, $username, $password, $dbname);
if ($conn->connect_error) {
    die('Connect Error: ' . $mysqli->connect_error);
}
$conn->close();
```
##### Mysql用法：
```php
$conn=mysql_connect($servername, $username, $password);
mysql_select_db($dbname);
mysql_error();
mysql_close($conn);
```
#### 数据库查询：
##### Mysqli用法：
```php
//执行$sql查询
$result=$conn->query($sql);
//取出记录集中当前指针位置数据
$row=$result->fetch_array();
```
##### Mysql用法：
```php
//先选择数据库
mysql_select_db($dbname);
//执行$sql查询
$result=mysql_query($sql, $conn);
//取出记录集中当前指针位置数据
$row=mysql_fetch_array($result,MYSQL_ASSOC);
```