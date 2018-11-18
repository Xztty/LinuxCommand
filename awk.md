
# awk 

## 介绍

用式匹配和处理文本的语言

## 示例

```text
awk  '{print}' /etc/passwd
awk -F: '{print $1 $5}' /etc/passwd
awk '/ERROR/ {print $0}'  log.txt                    # 打印ERROR字符串的匹配行
awk '$1 ~ /ERROR/ {print $0}'  log.txt                    # 打印第一个字段匹配ERROR字符串的行
awk '$1 ~ /ERROR|error/ {print $0}'  log.txt                    # 正则表达式匹配，打印第一个字段匹配ERROR或者error字符串的行
awk '$1 !~ /ERROR/ {print $0}'  log.txt                    # 打印第一个字段不匹配ERROR字符串的行
awk '$1 > 100 {print $0}' log.txt                    # 打印匹配第一个字段>100的行
awk  'BEGIN {FS=":"} $1 ~ /test/ {print $1}' /etc/passwd      # BEGIN在所有文件读取前执行, 匹配用户名含test的行
awk 'length>80' file                                 # >80的行
ss -ant | awk ' {++s[$1]} END {for(k in s) print k,s[k]} '  # awk实现sort uniq的功能, 这里使用到s数组不需要初始化
```

注: 非内置变量不需要加$符号，而0-9所表示的列需要加$符号, -F可以是个字符集合/字符串，字符集-F"[:,+ ]", 字符串 -F"ERROR|error"

## 内置变量

常用的有:

- NR                    The total number of input records seen so far.
- NF                    The number of fields in the current input record 
- FNR                   The input record number in the current input file  注意与NR的区别，FNR是值对应文件，NR值所有文件的总共的当前行数
- FS                    input field separator
- RS                    input record separator
- OFS                   output field separator
- ORS                   output record separator

详细可以看man awk Built-in Variables部分.

## Regular Expression

AWK GNU实现的是ERE，类似使用`egrep`或者`grep -E`. 正则常用语法有:

- .                     任意字符
- $                     行尾 
- ^                     行首
- [abc...]              匹配集合中字符
- [^abc....]            匹配不在集合中的字符
- r1|r2                 或
- r*                    匹配任意次数
- r+
- r?
- (r)
- r{n}

详细可以看 man awk `Regular Expressions` 章节

## TO ADD

- 二维数组
- 控制语句IF...ELSE

## RTFM

11.18 30%

## References

- [The AWK Programming Language](https://github.com/wuzhouhui/awk/blob/master/The_AWK_Programming_Language_zh_CN.pdf)
- https://en.wikibooks.org/wiki/AWK
- https://coolshell.cn/articles/9070.html
