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

## Resources

- [jdauphant/awesome-ansible: A collaborative curated list of awesome Ansible resources](https://github.com/jdauphant/awesome-ansible)
- [awesome-devops/awesome-ansible: Awesome Ansible List](https://github.com/awesome-devops/awesome-ansible)
