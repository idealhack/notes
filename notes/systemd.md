# systemd

## Overview

- [systemd](https://www.freedesktop.org/wiki/Software/systemd/)
- [systemd - 维基百科](https://zh.wikipedia.org/wiki/Systemd)

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

- [Systemd (简体中文) - ArchWiki](https://wiki.archlinux.org/index.php/systemd_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
- [Understanding and administering systemd :: Fedora Docs Site](https://docs.fedoraproject.org/en-US/quick-docs/understanding-and-administering-systemd/index.html)
- [systemd - Debian Wiki](https://wiki.debian.org/systemd)
- [Chapter 9. Managing Services with systemd - Red Hat Customer Portal](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/chap-managing_services_with_systemd)
- [How To Use Systemctl to Manage Systemd Services and Units | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units)
- [Systemd 入门教程：命令篇 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html)
- [Understanding and Using Systemd | Linux.com | The source for Linux information](https://www.linux.com/learn/understanding-and-using-systemd)
- [Integration of a Go service with systemd: readiness & liveness | Vincent Bernat](https://vincent.bernat.ch/en/blog/2017-systemd-golang)
- [Integration of a Go service with systemd: socket activation | Vincent Bernat](https://vincent.bernat.ch/en/blog/2018-systemd-golang-socket-activation)
