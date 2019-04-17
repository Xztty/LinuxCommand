
# timeout

## 介绍

执行带超时限制的command

## 示例

```text
timeout 2 sleep 5                        # sleep 5为要执行命令，timeout设置超时时间2s
timeout -k 1s  2  sleep 5                # 在2s TERM signal之后如果还在跑，则1s后KILL signal
```

## RTFM

11.23 done

## References

