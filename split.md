
# split 

## 介绍

将文件分成多块，可以使用 cat 进行合并

## 示例

```text
split -n 5 -d bigfile piece_prefix     # 指定块数分隔，以数字最后后缀
split -b 10m -d bigfile smallprefix    # 将大文件分块，每块 10m，指定块文件前缀
split -l 1000 
```

## RTFM

10.16 done

## References

