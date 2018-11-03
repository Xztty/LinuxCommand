
# ulimit 

## 介绍

ulimit为bash builtin command, 用于系统控制shell启动进程的资源，如最大打开进程数、最大的文件数、coredump 文件大小限制。 

## 示例

```text
ulimit -a            # 查看当前所有限制
ulimit -n 65536      # 增大打开文件数量到65536
ulimit – c unlimited # 对core文件大小不限制
```

### 常用几个选项

    a     All current limits are reported
    b     The maximum socket buffer size
    c     The maximum size of core files created
    n     The maximum number of open file descriptors (most systems  do  not allow this value to be set)
    u     The maximum number of processes available to a single user
    T     The maximum number of threads

## ulimit 配置

可以在~/.bash_profile中单独设置，此时限制的是登录的shell及其子进程，通过配置系统文件 /etc/security/limits.conf 可以针对 用户/组 进行设置，同一用户的配置后面的覆盖前面的值。

## RTFM

11.3 done

## References

- /etc/security/limits.conf
- https://www.ibm.com/developerworks/cn/linux/l-cn-ulimit/index.html
