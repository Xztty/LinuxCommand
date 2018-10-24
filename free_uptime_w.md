
# free/uptime 

## free

显示系统内存使用情况

### 常用示例

```text
free -h
free -m
free -g
```

### 各列含义

- buffers: Memory used by kernel buffers (Buffers in /proc/meminfo)
- cache: Memory used by the page cache and slabs (Cached and Slab in /proc/meminfo)
- available: Estimation of how much memory is available for starting new applications, without swapping.

### RTFM

9.21 done

## uptime

显示系统一些信息：当前时间、已经运行时间、登录用户数、系统负载

### load average 

三个值，分别为最近1/5/15min系统的平均负载，当值大于cpu核数时，说明系统负载重，一般达到80%*cpu时，需要扩容

### RTFM

9.21 done

## w

显示uptime信息，同时显示用户运行的程序。

### 示例

```text
w
w test           # 显示用户test运行程序的信息
```

### RTFM

9.21 done

## References

- http://www.brendangregg.com/blog/2017-08-08/linux-load-averages.html

