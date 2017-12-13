# TCP

## Overview

- [传输控制协议 - 维基百科](https://zh.wikipedia.org/wiki/%E4%BC%A0%E8%BE%93%E6%8E%A7%E5%88%B6%E5%8D%8F%E8%AE%AE)

## Commands

    netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'

## Resources

- [TCP 连接状态 | 鸟窝](http://colobu.com/2015/06/25/TCP-connection-status/)
- [优化Linux的内核参数来提高服务器并发处理能力](http://www.ha97.com/4396.html)
