# Ansible

## Overview

- [Ansible is Simple IT Automation](https://www.ansible.com/)

## Tasks

    vim /etc/ansible/hosts
    ansible <host-pattern> -m ping
    ansible <host-pattern> -m shell -a "date"
    ansible <host-pattern> -m script -a "script.sh"
    ansible <host-pattern> -m copy -a "src=file dest=file"

## Books

- [Ansible中文权威指南 — 国内最专业的Ansible中文官方学习手册](http://ansible-tran.readthedocs.io/en/latest/index.html)
