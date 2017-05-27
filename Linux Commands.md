# Linux Commands


## Commands

    top
    passwd
    df
    du
    tmux
    git

### Files

Count files recursively

    find . -type f | wc -l

### Processes

查看进程以及占用端口

    ps aux | grep $process
    netstat -tulpn | grep $port
    pwdx $pid
    which $process

ps 排序 http://alvinalexander.com/linux/unix-linux-process-memory-sort-ps-command-cpu


### Hardware information

CPU 

    cat /proc/cpuinfo

Memory : 

    free -h
    cat /proc/meminfo

HDD:

    df -h
    sudo fdisk -l
    hdparm -i /dev/device (for example sda1, hda3...)


- https://github.com/smxi/inxi


## Resources

- https://i.linuxtoy.org/files/pdf/fwunixref.pdf
- https://www.tecmint.com/commands-to-collect-system-and-hardware-information-in-linux/
- https://www.cyberciti.biz/faq/linux-command-to-find-the-system-configuration-and-hardware-information/
- http://www.binarytides.com/linux-commands-hardware-info/
- https://www.maketecheasier.com/check-hardware-information-linux/
- http://www.thegeekstuff.com/2008/11/how-to-get-hardware-information-on-linux-using-dmidecode-command/
- [mv操作深入浅出 - 百度技术博客 - 51CTO技术博客](http://baidutech.blog.51cto.com/4114344/743731)
