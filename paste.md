
# paste

## 介绍

将多个文件逐行合并到一行中，默认使用\t分隔

## 示例

```text
paste -s a.log                 # 将文件a.log所有行拼接成一行，使用\t分隔, 可以使用 -d "," 指定其他分隔符
paste -d "," a.log b.log                     # 将a.log和b.log的文件逐行合并成一行，使用 "," 分隔
paste -s -d "," a.log, b.log                 # 将a.log合并成第一行，b.log合并成第二行
```

`-d "\n"` 使用换行符合并

## RTFM

10.24 done

## References

