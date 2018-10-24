
# comm 

## 介绍

比较两个排好序的文件，comm f1 f2 输出三列分别为

- 第一列，只在f1存在
- 第二列，只在f2存在
- 第三列，共同存在

## 常用示例

```text
comm -12 f1 f2         # 得到f1和f2的交集
comm -23 f1 f2         # 得到只在f1的部分
comm -13 f1 f2         # 得到只在f2的部分

# 排序并对比
comm <(sort f1|uniq) <(sort f2|uniq)
```

## RTFM

9.29 done

## References

