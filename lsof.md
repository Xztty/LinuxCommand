
# lsof 

## 介绍

查看系统打开文件情况

文件类型包括

- REG 
- DIR
- CHR
- unix
- IPv4
- BLK
- FIFO
- sock

## 常用示例

```text
lsof                       # 查看素有
lsof -u root               # 查看指定用户
lsof -u ^root              # 查看非root用户
lsof -p 28553              # 查看指定pid
lsof -p ^28553             # 查看除了指定pid的进程打开情况
lsof -c nc                 # 查看进程名为nc的打开情况
lsof -i :90                # 查看打开端口80
lsof -i 4TCP               # 查看ipv4 udp情况
lsof -i 4 -a -p 1234,1235  # 查看ipv4 且 进程 1234/1235 打开文件
lsof /dev/log              # 打开文件的进程
```

lsof fd列含义

- cwd：表示current work dirctory，即：应用程序的当前工作目录，这是该应用程序启动的目录，除非它本身对这个目录进行更改
- txt：该类型的文件是程序代码，如应用程序二进制文件本身或共享库，如上列表中显示的 /sbin/init 程序
- lnn：library references (AIX);
- er：FD information error (see NAME column);
- jld：jail directory (FreeBSD);
- ltx：shared library text (code and data);
- mxx ：hex memory-mapped type number xx.
- m86：DOS Merge mapped file;
- mem：memory-mapped file;
- mmap：memory-mapped device;
- pd：parent directory;
- rtd：root directory;
- tr：kernel trace file (OpenBSD);
- v86  VP/ix mapped file;
- 0：表示标准输出
- 1：表示标准输入
- 2：表示标准错误

一般在标准输出、标准错误、标准输入后还跟着文件状态模式：

- u：表示该文件被打开并处于读取/写入模式。
- r：表示该文件被打开并处于只读模式。
- w：表示该文件被打开并处于。
- 空格：表示该文件的状态模式为unknow，且没有锁定。
- -：表示该文件的状态模式为unknow，且被锁定。


## RTFM

7%

## References

