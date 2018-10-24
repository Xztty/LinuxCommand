
# command 

## 介绍


## 示例

```text

```

## 记录

    grep pattern
    awk '/detailinfo/ {print $4}' PCMGR.HeartBeat_20160706.log

    not equal
    awk '/detailinfo/ {if($3 != 0) print $4}' PCMGR.HeartBeat_20160706.log

    awk实现sort uniq的功能
    ss -ant | awk ' {++s[$1]} END {for(k in s) print k,s[k]} '


    求和功能 (查看hdfs目录下文件总大小)
    hadoop fs -ls hdfs://10.49.136.233:9000/user/hive/warehouse/u_wsd.db/t_od_pcmgr_publicdns_response/ds=2017081110 | awk -F ' ' '{print $5}'| awk '{a+=$1}END{print a/(1024*1024*1024)}'

    NR 当前行号
    NF 列数



    将每一行拼接起来，使用 , 
    awk '
    BEGIN{
        s=""
    }
    {
    if ((NR) % 3 == 0)
        {
            print s","$0;
            s=""
        }
    else {
        if (length(s) == 0)
        {
            s=$0
        }
        else
        {
            s=s","$0
        }
      }
    }
    ' a

## RTFM



## References

