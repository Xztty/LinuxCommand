
# vmstat/iostat/mpstat 

##  vmstat介绍

### 示例

```text
vmstat 1 10                 # 1 为delay second, 10为显示次数
vmstat 1
```

### 输出字段分析

详细查看FIELD DESCRIPTION FOR VM MODE部分，常用重点关注

- si                Amount of memory swapped in from disk (/s)
- so                Amount of memory swapped to disk (/s)
- cs                The number of context switches per second
- wa                Time spent waiting for IO

### RTFM
 
10.7 done

## References

- https://en.wikipedia.org/wiki/Paging

