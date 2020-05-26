
# grep 

## 介绍

用于查找匹配文本内容

## 常用示例

```bash
grep hello log.txt
grep -e a[1-9].log log.txt
grep -e warn -e error log.txt           # warn或error
grep -n error log.txt
grep -a error log.txt                   # 像文本一样处理二进制文件
grep -o hello.*world log.txt
grep -w error log.txt                   # 匹配完整单词error
grep -E "WARN|ERROR" log.txt
grep -v "DEBUG" log.txt
grep -i "debug" log.txt
grep -C "ERROR" log.txt
grep -A "ERROR" log.txt
grep -B "ERROR" log.txt
grep -f pattern.txt log.txt
grep --line-buffered error log.txt  | cut -f1   # 当grep的输出经过pipe时，会使用fully buffered模式，导致cut结果有延迟，尤其是log.txt文件太大
ps -ef | grep [s]shd 
```

注: grep如果在文件中找到匹配字符串，进程exit code为0，反之为1

## Q&A

### 匹配pattern如何关闭BRE语法，当成普通字符串？

`-F` 即可



## RTFM progress

9.18 20%

## References

- https://eklitzke.org/stdout-buffering
- https://unix.stackexchange.com/questions/74185/how-can-i-prevent-grep-from-showing-up-in-ps-results
