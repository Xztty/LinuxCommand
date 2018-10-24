
# sort/uniq

## sort 

按行对文件内容进行排序

### 常用示例

```bash
sort -u             # 去重
sort -t , -k 2 test.txt     # 使用`,`分割列，并以第二列进行排序
sort -r             # 倒序
sort -n             # 转为数字排序
sort -h             # 按照可读的单位大小进行排序，1K 1M 1G
```

### RTFM

9.21 done

## uniq

打印或者忽略重复的行，注意：只比较连续的两行，因此一般前接 `sort a.txt | uniq`
### 示例

```text
uniq a.txt          # 
uniq -c a.txt       # 显示
uniq -u a.txt       # 只显示出现一次的内容
uniq -d a.txt       # 只显示出现多次的内容
```

### RTFM

10.14 done

## References

