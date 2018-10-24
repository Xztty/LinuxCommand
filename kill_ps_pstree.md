
# kill/ps/pstree

## kill

`type -a kill` 看到 kill 默认是shell内置命令。

    kill is a shell builtin
    kill is /usr/bin/kill

kill 用于给进程或者进程组发送相应信号，当kill指向的是线程号时，信号还是会往线程所在进程发送

### 常用信号

    HUP     1     终端断线
    INT     2     中断（同 Ctrl + C）
    QUIT    3     退出（同 Ctrl + \）
    TERM    15    终止
    KILL    9     强制终止
    CONT    18    继续（与STOP相反， fg/bg命令）
    STOP    19    暂停（同 Ctrl + Z）
    
### 常用示例

```text
kill 100              # 向进程pid 100 发送TERM信号
kill -TERM 100        # 向进程pid 100 发送TERM信号
kill -9 100           # 强制杀死进程pid 100
kill -l               # 查看信号
kill -- -<process group id>  # 向进程组发信号
```

### RTFM progress

9.19 done

## ps 

查看进程信息

###  常用示例

```text
ps -ef                 # 查看所有进程，包含命令参数
ps -ejH [f]            # 查看进程树（父子进程）
ps -eO lstart	       # 默认输出 pid,comm,args等列，指定额外显示的format
ps -eo lstart,pid,user,args --sort user   # 输出指定字段，并排序
ps -u test             # 查看用户test的进程信息
# 如何显示线程信息?
```

### STANDARD FORMAT SPECIFIERS 输出格式含义

重点介绍以下几个

- %cpu         cpu占比
- %mem         内存占比
- etime        进程启动到现在已经elapse的时间
- comm         executable file name
- pid
- lstart       具体启动时间
- args         参数
- rss          使用物理内存
- ppid         父进程pid
- stat         状态

## PROCESS STATE CODES 进程状态码

    D    uninterruptible sleep (usually IO)
    R    running or runnable (on run queue)
    S    interruptible sleep (waiting for an event to complete)
    T    stopped by job control signal
    t    stopped by debugger during the tracing
    W    paging (not valid since the 2.6.xx kernel)
    X    dead (should never be seen)
    Z    defunct ("zombie") process, terminated but not reaped by its parent

### RTFM 

9.20 done


## pstree

显示进程树状结构

### 常用示例

```text
pstree -n                     # 排序
pstree -h                     # 高亮当前进程及其父进程
pstree -a                     # 显示参数
pstree -H 18244 -c            # 高亮指定pid，展开显示
pstree -c -a 18244            # 指定pid显示树状结构
```

### RTFM

9.21 done

## References



