
# xargs 

## 介绍

从stdin获取参数，用于构建和执行命令

## 示例

```text
cat test.txt | xargs -n3                      # n表示几项执行一次命令，默认命令为echo
echo "nameXname" | xargs -dX                  # 执行分隔符
ls *.log | xargs -n1 -t -I {}  cp {} /tmp     # 使用-t 将执行命令打出，-I 指定占位符
find /tmp -name core -type f -print0 | xargs -0 -n10 /bin/rm -f        # -0 表示使用 null character作为标准输入的参数分隔符
echo '11@22@33' | xargs -p -d '@'  echo       # -p 询问是否执行命令，输入y/Y执行
cut -d: -f1 < /etc/passwd | sort | xargs echo 
```

## Q&A

### xargs 与 管道的区别是什么？

管道是I/O重定向技术，xargs是将上一个命令的输入当作下一个命令的参数，不是stdin

### man中的example  `xargs sh -c 'emacs "$@" < /dev/tty' emacs` 怎么解释

https://stackoverflow.com/questions/41043163/xargs-sh-c-skipping-the-first-argument

## RTFM

10.2 done

## References

