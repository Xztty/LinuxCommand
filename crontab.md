
# crontab 

## 介绍

管理每个用户的crontab设置

## 示例

```text
crontab -l
crontab -e
crontab -u testuser -l
crontab -r                     # 直接删除当前用户的cron设置
(crontab -l; echo "* * * * * /bin/bash -c 'date'") | crontab -        # 通过命令行直接增加cron
(crontab -l; echo "* * * * * /bin/bash -c 'date'") > /var/spool/cron/$USER      #直接修改cron对应用户的配置文件

```

## 系统维护cron设置

可以在类/etc/cron.daily中增加需要定期跑的cron任务, 如yum-cron 每日更新rpm.

cron.allow/cron.deny 用于用户黑白名单控制。

## RTFM

11.3 done

## References

