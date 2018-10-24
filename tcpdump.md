
# tcpdump

## 介绍

网络抓包分析工具

## 常用options

    -i any : Listen on all interfaces just to see if you’re seeing any traffic.
    -i eth0 : Listen on the eth0 interface.
    -D : Show the list of available interfaces
    -l : Make stdout line buffered.  Useful if you want to see the data while capturing it, eg: pipe to grep
    -n : Don’t resolve hostnames.
    -nn : Don’t resolve hostnames or port names.
    -tttt : Give maximally human-readable timestamp output.
    -X : Show the packet’s contents in both hex and ASCII.
    -XX : Same as -X, but also shows the ethernet header.
    -v, -vv, -vvv : Increase the amount of packet information you get back.
    -c : Only get x number of packets and then stop.
    -s : Define the size of the capture in bytes. Use -s0 to get everything, unless you are intentionally capturing less.(抓取每个包的部分)
    -e : Get the ethernet header as well.
    -q : Show less protocol information.
    -E : Decrypt IPSEC traffic by providing an encryption key.

## 示例

```text
tcpdump
tcpdump -D                                 # 查看interface列表
tcpdump -c 100                            # 指定抓取包的数量
tcpdump -i any dst port 10001
tcpdump -i any dst host 127.0.0.1
tcpdump -i any tcp and dst host 127.0.01 and dst port 
tcpdump -i eth0  greater 1024             # 指定包大小
tcpdump -i eth0  less 1024             # 指定包大小
tcpdump -i eth0 host 192.168.0.100 and \(192.168.0.101 or 192.168.0.102\)`   # 指定机器间通信
tcpdump -i any  host ! 127.0.0.1 and greater 305 -nn            # 指定非127.0.0.1的包
tcpdump -i any 'tcp[tcpflags] & tcp-syn != 0'                  # tcp-fin, tcp-syn, tcp-rst, tcp-push, tcp-act, tcp-urg
tcpdump -i any 'tcp[13] & 2!=0'    # 判断指定字节，功能同上
tcpdump -i any udp and src host 10.0.0.1 -Xnlps0 -w  ~/out.pcap
tcpdump -nvX src net 192.168.0.0/16 and dst net 10.0.0.0/8 or 172.16.0.0/16  # 指定网络
```

## expression介绍

expression用于包过滤，支持语法丰富：包大小、包中的Flags、主机端口、协议等, 详见man 7 pcap-filter 

## tcpdump -i any 抓包失败，但是指定iface可以

## promiscuous mode(混杂模式)

混杂模式下网卡将来自接口的所有数据都捕获并交给相应的驱动程序（即不验证MAC地址），可以用与监听网络数据

`-p` 选项可以开启混杂模式

## Q&A

### 编写echo server/client, client -> server 发包10w，server显示收到10w，但通过tcpdump抓包得到结果1.4w条，tcpdump性能很差？

这位tcpdump抓包结束后输出

```
14008 packets captured
200000 packets received by filter
169983 packets dropped by kernel
```

尝试加大tcpdump接收缓冲区 -B 65536
???

### 当系统发生丢包时，可以通过tcpdump抓包到吗？有什么办法抓到包？

?

## RTFM

10.14 

## References

- https://www.tcpdump.org/
- https://www.andreafortuna.org/technology/networking/tcpdump-a-simple-cheatsheet/
- https://wiki.linuxfoundation.org/networking/kernel_flow
- [The Journey of a Packet Through the Linux Network Stack](https://www.cs.dartmouth.edu/~sergey/me/netreads/path-of-packet/Lab9_modified.pdf)

