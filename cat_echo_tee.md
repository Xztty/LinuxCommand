
# cat/echo

## cat

读取文件内容，在标准输出中打印

### 示例

```bash
cat a.log
cat -n a.log # 显示行号
cat -t a.log # 显示TAB 为 ^I, 同时显示不可打印字符
```

cat 可以操作二进制文件，它不关心文件编码，统一当初字节流处理，因此有时候可以用来合并多个子文件（如下载分片/压缩文件分片）

### RTFM

- 9.12 done

## echo

回显字符串到标准输出

### 示例

```text
echo -n "test"            # 不显示trailing newline
echo -e "a\tb"            # 对\进行转义
```

If -e is in effect, the following sequences are recognized:

    \\ backslash
    \a alert (BEL)
    \b backspace
    \c produce no further output
    \e escape
    \f form feed
    \n new line
    \r carriage return
    \t horizontal tab
    \v vertical tab

### RTFM

9.21 done

## tee 介绍

从标准输入读取数据，写入文件和标准输出

### 示例

```text
echo "hello" | tee a.log
tail -F a.log | tee b.log | grep "ERROR"       
echo "hello" | tee -a a.log                                # 使用append的方式到文件
```

### RTFM

10.2 done

## References

