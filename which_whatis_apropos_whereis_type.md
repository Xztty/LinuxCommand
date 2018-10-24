
# which/whatis/apropos/whereis/type

## which介绍

显示shell命令的全路径

### 示例

```text
which ls
which -a ls                 # 显示所有
which --skip-alias ls       # 
```

### RTFM

10.6 done

## whatis介绍

查找manual page的名字，显示manual page的description, 表示该命令的基本功能，与man -f 命令效果一样

### 示例

```text
whatis ls
whatis -s 7  signal                     # 指定section
whatis -s 3 -r  ".*ill"                 # -r 支持正则
whatis -s 3 -w  "*ill"                  # -w 支持通配符
```

### RTFM

10.3 done


## apropos介绍

查找manual page的描述，并显示，与man -k 命令效果一样

### 示例

```text
apropos open
apropos -s 2 open                       # 指定section
apropos -s 3 -r  ".*ill"                # 正则
apropos -s 3 -w  ".*ill"                # 通配符
```

### RTFM

10.3 done

## whereis介绍

用来定位指令的二进制程序、源代码文件和man手册页等相关文件的路径。

### 示例

```text
whereis ls
whereis -b ls                           # 查找二进制文件
whereis -m ls                           # 查找manual 文档
whereis -s ls                           # 查找源文件
cd /usr/bin && whereis -m -u *          # 查看/usr/bin下的命令，存在异常(不止一项或者0项manual page)的命令有哪些 
```

### RTFM

10.6 done


## type介绍

type is a shell builtin

### 示例

```text
type -a ls
```

## References

