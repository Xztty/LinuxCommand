
# man/info 

## man介绍

查看系统在线参考手册

### 示例

```text
man -?
man ls
man 1 signal                # 指定section
man -a signal               # 查看所有的signal相关手册
man -k signal               # 查找描述和名字中含有signal的页面，equivalent to apropos
man -f basename dirname 
man -K signal               # 全局搜索manual页面，时间较长
man -w ls                   # 显示manual page所在的路径
man cp | more               # 使用管道可以指定其他pager
```

### Section

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions eg /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]

### 个人配置

man默认pager使用less打开，以下配置显示当前行数和百分比

在 ~/.bash_profile 增加两行

```bash
export MANPAGER='/usr/bin/less -ismM'
export LESS='r+Gg'
```

### Tricks And Tips

vim中移动到对应函数 `Shift+k` 跳转到man手册

### RTFM

10.3 done

## info

阅读Info格式文档，Info为GNU系统的文档阅读工具，手册源码使用TexInfo编写，支持索引等类HTML跳转等

### 示例

```text
info ls
info 
``` 


### 常用快捷键

    ?键：它就会显示info的常用快捷键。
    n键：显示（相对于本节点的）下一节点的文档内容。
    p键：显示（相对于本节点的）前一节点的文档内容。
    u键：进入当前命令所在的主题。
    m键：敲M键后输入命令的名称就可以查看该命令的帮助文档了。
    g键：敲G键后输入主题名称，进入该主题。
    l键：回到上一个访问的页面。
    space键：向前滚动一页。
    del键：向后滚动一页。
    q：退出info。

### RTFM

10.3 done

## References

- [Linux man 详解](dhttp://blog.51cto.com/zhaoqifly/1830672)
- [man 与 info](https://www.zybuluo.com/wangmiao/note/738619#info-%E6%98%AF%E4%BB%80%E4%B9%88)
