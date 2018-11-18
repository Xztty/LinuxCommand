
# kill/killall

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

## killall 

###  常用示例

```text
```

### RTFM 

## References



