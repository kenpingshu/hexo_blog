---
title: "mysql-Can't create/write to file (Errcode: 13 - Permission denied)"
date: 2018-02-01 16:43:02
tags: Mysql
categories: Mysql
---
今天在執行 Mysql 
```sql
SELECT * FROM `a` INTO OUTFILE '/var/www/html/a.csv';
```
出現以下錯誤
```
Can't create/write to file '/var/www/html/a.csv' (Errcode: 13 - Permission denied)
```
把資料夾權限全部改成777都沒用  
後來發現需要改動以下檔案
```sh
sudo vim /etc/apparmor.d/usr.sbin.mysqld
```
在文件裡面多加一行
```
/var/www/html/** rwk,
```
這樣才能讓mysql有權限寫檔進去