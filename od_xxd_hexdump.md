
# od/xxd/hexdump

## od

以8进制或其他格式, dump文件到标准输出

### 常用示例

```text
od a.log                # 默认8进制显示，每行16字节
od -A x -t x2z  a.log   # 以16进制显示，每行16字节
od -A d a.log           # 以十进制显示地址
od -c a.log             # 显示可打印ascii字符，其他使用八进制
```

### RTFM

9.26 done

## xxd

产生16进制dump，或者反转16进制dump文件

### 常用示例

```text
xxd a.log a.hex.log
xxd -r a.hex.log a.log    # 可以编辑对应16进制，然后反转
```

注: `-r 参数根据 -c参数指定列读取后，不在读该行，因此改变xxd每行后面的ascii字符不会影响结果`

### RTFM

9.26 done

## hexdump

查看文件的16进制编码

### 常用示例

```text
hexdump a.log
```

### RTFM

40%

## References

