
# ss/netstat

## ss介绍

dump socket统计信息

### 常用示例

```text
ss -a          # 显示所有socket信息
ss -s          # 统计信息，有大量socket时使用
ss -l          # 显示监听端口的socket信息
ss -p          # 显示进程信息
ss -4t         # ipv4 tcp信息
ss -4u           
ss -a state time-wait  # 指定过滤状态
ss -o state established '( dport = :ssh or sport = :ssh )'
```

如何查看进程号

### RTFM

9.29 done

## netstat介绍

用于显示系统网络连接信息、路由表信息等

## 常用示例

```text
netstat -an
netstat -tn
netstat -un
netstat -anp
nesstat -nlp
netstat -4 -tnlp      
netstat -unlp
netstat -s                                  查看各个类型的统计信息，可以用于判断是否有丢包
netstat -s -u                               查看UDP包统计信息
netstat -r                                  查看路由表与route功能重
```

## RTFM

10.14 done

## References

