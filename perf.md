
# command 

## 介绍


## 示例

```text

```


## 记录


    1. 先观察是否有线程占用过高 Top -H ，发现确实有部分线程CPU占用过高。
    2. 采集线程：perf record -ag -t31639
    其中31639为线程ID，过一会（如几秒后）CTRL+C退出采集，这时在当前目录下生成perf.data.
    3. 生成调用链
    perf script -i perf.data > ReportProxyServer.txt
    4. 生成dot格式
    python gprof2dot.py -f perf ReportProxyServer.txt > ReportProxyServer.dot
    5. 生成图形
    dot -Tpng -o ReportProxyServer.png ReportProxyServer.dot

    6. 打开ReportProxyServer.png看图形调用量，寻找执行热点

    (注：第4、5步可以在linux下完成，也可以在windows完成，需要安装python和graphviz。windows下的相关安装包见附件，或到网上下载）

      

    perf record -ag -p pid
         -o output file 
    perf record -ag -t tid
    perf report

    查看进程top
    perf top -p 71787

    查看线程耗时top
    perf top -t 119763

 
 
## RTFM



## References

