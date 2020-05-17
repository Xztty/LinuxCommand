
# dd 

## 介绍

转换和拷贝文件，常用于磁盘性能测试

## 常用示例

```bash
dd if=/dev/zero of=test.txt bs=64k count=4k oflag=dsync    # 磁盘连续写入测试 256MB  
dd if=test.txt of=/dev/zero bs=64k count=4k iflag=direct   # 磁盘连续读取测试 256MB
```

## RTFM 

9.21 done

## 介绍flag值


    direct: use direct I/O for data
    dsync: use synchronized I/O for data
    nonblock: use non-blocking I/O

## Q&A

### direct I/O 具体是什么？



### 使用dd命令可以测试出来峰值吗？ 

测试发现不能，dd命令写入时iostat 中util使用率没有达到上限，另外当同时执行两个dd命令时，发现iostat util有上升，每个dd命令的写入速度没有太大变化。

### 如何测试随机写的性能？


## References

