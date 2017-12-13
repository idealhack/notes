# MySQL

## Docs

- https://dev.mysql.com/doc/refman/5.7/en/

## Commands

### MySQL 查询状态

    mysql> show processlist;

各状态含义

- https://dev.mysql.com/doc/refman/5.5/en/general-thread-states.html
- http://imysql.com/2015/06/10/mysql-faq-processlist-thread-states.shtml

### 配置访问权限

    GRANT ALL PRIVILEGES ON *.* TO 'user'@'ip' IDENTIFIED BY 'password' WITH GRANT OPTION;
    flush privileges;
    use mysql;
    SELECT user, host, password FROM user where host = 'ip';
    delete from user where user = 'user';
    flush privileges;

### 备份 master 数据库

https://dev.mysql.com/doc/refman/5.7/en/replication-solutions-backups-read-only.html

    mysql -uroot -ppassword --database=database -e "FLUSH TABLES WITH READ LOCK; SET GLOBAL read_only = ON;"
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-beforedump.txt
    mysqldump -uroot -ppassword database | gzip > database.sql.gz
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-afterdump.txt
    mysql -uroot -ppassword --database=database -e "SET GLOBAL read_only = OFF; UNLOCK TABLES;"

### 查询包含时间戳的字段

https://stackoverflow.com/questions/9251561/convert-timestamp-to-date-in-mysql-query

## Cluster

- [Vitess](http://vitess.io)
- [MYCAT](http://mycat.io/)

## Resources

- [21分钟MySQL基础入门 - 埋名 - SegmentFault](https://segmentfault.com/a/1190000006876419)
- http://www.xbitworld.com/?p=919
- https://segmentfault.com/q/1010000010173985
- [我必须得告诉大家的MySQL优化原理 - 简书](http://www.jianshu.com/p/d7665192aaaf)
- [项目中常用的19条MySQL优化 - 个人文章 - SegmentFault](https://segmentfault.com/a/1190000012155267)
