
# nc 

## 介绍

强大的网络数据重定向工具，可以用于端口扫描、传输文件、网络聊天等。

## 示例

```text
nc www.example.com 80               # 请求连接网站，相当于客户端
nc 127.0.0.1  80                    # 请求连接网站，相当于客户端
nc -lk 8080                         # 监听端口，允许多链接
nc -u 127.0.0.1 80                  # 使用udp连接
nc -l 127.0.0.1 10000 -e /bin/bash          # 创建后门，客户端连上就可以执行命令，客户端执行命令并看到bash输出结果   nc 127.0.0.1 10000
nc -z -v -w10 127.0.0.01 180                   # 测试tcp端口是否开放, 设置超时10s
nc -lu 127.0.0.1 80                 # 监听udp端口，注:只能处理一个链接!
```

## 传输文件

在一台机器上运行 `nc -l 9999 > test.txt`, 在另一台机器上运行`nc $remote_ip 9999 < test.txt`

## RTFM

10.5 done

## References

- http://blog.jobbole.com/113410/
- [NC UDP Strange Behaviour Listen](https://markhneedham.com/blog/2013/07/30/netcat-strange-behaviour-with-udp-only-receives-first-packet-sent/)
- [使用Netcat进行黑客攻击]https://www.freebuf.com/column/135007.html
