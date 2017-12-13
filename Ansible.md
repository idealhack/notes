# Ansible

## Overview

- https://www.ansible.com/

## Tasks

    vim /etc/ansible/hosts
    ansible <host-pattern> -m ping
    ansible <host-pattern> -m shell -a "date"
    ansible <host-pattern> -m script -a "script.sh"
    ansible <host-pattern> -m copy -a "src=file dest=file"

## Books

- http://ansible-tran.readthedocs.io/en/latest/index.html
