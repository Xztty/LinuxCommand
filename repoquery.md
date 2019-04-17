
# repoquery 

## 介绍

从yum的仓库中查看信息

## 示例

```text
repoquery '*perl*'                          # 查看匹配通配符的软件包
repoquery -l yum-cron.noarch                # 查看软件包里的文件信息
```

## 包名格式

以下格式都可以:

    name
    name.arch
    name-ver
    name-ver-rel
    name-ver-rel.arch
    name-epoch:ver-rel.arch
    epoch:name-ver-rel.arch

## RTFM

11.25 done

## References

