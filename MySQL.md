# MySQL


## Docs

- https://dev.mysql.com/doc/refman/5.7/en/


## Commands

### MySQL 查询状态

    mysql> show processlist;

各状态含义

- https://dev.mysql.com/doc/refman/5.5/en/general-thread-states.html
- http://imysql.com/2015/06/10/mysql-faq-processlist-thread-states.shtml


### 备份 master 数据库

https://dev.mysql.com/doc/refman/5.7/en/replication-solutions-backups-read-only.html

    mysql -uroot -ppassword --database=database -e "FLUSH TABLES WITH READ LOCK; SET GLOBAL read_only = ON;"
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-beforedump.txt
    mysqldump -uroot -ppassword database | gzip > database.sql.gz
    mysql -uroot -ppassword --database=database -e "show master status\G" > master-status-afterdump.txt
    mysql -uroot -ppassword --database=database -e "SET GLOBAL read_only = OFF; UNLOCK TABLES;"


## Resources

[21分钟MySQL基础入门 - 埋名 - SegmentFault](https://segmentfault.com/a/1190000006876419)
[MYCAT官方网站-中国第一开源分布式数据库中间件](http://mycat.io/)
