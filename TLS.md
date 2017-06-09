# TLS


## Overview

- https://zh.wikipedia.org/wiki/%E5%82%B3%E8%BC%B8%E5%B1%A4%E5%AE%89%E5%85%A8%E5%8D%94%E8%AD%B0
- https://en.wikipedia.org/wiki/Transport_Layer_Security


## Let's Encrypt

- [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
- [certbot/certbot](https://github.com/certbot/certbot)
- [Let's Encrypt，免费好用的 HTTPS 证书 | JerryQu 的小站](https://imququ.com/post/letsencrypt-certificate.html)

Manual get a certificate:

    certbot certonly -d example.com --manual

Auto renew by crontab:

    15 0  * * * certbot renew --quiet
    45 12 * * * certbot renew --quiet


## Resources

- [google/nogotofail](https://github.com/google/nogotofail)
- [TLS 握手优化详解 | JerryQu 的小站](https://imququ.com/post/optimize-tls-handshake.html)
- [开始使用 ECC 证书 | JerryQu 的小站](https://imququ.com/post/ecc-certificate.html)
- [Qualys SSL Labs](https://www.ssllabs.com/)
- [﻿Security with HTTPS and SSL | Android Developers](https://developer.android.com/training/articles/security-ssl.html)
- [HTTPS是如何工作的 - 众成翻译](http://www.zcfy.cc/article/how-does-https-work-1280.html)
- http://blog.m31271n.com/2017/03/17/SSL-TLS-%E6%A6%82%E8%A7%88/
- https://github.com/k8sp/tls
