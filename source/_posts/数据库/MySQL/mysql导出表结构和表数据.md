---
title: "mysql导出表结构和表数据"
date: 2021-03-24T19:36:38+08:00
draft: true
---

命令行下具体用法如下：  

```
mysqldump -u用戶名 -p密码 -d 数据库名 表名 > 脚本名;
```

导出整个数据库结构和数据

```sql
mysqldump -h localhost -uroot -p123456 database > dump.sql
```

导出单个数据表结构和数据

```sql
mysqldump -h localhost -uroot -p123456  database table > dump.sql
```

导出整个数据库结构（不包含数据）

```sql
mysqldump -h localhost -uroot -p123456  -d database > dump.sql
```

导出单个数据表结构（不包含数据）

```sql
mysqldump -h localhost -uroot -p123456  -d database table > dump.sql
```