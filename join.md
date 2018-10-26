
# join 

## 介绍

将两个文件根据指定列进行join, 两个文件需是根据join列排好序的.

## 示例

```text
join f1 f2                                    # 根据第一列join，其他列拼接在后面
join -a 1 f1 f2                               # 同上，但是保留f1文件中没有匹配的行
join -a 1 -a 2 f1 f2                          # 同上，但是保留f1&f2文件中没有匹配的行
join -o 1.1 -o 1.2 -o 1.2  <(sort s.log) <(sort t.log)    # 输出的列自定义，FORMAT: FILENUM.FILED，其中FIELD从1开始，FILENUM为1或2
```

## RTFM

10.26 done

## References

