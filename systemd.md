# systemd

## Overview

- https://www.freedesktop.org/wiki/Software/systemd/
- https://zh.wikipedia.org/wiki/Systemd

## Commands

    systemctl list-units

    systemctl enable service-name.service
    systemctl disable service-name.service
    systemctl start service-name.service
    systemctl stop service-name.service
    systemctl restart service-name.service
    systemctl status service-name.service

    journalctl -u service-name.service

## Resources

- https://wiki.archlinux.org/index.php/systemd_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)
- https://fedoraproject.org/wiki/Systemd
- https://wiki.debian.org/systemd
- https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/chap-Managing_Services_with_systemd.html
- https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units
- http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html
