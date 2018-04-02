# TCP

## Overview

- [传输控制协议 - 维基百科](https://zh.wikipedia.org/wiki/%E4%BC%A0%E8%BE%93%E6%8E%A7%E5%88%B6%E5%8D%8F%E8%AE%AE)

## Commands

    netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'

## Resources

- [TCP 连接状态 | 鸟窝](http://colobu.com/2015/06/25/TCP-connection-status/)
- [TCP TIME-WAIT 笔记 - 概览](https://blog.tonyseek.com/post/tcp-tw-overview/)
- [Linux高并发系统参数优化](https://blog.icehoney.me/posts/2016-11-27-Linux-tune-guide)
- [Linux下Http高并发参数优化之TCP参数 | One Rain's Blog](https://kiswo.com/article/1017)
