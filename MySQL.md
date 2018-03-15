# MySQL

## Docs

- [MySQL :: MySQL 5.7 Reference Manual](https://dev.mysql.com/doc/refman/5.7/en/)

## Commands

### MySQL 查询状态

    mysql> show processlist;

各状态含义

- [MySQL :: MySQL 5.5 Reference Manual :: 8.14.2 General Thread States](https://dev.mysql.com/doc/refman/5.5/en/general-thread-states.html)
- [[MySQL FAQ]系列 — processlist中哪些状态要引起关注 | iMySQL | 老叶茶馆](http://imysql.com/2015/06/10/mysql-faq-processlist-thread-states.shtml)

### 配置访问权限

    GRANT ALL PRIVILEGES ON *.* TO 'user'@'ip' IDENTIFIED BY 'password' WITH GRANT OPTION;
    flush privileges;
    use mysql;
    SELECT user, host, password FROM user where host = 'ip';
    delete from user where user = 'user';
    flush privileges;

### 备份 master 数据库

[MySQL :: MySQL 5.7 Reference Manual :: 16.3.1.3 Backing Up a Master or Slave by Making It Read Only](https://dev.mysql.com/doc/refman/5.7/en/replication-solutions-backups-read-only.html)

    mysql -uroot -ppassword --database=database -e "FLUSH TABLES WITH READ LOCK; SET GLOBAL read_only = ON;"
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-beforedump.txt
    mysqldump -uroot -ppassword database | gzip > database.sql.gz
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-afterdump.txt
    mysql -uroot -ppassword --database=database -e "SET GLOBAL read_only = OFF; UNLOCK TABLES;"

### 查询包含时间戳的字段

[sql - Convert timestamp to date in MySQL query - Stack Overflow](https://stackoverflow.com/questions/9251561/convert-timestamp-to-date-in-mysql-query)

## Cluster

- [Vitess](http://vitess.io)
- [MYCAT](http://mycat.io/)

## Resources

- [21分钟MySQL基础入门 - 埋名 - SegmentFault](https://segmentfault.com/a/1190000006876419)
- [将MySQL数据文件和临时文件移动到SSD以加速数据库访问](http://www.xbitworld.com/?p=919)
- [php - 一次插入几万条数据应该怎么做优化 - SegmentFault](https://segmentfault.com/q/1010000010173985)
- [我必须得告诉大家的MySQL优化原理 - 简书](http://www.jianshu.com/p/d7665192aaaf)
- [项目中常用的19条MySQL优化 - 个人文章 - SegmentFault](https://segmentfault.com/a/1190000012155267)
- [纲举目张：打通MySQL架构和业务的任督二脉](https://mp.weixin.qq.com/s/wS6bRSAPplhK6tRO3pb5xg)
