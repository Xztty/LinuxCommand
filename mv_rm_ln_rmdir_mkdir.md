
# mv/rm/ln/rmdir/mkdir 


## mv

又叫rename

### 常用示例

```bash
mv -b a.txt b.txt   # 先备份b.txt
mv -f a.txt b.txt   # 无提示覆盖
mv -n a.txt b.txt   # b.txt不存在时才执行改名
```

### RTFM

9.18 done

## rm

删除文件或文件夹

### 常用示例

```bash
rm -f a.log       # 不管是否存在，且无提示
rm -d tmp         # 删除文件夹
rm -r test        # 删除文件夹及其文件
```

### RTFM

9.18 done


## ln

在文件间创建链接, 分为软链接和硬链接，两者对比如下：

- 硬链接不产生新inode，与关联文件共用inode，硬链接及其文件对应同一个区域的磁盘内容
- 硬链接只能对已经存在的文件创建，软链接对应的文件可以不存在
- 软链接的文件对应新inode, 和对应的数据块，数据块的内容即所链接文件的路径信息
- 不同文件系统的inode可以重复，因此硬链接不能跨文件系统使用
- 硬链接不能对目录创建，只可以对文件创建

### 常用示例

```bash
ln -s a.txt a.ln   # 创建软链接
ln a.txt a.hl      # 创建硬链接
ln -s a.txt b.txt ~/tmp/     # 在~/tmp/目录中, 创建多个软链接, 名字保持不变
```

### RTFM

9.18 done

### Q&A

- 软链接是个普通的文件，文件名存储在目录的数据中，是否有特殊的标识？

## rmdir 

删除目录

### 常用示例

```bash
rmdir /tmp/test
rmdir -p /a/b/c
```

### RTFM

9.18 done

## mkdir

创建目录

### 常用示例

```bash
mkdir -p /home/test/code/foo   # 创建目录
mkdir -m644 /tmp/test          # 创建目录，并设置文件模式
```

### RTFM

9.18 done

## References

- [理解 Linux 的硬链接与软链接](https://www.ibm.com/developerworks/cn/linux/l-cn-hardandsymb-links/index.html)


