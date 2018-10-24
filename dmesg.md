
# command 

## 介绍


## 示例

```text

```

## 记录

   
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



## References
