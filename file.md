
# file 

## 介绍

file 判定文件类型, 它还可以检测出文本文件的编码、语言、换行符等

## 常用示例

```bash
file a.sh
file -i a.txt      # 以mime格式显示
file -s /dev/sda   # 显示special file的具体内容
file -z a.zip      # 显示压缩文件具体内容
```

## 检测流程

- filesystem
- magic

## RTFM progress

9.13 done

## References

