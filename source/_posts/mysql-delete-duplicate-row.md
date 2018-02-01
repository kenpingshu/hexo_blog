---
title: mysql 刪除重複的資料
date: 2017-08-16 15:02:52
tags: Mysql
categories: Mysql
---
```mysql
DELETE t1 FROM `A` as t1, `A` as t2
WHERE `t1`.`id` > `t2`.`id`
AND `t1`.`first_name` = `t2`.`first_name`
AND `t1`.`last_name` = `t2`.`last_name`
AND `t1`.`age` = `t2`.`age`
AND `t1`.`state` = `t2`.`state`
AND `t1`.`city` = `t2`.`city`
AND `t1`.`zip` = `t2`.`zip`
```

