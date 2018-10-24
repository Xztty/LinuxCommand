
# yum 

## 介绍


## 示例

```text
yum install vim
yum clean all
yum provides
```

## 记录

    安装epel repo
    yum -y install epel-release

    查看repo
    yum repolist 

    yum provides nc

    安装
    yum install opencv

    查找
    yum search opencv 

    yum list | grep opencv  带@标志的为已经安装


    下载rpm包
    yum install --downloadonly --downloaddir=/tmp/xxx httpd
    如果已经安装httpd，但需要下载rpm，可以使用
    yum reinstall --downloadonly --downloaddir=/tmp/xxx httpd


    yum info opencv 

    yum grouplist 

    安装图形桌面开发环境
    yum groupinstall "KDE Desktop"
    startx

    yum groupinfo "Development Tools"


    centos安装中文输入法
    yum install "@Chinese Support"

    yum remove -y gcc-c++

    下载安装包
    yum install --downloadonly words.noarch
    默认情况下载安装包位于
    /var/cache/yum/x86_64/[centos/fedora-version]/[repository]/packages
    通过rpm可以查看安装包内容
    rpm -qpl /var/cache/yum/x86_64/7/base/packages/words-3.0-22.el7.noarch.rpm
    查看安装情况
    rpm -q  words

    查看版本
    strings /usr/lib64/libstdc++.so.6 | grep GLIBC

    查看安装包的具体信息
    repoquery -l maven

    下载安装rpm及其所有依赖
    repotrack -a x86_64 -p /tmp/repotest/ VirtualBox-5.1


## RTFM



## References

