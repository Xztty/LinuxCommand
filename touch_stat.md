
# touch/stat 

## touch

修改文件的access/modify time

### 常用示例

```bash
touch log            # 修改时间
touch -a log         # 修改access time
touch -m log         # 修改modify time
touch -d "1 days ago" log # 指定时间
touch -r log from.log  # 以另一个文件from.log的时间来更新log 
```

### RTFM progress

9.18 done

## stat

显示文件或者文件系统的状态信息

### 常用示例

```bash
stat log
stat -c "%A %B %F %i" log   # 指定字段和格式
stat -f log                 # 显示文件所在的文件系统的信息
```
### RTFM progress

9.18 done

## References

