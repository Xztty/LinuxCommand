
# nc 

## 介绍

强大的网络数据重定向工具，可以用于端口扫描、传输文件、网络聊天等。

## 示例

```text
nc www.example.com 80               # 请求连接网站，相当于客户端
nc 127.0.0.1  80                    # 请求连接网站，相当于客户端
nc -lk 8080                         # 监听端口，允许多链接
nc -u 127.0.0.1 80                  # 使用udp连接
```

## 传输文件

在一台机器上运行 `nc -l 9999 > test.txt`, 在另一台机器上运行`nc $remote_ip 9999 < test.txt`

## RTFM

10.5 done

## References

- http://blog.jobbole.com/113410/

