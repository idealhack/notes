# Public key infrastructure

## Overview

- [公開金鑰基礎建設 - 维基百科](https://zh.wikipedia.org/wiki/%E5%85%AC%E9%96%8B%E9%87%91%E9%91%B0%E5%9F%BA%E7%A4%8E%E5%BB%BA%E8%A8%AD)

### Public-key cryptography

- [公开密钥加密 - 维基百科](https://zh.wikipedia.org/wiki/%E5%85%AC%E5%BC%80%E5%AF%86%E9%92%A5%E5%8A%A0%E5%AF%86)

### Public key certificate

- [公開金鑰認證 - 维基百科](https://zh.wikipedia.org/wiki/%E5%85%AC%E9%96%8B%E9%87%91%E9%91%B0%E8%AA%8D%E8%AD%89)

### Digital signature

- [數位簽章 - 维基百科](https://zh.wikipedia.org/wiki/%E6%95%B8%E4%BD%8D%E7%B0%BD%E7%AB%A0)

### X.509

- [X.509 - 维基百科](https://zh.wikipedia.org/wiki/X.509)

### Certificate authority

- [数字证书认证机构 - 维基百科](https://zh.wikipedia.org/wiki/%E6%95%B0%E5%AD%97%E8%AF%81%E4%B9%A6%E8%AE%A4%E8%AF%81%E6%9C%BA%E6%9E%84)

## Tools

- [cloudflare/cfssl: CFSSL: Cloudflare's PKI and TLS toolkit](https://github.com/cloudflare/cfssl)

## Tasks

### Displaying a remote SSL certificate details

    echo | openssl s_client -showcerts -servername gnupg.org -connect gnupg.org:443 2>/dev/null | openssl x509 -inform pem -noout -text

## Resources

- [自建 CA 的那些事儿 | 自言自语](http://blog.m31271n.com/2017/03/17/%E8%87%AA%E5%BB%BA-CA-%E7%9A%84%E9%82%A3%E4%BA%9B%E4%BA%8B%E5%84%BF/)
- [基于OpenSSL自建CA和颁发SSL证书 | Sean's Notes](http://seanlook.com/2015/01/18/openssl-self-sign-ca/)
- [自建 CA 和 PKI 相关内容 | 自说自话](http://www.scalaone.com/?p=309)

### Certificate Pinning

- [Certificate and Public Key Pinning | OWASP Foundation](https://owasp.org/www-community/controls/Certificate_and_Public_Key_Pinning)
- [Certificate pinning for Android and iOS: Man-in-the-middle attack prevention | NowSecure Blog](https://www.nowsecure.com/blog/2017/06/15/certificate-pinning-for-android-and-ios-mobile-man-in-the-middle-attack-prevention/)
- [Bypassing OpenSSL Certificate Pinning in iOS Apps](https://www.nccgroup.trust/us/about-us/newsroom-and-events/blog/2015/january/bypassing-openssl-certificate-pinning-in-ios-apps/)
- [iphone - How to pin the Public key of a certificate on iOS - Stack Overflow](https://stackoverflow.com/questions/15728636/how-to-pin-the-public-key-of-a-certificate-on-ios?answertab=votes)
