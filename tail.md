
# tail

## 介绍

tail查看文本末尾内容, 可以用来监控日志文件新内容

## 常用示例

```bash
tail a.txt
tail -v a.txt
tail -c 16 a.txt
tail -n 100 a.txt
tail -f a.txt         # 跟踪文件，使用文件描述符，文件重命名还是会跟踪
tail -F a.txt         # 跟踪文件，使用文件名跟踪，常用于滚动日志监控
```

## RTFM progress

9.13 done

## References

