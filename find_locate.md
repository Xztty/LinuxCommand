
# find/locate

## find

从目录树中搜索文件

find中expression包含: option/test/action/OPERATORS

### 常用示例

```text
find . -name a.txt                    # 查找文件名
find -L .  -name a.txt                # 查找文件名，文件名支持通配符，-L 指同时查找软链接所指文件
find -L . -name a.txt -maxdepth 1     # 指定最大深度
find -L . -newer a.txt -name "*.txt"  # 查找比指定文件更新的文件
find . -regextype posix-egrep -regex ".*a\.(txt|sh)" -type -f # 待验证, regex匹配的是path，与name指匹配文件名不一样
find . -perm /u+w,g+w                     # 带-开头的，为部分匹配，即查找group为writable
find . -perm 644                      # 不带-为全匹配，即查找的文件的权限需完全匹配
find . -size +10M                     # 大于10M的文件
find . -type f                        # 查找文件
find . -mtime +7 -name "*.log"        # 查找7天之前(modify time)的log后缀文件, 注：0表示最近一天内，+0表示最近一天之前, -0 含义待验证
find . -size +10M -delete             # 删除匹配

## action
find . -print0                    # 使用 null character 作为各个结果的分隔符，用于当文件名含有换行符时
find . -empty -exec echo {} \;    # 打印空文件，此处使用 \; 的原因是 bash中;是两个目录的分割符，而find的action中 -exec 需要用到;作为该action部分的结束符
find . -empty -exec echo {} \; -exec ls {} +   # 多个action示例
find . -empty -exec echo {} +     
find . -empty -ok  rm {} \;
```

### type常用类型

- f regular file
- d directory
- b block (buffered) special
- c character (unbuffered) special
- p named pipe (FIFO)
- l symbolic link; this is never true if the -L option or the -follow option is in effect, unless the symbolic link is broken. If you want to search for symbolic links when -L is in effect, use -xtype.
- s socket
- D door (Solaris)

### RTFM progress

9.29 done


## locate

## References
