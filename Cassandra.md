# Cassandra


## Overview

- http://cassandra.apache.org/
- https://zh.wikipedia.org/wiki/Cassandra


## Installing

### Docker

https://hub.docker.com/_/cassandra/

    docker pull cassandra

### Kubernetes

https://console.cloud.google.com/gcr/images/google-samples/GLOBAL/cassandra

    docker pull gcr.io/google-samples/cassandra:v12


## Documentation

- http://cassandra.apache.org/doc/latest/getting_started/index.html
- http://docs.datastax.com/en/cassandra/latest/


## Drivers

- http://cassandra.apache.org/doc/latest/getting_started/drivers.html

### Go

- https://github.com/gocql/gocql
- https://academy.datastax.com/resources/getting-started-apache-cassandra-and-go

### C++

- https://academy.datastax.com/resources/getting-started-cpp-driver
- https://github.com/datastax/cpp-driver
- http://docs.datastax.com/en/developer/cpp-driver/2.6/

Installing on Ubuntu 14.04:

    wget http://ftp.br.debian.org/debian/pool/main/o/openssl1.0/libssl1.0.2_1.0.2k-1_amd64.deb
    wget http://downloads.datastax.com/cpp-driver/ubuntu/14.04/dependencies/libuv/v1.11.0/libuv_1.11.0-1_amd64.deb
    wget http://downloads.datastax.com/cpp-driver/ubuntu/14.04/cassandra/v2.6.0/cassandra-cpp-driver_2.6.0-1_amd64.deb

### PHP

- https://academy.datastax.com/resources/getting-started-apache-cassandra-and-php
- https://github.com/datastax/php-driver


## Books

- [学习Cassandra](http://teddymaef.github.io/learncassandra/cn/)


## Tools

- https://github.com/gianlucaborello/cassandradump
- https://www.ecyrd.com/cassandracalculator/


## Resources

- [DataStax Academy](https://academy.datastax.com/)
- [Cassandra选型介绍 at master · shahuwang/blogposts](https://github.com/shahuwang/blogposts/blob/master/Cassandra%E9%80%89%E5%9E%8B%E4%BB%8B%E7%BB%8D.md)
- [Cassandra数据模型设计最佳实践（上部）](http://www.infoq.com/cn/articles/best-practice-of-cassandra-data-model-design)
- [Cassandra数据模型设计最佳实践（下部）](http://www.infoq.com/cn/articles/best-practices-cassandra-data-model-design-part2)
- [Cassandra – 理解关键概念和数据模型 | Silent River](http://www.justinablog.com/archives/882)
- [Cassandra – 数据结构设计概念和原则 | Silent River](http://www.justinablog.com/archives/902)
- [Cassandra - FlyML](https://www.flyml.net/category/big-data/cassandra/)
- [Fulfilling the promise of Apache Cassandra performance - OpenCredo](https://opencredo.com/fulfilling-promise-apache-cassandra/)
- [Apache Cassandra for analytics: A performance and storage analysis - O'Reilly Media](https://www.oreilly.com/ideas/apache-cassandra-for-analytics-a-performance-and-storage-analysis)

