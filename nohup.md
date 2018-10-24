
# nohup

## 介绍

执行使其他命令对SIGNAL HANGUP免疫, 输出到nohup.out

## 示例

```text
nohup (echo "begin"; sleep 100; echo "end")   # 启动命令，即使当前连接中断也会继续执行命令
nohup xxx_command > out.txt                   # 指定了输出，则不会产生nohup.out文件
nohup xxx_command > /dev/null &               # nohup启动并后台运行
```

## RTFM

10.13 done

## References

