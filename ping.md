
# ping 

## 介绍

使用ICMP包用于主机间网络探测

## 示例

```text
ping 127.0.0.1
ping -c 10 127.0.0.1            # 次数
ping -s 200 127.0.0.1         # 指定数据payload大小
```

## Q&A

ping -t 100 127.0.0.1 显示的时候没有看到ttl变化

## RTFM

12.3 done

## References

