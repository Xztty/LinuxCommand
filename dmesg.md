
# dmesg 

## 介绍

检查和控制内核的环形缓冲区, 一般用于检查进程被OOM被KILL的情况。

## 示例

```text
dmesg 
dmesg -l err,warn -H                    # 指定级别，-H是显示更可读，颜色，时间等
dmesg -c                                # 读取并清理ring buffer
```

注：CentOS6和CentOS7的dmesg option差别很多，以上内容为基于CentOS7

## CentOS6 显示时间
   
    转换为时间
    #!/bin/bash
    dmesg_with_human_timestamps () {
        $(type -P dmesg) "$@" | perl -w -e 'use strict;
            my ($uptime) = do { local @ARGV="/proc/uptime";<>}; ($uptime) = ($uptime =~ /^(\d+)\./);
            foreach my $line (<>) {
                printf( ($line=~/^\[\s*(\d+)\.\d+\](.+)/) ? ( "[%s]%s\n", scalar localtime(time - $uptime + $1), $2 ) : $line )
            }'
    }
    #alias dmesg=dmesg_with_human_timestamps
    dmesg_with_human_timestamps


## RTFM

12.11 done

## References

