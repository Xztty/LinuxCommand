
# printf

## 介绍

格式化数据并输出, 语法与c语言printf一致

## 示例

```text
printf "%d" 100        # 
printf "%.3f" 100.01        # 
printf "%d" 0x1a       # 16进制转10进制
printf "%d" 012        # 8进制转10进制
printf "%#o" 10         # 10 进制转8进制
printf "%#x" 10         # 10 进制转16进制
```

### format简介

format为：`%[flags][width][.precision][length]specifier`, 其中specifier常见为：

- d   signed decimal integer
- u   unsigned decimal integer
- o   unsigned octal 
- x/X Unsigned hexadecimal integer
- f/F  默认精度为小数点后6位, Decimal floating point
- e/E  Scientific notation
- c    character 
- s    string

## RTFM

10.13 done

## References

- http://www.cplusplus.com/reference/cstdio/printf/?kw=printf
- https://blog.csdn.net/k346k346/article/details/52252626

