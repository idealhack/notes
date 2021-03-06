# Linux Configuration

## Wireless Network

查询无线网卡名

    ifconfig -a
    ip a
    sudo lshw -C network

配置无线网络

    vim /etc/network/interfaces

    auto wlan0
    iface wlan0 inet dhcp
    wpa-ssid <your_router>
    wpa-psk <your_wpa_key>

    sudo ifup -v wlan0

## Wake-on-LAN

    ethtool eth0
    ethtool -s eth0 wol g
    ether-wake -i eth0 00:30:67:6d:3d:7c
    echo 'ETHTOOL_OPTS="wol g"' > /etc/sysconfig/network-scripts/ifcfg-eth0

## Resources

- [Linux TCP/IP 协议栈调优](http://colobu.com/2014/09/18/linux-tcpip-tuning/)
- [The Netflix Tech Blog: Linux Performance Analysis in 60,000 Milliseconds](http://techblog.netflix.com/2015/11/linux-performance-analysis-in-60s.html)
- [全新CentOS 7安装 LNMP（Linux+Nginx+MariaDB+PHP）及多站点配置](https://www.ifshow.com/the-new-centos-7-install-lnmp-linux-nginx-mariadb-php-and-multi-site-configuration/)
- [美团云知识库|在CentOS 7上搭建LNMP环境 | 美团云](https://mos.meituan.com/library/18/how-to-install-lnmp-on-centos7/)
- [当我们 chmod 777 的时候，到底干了些什么？ - Learning Every Day - SegmentFault](https://segmentfault.com/a/1190000006246645)
