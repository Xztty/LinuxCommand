
# date/clock

## 介绍

显示/设置时间

### 示例

```text
date
date -R                                     # 当前时间和时区
date +%s                                    # 当前时间unix timestamp 
date -d "1 days ago"
date -d "1 days ago" +"%F %T%z"             # 2018-10-01 20:16:49+0800
date -d "1 days ago" +"%Y-%m-%d %H:%M:%S"   # 2018-10-01 20:16:49
date -d  @1538482847                        # 将unix timestamp转为 datetime，结果如：Tue Oct  2 20:20:47 CST 2018
date -s "2018-10-02 12:25:44"               # 设置系统时间，临时生效, 使用clock写入硬件
```

### RTFM

10.2 done

## clock

查询和设置硬件时间

### 示例

```text
clock -w
```
### RTFM

10.2 8%

## References

