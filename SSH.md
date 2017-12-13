# SSH

## Client config

[ssh_config(5) Mac OS X Manual Page](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man5/ssh_config.5.html)

## Tasks

### Debugging

    sshd -ddd
    ssh user@host -vvv

### Use RSA key authentication

    ssh-keygen -t rsa
    ssh-copy-id user@host

### Disable password login

    vim /etc/ssh/sshd_config
    systemctl reload sshd

### Show fignerprint

    ssh-keygen -E md5 -lf ~/.ssh/id_rsa.pub

## Tools

- https://github.com/emre/storm
- http://fitztrev.github.io/shuttle/
- http://liftoffsoftware.com/Products/GateOne

## Issues

### Disable DNS in case of slow login

    vim /etc/ssh/sshd_config
    UseDNS no

### Ubuntu encrypted home directory

Put `authorized_keys` out of `home` https://help.ubuntu.com/community/SSH/OpenSSH/Keys#Troubleshooting
