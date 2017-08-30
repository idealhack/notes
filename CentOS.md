# CentOS


## Overview

- https://www.centos.org/
- https://zh.wikipedia.org/wiki/CentOS


## Setup

使用 `CentOS-7-x86_64-Minimal-1611.iso` 安装后的配置流程如下

### Update system

    sudo yum update -y

### Install missing softwares

    sudo yum install -y ifconfig vim tmux

### Configure hostname

    sudo vim /etc/hosts
    sudo vim /etc/hostname
    sudo hostname hostname

### Configure SSH server

[[SSH]]

### EPEL Repo

    sudo yum install epel-release

### Remi Repo

    wget http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
    sudo rpm -Uvh remi-release-7*.rpm

### Disable kernel update

    echo $'\n'"exclude=kernel*" >> /etc/yum.conf

### CPU benchmark

    sudo yum install sysbench lm_sensors
