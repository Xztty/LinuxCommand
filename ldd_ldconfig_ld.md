
# ldd/ldconfig/ld

## ldd介绍

ldd是shell脚本，用于显示可执行文件的共享库信息

### 示例

```text
ldd ls
ldd /bin/grep
```

### RTFM

10.13 done

## ldconfig介绍

管理Linux系统的动态共享库的绑定

### 示例

```text
ldconfig                                        # 根据当前配置/etc/ld.so.conf, /lib, /usr/lib中的动态库重新生成cache文件/etc/ld.so.cache, 当安装新库时需要执行
ldconfig -p | grep libmysqlclient.so            # 查看系统库中是否包含libmysqlclient.so
```

### LD_LIBRARY_PATH环境变量

/lib/ld.so在搜索*.so时会优先这个变量对应的路径，然后才会去/etc/lc.so.cache中查找。具体可以查看man 8 ld.so

当存在不同版本的共享库时，可以通过这个变量来指定程序使用的动态库.

### RTFM

10.14 done

## ld介绍

GNU 连接器

### 示例

```text
```

### RTFM


## References

- https://networkengineer.me/2015/06/16/intro-to-linux-shared-libraries-how-to-create-shared-libraries/
- https://stackoverflow.com/questions/34428037/how-to-interpret-the-output-of-the-ldd-program
- [Linux Understanding Shared Libraries](https://www.youtube.com/watch?v=RmdvkUWQ78g)
- http://man.linuxde.net/ldconfig
- [Manage shared libraries](https://www.ibm.com/developerworks/library/l-lpic1-102-3/index.html)

