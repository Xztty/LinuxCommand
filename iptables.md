
# iptables 

## 介绍

管理网络包的过滤策略，用于防火墙功能

## 示例

```text
iptables -L -n -v --line-number
iptables -L -n -v -t nat   
iptables -S
iptables -A INPUT -d 139.162.10.100/32 -p tcp -m tcp --dport 22 -j ACCEPT
iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT  -m state --state NEW,ESTABLISHED -j ACCEPT
iptables -P INPUT DROP                                                          # INPUT Chain 默认策略DROP
iptables -D INPUT 3                                                             # 删除策略               
```

## RTFM



## References

