
# stdbuf

## 介绍

修改command的标准流的缓冲操作，改变缓冲区大小和类型.  标准流 `-i, -o, -e` 分别为输入、输出、错误

## 示例

```text
stdbuf -oL tcpdump -i any arp |  grep 192.168                        # 
tail -f access.log | stdbuf -oL cut -d ' ' -f1 | uniq                # 使cut命令的输出缓冲区使用换行
```

支持buffer类型:

- L         Line Buffered
- 0         Unbuffered

## GLibc Buffer Mode

GNU libc (glibc) uses the following rules for buffering:

Stream | Type |   Behavior |
------- | ------ | ------- |
stdin  | input |  line-buffered |
stdout (TTY) |   output | line-buffered |
stdout (not a TTY) | output | fully-buffered |
stderr |  output | unbuffered |

## Q&A

Q. `tail -f test.log |  grep  test` 可以立即看到输出，但是 `tail -f test.log |  grep  test | grep te` 却没有立即输出

A. 当`grep test` 后面没有命令时，它的输出将直接转到terminal上，此时`grep test`是使用Line Buffered, 当后面有管道时，即 `grep test | grep te`, 它将进入Fully Buffered，缓冲区大小一般为系统页大小(4k?)

## RTFM

10.26 done

## References

- http://www.pixelbeat.org/programming/stdio_buffering/
- https://eklitzke.org/stdout-buffering
- man 3 setbuf
