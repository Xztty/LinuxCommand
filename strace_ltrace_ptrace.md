
# strace/lstrace 

## strace介绍

跟踪系统调用和信号

### 示例

```text
strace ls                       # 跟踪并运行命令的系统调用和信号
strace -o result.txt ls -al     # 将结果存入文件
strace -c ls -al                # 结束时输出统计信息
strace -f -p pid                # 同时跟踪fork/clone的子程序 
strace -ff -p pid -o result     # 同上，但是每个子进程输出到文件中result.pid中
strace -tt -p pid               # -tt 显示时间，精确到微妙
strace -T -p pid                # 显示系统调用使用时间
strace -x -p pid                # 将non-ASCII字符以16进制显示
strace -s 64 -p pid             # 调整输出中的字符长度
```

注: strace默认只跟踪主线程的调用情况，针对多线程的程序需要使用`-f`才能更好看到信息

### -e expr

strace提供了跟踪指定系统调用的能力，具体参看man page，同时提供了几种快捷方式

- -e trace=file                 # 文件相关调用          
- -e trace=process              # 进程调用
- -e trace=network              # 网络调用 
- -e trace=signal
- -e trace=ipc
- -e trace=desc
- -e trace=memory

### 输出字段解释

TODO

### RTFM

10.7 done

## ltrace介绍

库调用跟踪器

### 示例



## References

- http://github.tiankonguse.com/blog/2016/08/28/strace.html

