# macOS Commands


## Commands

文件列表显示完整时间

    ls -T -l

时间戳转为时间

    date -r $1483200000

时间转为时间戳

    date -j -f "%b %d %T %Z %Y" "Feb 1 00:00:00 CST 2017" "+%s"


## Resources

- [Rosetta Stone for Unix](http://bhami.com/rosetta.html)
- [UNIX 系统上的文本操作简介](http://www.ibm.com/developerworks/cn/aix/library/au-unixtext/index.html)
