# TLS


## Overview

- https://zh.wikipedia.org/wiki/%E5%82%B3%E8%BC%B8%E5%B1%A4%E5%AE%89%E5%85%A8%E5%8D%94%E8%AD%B0
- https://en.wikipedia.org/wiki/Transport_Layer_Security


## Let's Encrypt

- [Let's Encrypt](https://letsencrypt.org/)
- [Certbot](https://certbot.eff.org/)

Nginx on CentOS/RHEL 7

    yum -y install yum-utils
    yum-config-manager --enable rhui-REGION-rhel-server-extras rhui-REGION-rhel-server-optional
    yum install certbot-nginx
    certbot --nginx

Auto renew by crontab:

    15 0  * * * certbot renew --quiet
    45 12 * * * certbot renew --quiet

Manual get a certificate:

    certbot certonly -d example.com --manual


## HSTS

- https://zh.wikipedia.org/zh-hans/HTTP%E4%B8%A5%E6%A0%BC%E4%BC%A0%E8%BE%93%E5%AE%89%E5%85%A8
- https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security


## Tools

- https://www.ssllabs.com/ssltest/analyze.html
- https://mozilla.github.io/server-side-tls/ssl-config-generator/
- https://github.com/SteveLTN/https-portal


## Resources

- [google/nogotofail](https://github.com/google/nogotofail)
- [TLS 握手优化详解 | JerryQu 的小站](https://imququ.com/post/optimize-tls-handshake.html)
- [开始使用 ECC 证书 | JerryQu 的小站](https://imququ.com/post/ecc-certificate.html)
- [Let's Encrypt，免费好用的 HTTPS 证书 | JerryQu 的小站](https://imququ.com/post/letsencrypt-certificate.html)
- [Qualys SSL Labs](https://www.ssllabs.com/)
- [﻿Security with HTTPS and SSL | Android Developers](https://developer.android.com/training/articles/security-ssl.html)
- [HTTPS是如何工作的 - 众成翻译](http://www.zcfy.cc/article/how-does-https-work-1280.html)
- http://blog.m31271n.com/2017/03/17/SSL-TLS-%E6%A6%82%E8%A7%88/
- https://github.com/k8sp/tls
- https://weakdh.org/
