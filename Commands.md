# Commands


[Rosetta Stone for Unix](http://bhami.com/rosetta.html)


## Commands

    top
    passwd
    df
    du
    tmux
    git


### Linux

查看进程以及占用端口

    ps aux | grep $process
    netstat -tulpn | grep $port
    pwdx $pid
    which $process

ps 排序 http://alvinalexander.com/linux/unix-linux-process-memory-sort-ps-command-cpu


### macOS

时间戳转为时间

    date -r $1483200000

时间转为时间戳

    date -j -f "%b %d %T %Z %Y" "Feb 1 00:00:00 CST 2017" "+%s"


## Resources

- [UNIX 系统上的文本操作简介](http://www.ibm.com/developerworks/cn/aix/library/au-unixtext/index.html)
- [mv操作深入浅出 - 百度技术博客 - 51CTO技术博客](http://baidutech.blog.51cto.com/4114344/743731)
