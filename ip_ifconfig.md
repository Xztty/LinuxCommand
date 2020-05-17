
# ip/ifconfig

## ip 介绍

管理设备、路由和隧道

## 常用示例

```bash
ip addr show
ip addr add 192.168.1.10/24 dev eth0
ip route add default via 192.168.190.105 dev eth0 proto static metric 100
ip route add 192.168.1.0/24 dev eth0 scope link         # 增加路由表
ip route del 192.168.1.0/24 dev eth0 scope link         # 删除路由表

ip link set enp0s3 up
ip link set enp0s3 down
```

## RTFM 

9.20 done

## References

- [Linux 路由基础知识介绍](https://blog.csdn.net/liupeifeng3514/article/details/79054475)
- [12 个 ip 命令范例](https://linux.cn/article-9230-1.html)
