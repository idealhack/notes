# Cassandra


## Overview

- http://cassandra.apache.org/
- https://en.wikipedia.org/wiki/Apache_Cassandra
- https://zh.wikipedia.org/wiki/Cassandra


## Installing

### Docker

https://hub.docker.com/_/cassandra/

    docker pull cassandra

### Ubuntu 14.04:

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java8-set-default
    java -version
    echo "deb http://www.apache.org/dist/cassandra/debian 310x main" | sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list
    curl https://www.apache.org/dist/cassandra/KEYS | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install cassandra


## Documentation

- http://cassandra.apache.org/doc/latest/getting_started/index.html
- http://docs.datastax.com/en/cassandra/latest/


## Drivers

- http://cassandra.apache.org/doc/latest/getting_started/drivers.html

### Go

- https://github.com/gocql/gocql

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


## Tools

- https://github.com/gianlucaborello/cassandradump


## Resources

- [Cassandra选型介绍 at master · shahuwang/blogposts](https://github.com/shahuwang/blogposts/blob/master/Cassandra%E9%80%89%E5%9E%8B%E4%BB%8B%E7%BB%8D.md)
- [学习Cassandra](http://teddymaef.github.io/learncassandra/cn/)
- http://clusterhq.com/2016/03/09/fun-with-swarm-part1/
