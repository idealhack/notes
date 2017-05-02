# TCP


## Commands

    netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'


## Resources

- http://colobu.com/2015/06/25/TCP-connection-status/
- http://www.ha97.com/4396.html
