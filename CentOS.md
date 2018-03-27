# CentOS

## Overview

- [CentOS Project](https://www.centos.org/)
- [CentOS - 维基百科](https://zh.wikipedia.org/wiki/CentOS)

## Setup

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

## RHEL

- [RHEL7 RHCSA Exam objectives - CertDepot](https://www.certdepot.net/rhel7-rhcsa-exam-objectives/)
- [RHEL7 RHCE Exam objectives - CertDepot](https://www.certdepot.net/rhel7-rhce-exam-objectives/)
