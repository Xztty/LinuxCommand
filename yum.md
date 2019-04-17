
# yum 

## 介绍


## 示例

```text
yum install vim
yum remove -y gcc-c++
yum info vim
yum clean all
yum provides strace                                         # 搜索包内文件, 支持文件通配符
yum -y install epel-release
yum repolist
yum search opencv                                            # 搜索包名、描述中的关键词
yum list | grep opencv
yum install --doenloadonly --downloaddir=/tmp epel-release   # 下载rpm包，不安装
yum reinstall --doenloadonly --downloaddir=/tmp epel-release   #重新 下载rpm包，不安装
yum grouplist
yum groupinfo "Development Tools"      # 查看软件组信息
yum groupinstall "KDE Desktop"
```

注: 默认情况下载安装包位于 `/var/cache/yum/x86_64/[centos/fedora-version]/[repository]/packages`, 通过rpm可以查看安装包内容 `rpm -qpl /var/cache/yum/x86_64/7/base/packages/words-3.0-22.el7.noarch.rpm`

## yum-cron 自动更新

定期更新rpm包，可以使系统更健康，使用yum-cron每天自动下载更新, 以下命令安装并启动

```
yum -y install yum-cron
systemctl enable yum-cron
systemctl start yum-cron 
```

`rpm -ql yum-cron` 可以看到两个配置增加到cron中: /etc/cron.daily/0yum-daily.cron, /etc/cron.hourly/0yum-hourly.cron .

注: 更多关于yum-cron配置的信息不是很全, `RedHat Enterprise Linux-7 System Administrators Guide 9.7 AUTOMATICALLY REFRESHING PACKAGE DATABASE AND DOWNLOADING UPDATES WITH YUM-CRON`, 有介绍

## Q&A

### 如何查看一个包的依赖项

查询未安装软件包的依赖关系 `rpm -qRp vim-common-6.3.046-2.el4.1.x86_64.rpm`

查询已安装软件包的依赖关系 `rpm -qR vim-common-6.3.046-2.el4.1`


## RTFM

11.2 50%

## References

- https://amon.org/yum-cron
- https://linux.die.net/man/8/yum-cron

