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

- [emre/storm: Manage your SSH like a boss.](https://github.com/emre/storm)
- [Shuttle | A simple SSH shortcut menu for OS X](http://fitztrev.github.io/shuttle/)
- [Gate One ✈ Web Terminal Emulator and SSH Client | Liftoff Software](http://liftoffsoftware.com/Products/GateOne)

## Issues

### Disable DNS in case of slow login

    vim /etc/ssh/sshd_config
    UseDNS no

### Ubuntu encrypted home directory

Put `authorized_keys` out of `home` [SSH/OpenSSH/Keys - Community Help Wiki](https://help.ubuntu.com/community/SSH/OpenSSH/Keys#Troubleshooting)
