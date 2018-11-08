
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

## crontab 格式

`minute   hour   day   month   week   command`

在以上各个字段中，还可以使用以下特殊字符：

- 星号（*）：代表所有可能的值，例如month字段如果是星号，则表示在满足其它字段的制约条件后每月都执行该命令操作。
- 逗号（,）：可以用逗号隔开的值指定一个列表范围，例如，“1,2,5,7,8,9”
- 中杠（-）：可以用整数之间的中杠表示一个整数范围，例如“2-6”表示“2,3,4,5,6”
- 正斜线（/）：可以用正斜线指定时间的间隔频率，例如“0-23/2”表示每两小时执行一次。同时正斜线可以和星号一起使用，例如*/10，如果用在minute字段，表示每十分钟执行一次。

## 常见问题

crontab命令找不到的错误，由于cron job不会执行用户的~/.bash_profile和系统的/etc/profile，所以用户登录后执行的command，很有可能无法在crontab中执行。通过测试发现cron job的path=/usr/bin:/bin  (CentOS7.4), 因此linux command尽量写全路径，或者执行脚本使用Shebang

## RTFM

11.3 done

## References

- man 8 cron

