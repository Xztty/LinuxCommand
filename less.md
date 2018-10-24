
# less

## 介绍

less用于查看文本内容，以翻页的形式，与more类似，但是支持backward movement，即往回翻页移动，使用广泛如: man/git等

less不必读取所有文件内容，所以大文件的时候较vim启动更快

## 常用示例

```bash
less a.log
less -N a.log # 显示行号
```

## 内部命令

- g         开头
- G         结尾
- f         下一页
- b         上一页
- u
- d
- R         重新加载文件
- F         类似tail -f功能
- m[a-z] 使用mark标记
- '[a-z] 跳回到标记处
- /pattern 从当前屏幕往下搜索
- ?pattern 从当前屏幕往上搜索
- :e [filename] 打开文件
- -N,enter  显示行号
- :n 查看下一个文件
- :p 查看上一个文件

## LESS environment

示例：export LESS='-r +Gg', 前者-options, 后者+commands

## RTFM

- 10.17 50%

## Q&A

- tag 是什么意思？
- line editing 怎么使用？
- 试验发现，less可以读取 .gz 结尾的压缩文件的内容，类似zcat


## References

- https://en.wikipedia.org/wiki/ANSI_escape_code

