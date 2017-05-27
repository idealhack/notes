# Ansible


## Overview

- https://www.ansible.com/


## Common Tasks

    vim /etc/ansible/hosts
    ansible intel -m ping
    ansible intel -m shell -a "date"
    ansible intel -m script -a "script.sh"
    ansible intel -m copy -a "src=file dest=file"
