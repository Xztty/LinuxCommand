
# top 

## 介绍

显示进程信息

## 示例

```text
top
top -u testuser       # 指定user
top -p 777            # 指定pid
top -d 3              # 间隔3s刷新
top -H                # 显示线程信息
top -c                # 显示进程命令行参数
top -b                # batch mode, 用于获取输出
top -n 2              # 显示结果次数
top -o %MEM           # 按照 %MEM 列排序，从高到低
top -o -%MEM          # 按照 %MEM 列排序，从低到高
```

进程状态

    D = uninterruptible sleep 
    R = running 
    S = sleeping 
    T = stopped by job control signal 
    t = stopped by debugger during trace 
    Z = zombie


## Interactive Command

- h       help
- M       按RES排序
- P       按CPU使用排序
- S       切换到累计模式
- f/F     进入Field Management
- k       kill pid
- T       根据时间排序
- c       命令行参数
- i       toggle idle process，显示在跑的程序
- g       输入窗口编号，1-4为：Def(%CPU)/Job(PID)/Mem/Usr
- R       reverse order 

## Field Management 介绍

管理显示Window、top显示列表，排序字段等

- s 使用字段排序
- `<space>` toggle 显示字段
- a/w   显示window，默认为Def，

## Q&A

Q: 在batch mode时如何让top输出指定的列?

A: 

## RTFM

10.1 done

## References

