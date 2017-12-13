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

ps 排序 [Linux process memory usage: How to sort ‘ps’ command output | alvinalexander.com](http://alvinalexander.com/linux/unix-linux-process-memory-sort-ps-command-cpu)

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

- [smxi/inxi: inxi is a full featured CLI system information tool. It is available in most Linux distribution repositories, and also runs somewhat on BSDs.](https://github.com/smxi/inxi)

### Server status

    # CPU
    cat /proc/loadavg | awk '{print $1}'

    # CPU count
    getconf _NPROCESSORS_ONLN || grep -c ^processor /proc/cpuinfo

    # Memory
    free | grep Mem | awk '{print $2,$3}'

    # Disk
    df -h | awk '$NF == "/" {print $2,$(NF-1),$NF}'

    # Uptime
    cat /proc/uptime

    # Network
    cat /sys/class/net/`route -n | awk '$1 == "0.0.0.0" {print $8}' | head`/statistics/tx_bytes

    # Docker status
    [sudo] docker ps -a

    # Docker Stats
    [sudo] docker stats --format '{{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.NetIO}}' --no-stream

## Resources

- [https://i.linuxtoy.org/files/pdf/fwunixref.pdf](https://i.linuxtoy.org/files/pdf/fwunixref.pdf)
- [10 Useful Commands to Collect System and Hardware Information in Linux](https://www.tecmint.com/commands-to-collect-system-and-hardware-information-in-linux/)
- [Linux Command To Find the System Configuration And Hardware Information – nixCraft](https://www.cyberciti.biz/faq/linux-command-to-find-the-system-configuration-and-hardware-information/)
- [16 commands to check hardware information on Linux](http://www.binarytides.com/linux-commands-hardware-info/)
- [Check Hardware Information On Linux via Command Line](https://www.maketecheasier.com/check-hardware-information-linux/)
- [How To Get Hardware Information On Linux Using dmidecode Command](http://www.thegeekstuff.com/2008/11/how-to-get-hardware-information-on-linux-using-dmidecode-command/)
- [mv操作深入浅出 - 百度技术博客 - 51CTO技术博客](http://baidutech.blog.51cto.com/4114344/743731)
