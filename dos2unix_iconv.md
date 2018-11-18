
# dos2unix/iconv 

## dos2unix 介绍

DOS/Mac 与 Unix 系统文本文件的转换，常用于换行符转换，bash中遇到DOS的换行即\r\n 常常报错。

### 示例

```text
dos2unix a.txt            # 
dos2unix -n infile outfile
```

### RTFM

11.3 done

## iconv

对文件的编码进行转换，结果输出到stdout

### 示例

```text
iconv -l                                    # 查看当前支持的编码
iconv -f GBK a.txt                          # 将文件编码从GBK转为 LANG指定的编码(locale查看)
cat a.txt | iconv -f GBK -t UTF-8            
```

### RTFM

11.14 done

## References

