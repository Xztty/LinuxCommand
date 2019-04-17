
# tr

## 介绍

转换、压缩、删除字符，可以方便实现sed的一些功能

## 示例

```text
echo "a b" | tr -d ' '           # 删除空格
echo "a b" | tr ' ' '\n'         # 空格转换为换行
echo "HELLO WORLD" | tr 'A-Z' 'a-z' # 转为小写
echo aa.,a 1 b#$bb 2 c*/cc 3 ddd 4 | tr -d -c '0-9 \n'  # 只保留补集
echo -n  -e "ab\r\n" | tr -d "\r"                       # 功能类似与dos2unix，删除\r
tr -c "[:alpha:]" "\n" < $f | tr  '[A-Z]' '[a-z]' | grep "[a-z]"            # 抽取文件中单词,用于统计等
```

注: tr只从标准输入读取数据，所以使用io redirection/bash pipe: `tr -d ' ' <a.txt`

另外 tr 只能将一个字符集转换为对应的字符集，不能将一个字符转为字符串

## RTFM

10.13 done 

## References

