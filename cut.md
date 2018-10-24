
# cut

## 介绍

选取每行中指定列

## 常用示例

```text
cut -c -10 a.txt          # 每行前10列
cut -c 10- a.txt          # 每行从第10列开始到结束
cut -d ',' -f 1  a.txt    # 使用,分隔符，选取指定列
cut -d ',' -f 2-  a.txt    # 使用,分隔符，选取第二列到最后一列
```

## Q&A

### 分隔列数指定吗？比如 'a,b,c' 指定两列，结果为 a和b,c


## RTFM

9.20 done

## References

