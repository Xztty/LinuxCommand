
# grep 

## 介绍

用于查找匹配文本内容

## 常用示例

```bash
grep hello log.txt
grep -e a[1-9].log log.txt
grep -e warn -e error log.txt
grep -n error log.txt
grep -a log.txt                         # 像文本一样处理二进制文件
grep -o hello.*world log.txt
grep -w log.txt
grep -E "WARN|ERROR" log.txt
grep -v "DEBUG" log.txt
grep -i "debug" log.txt
grep -C "ERROR" log.txt
grep -A "ERROR" log.txt
grep -B "ERROR" log.txt
grep -f pattern.txt log.txt
grep --line-buffered error log.txt  | cut -f1   # 当grep的输出经过pipe时，会使用fully buffered模式，导致cut结果有延迟，尤其是log.txt文件太大
```

## RTFM progress

9.18 20%

## References

- https://eklitzke.org/stdout-buffering

