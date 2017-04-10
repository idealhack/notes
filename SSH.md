# SSH


## Common Tasks

### 调试方法

    sshd -ddd
    ssh user@host -vvv


### 使用 RSA key 认证

    ssh-keygen -t rsa
    ssh-copy-id user@host


### 禁用密码登录

    vim /etc/ssh/sshd_config
    systemctl reload sshd


## Tools

- https://github.com/emre/storm


## Issues

### 禁用 DNS 以免登录缓慢

    vim /etc/ssh/sshd_config
    UseDNS no

### 解决 Ubuntu home 目录加密问题

`authorized_keys` 放在 home 目录外 https://help.ubuntu.com/community/SSH/OpenSSH/Keys#Troubleshooting
