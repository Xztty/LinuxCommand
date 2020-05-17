
# wget/curl 

## wget介绍

非交互式网络下载器，可以用于下载网页、文件、镜像网站、ftp文件等，支持断点续传、限速、限量、过滤指定类型文件等功能。

## 示例

```text
wget www.baidu.com -O baidu.html       # 指定保存文档名
wget www.baidu.com -O /tmp/a.log       # 日志
wget -b www.baidu.com -q                 # start background, close output log  
wget --limit-rate=300k http://mirrors.aliyun.com/centos/7.5.1804/isos/x86_64/CentOS-7-x86_64-Minimal-1804.iso  # 限速
wget -c http://mirrors.aliyun.com/centos/7.5.1804/isos/x86_64/CentOS-7-x86_64-Minimal-1804.iso           # 断点续传
wget -r -p -np -k https://coolshell.cn/   # 镜像一个网站内容，wgets将遵守robots.txt标准, -r 默认深度为5层，可以使用-l设置max depth level, -k 转换为本地连接
wget -Q10m -r -p -np -k -e robots=off http://mirrors.163.com/debian/dists/jessie/main/installer-amd64/      # wget 将无视robots.txt文件
wget -Q10m http://xxx.com/                # 指定下载限额，超过限额则停止下载新文件(对于单个文件的情形不影响)，quota设置为0/inf表示不限制
wget -t0 http://xxx.com                   # 不限制重试次数
wget ftp://ip:port/file –ftp-user=用户名 –ftp-password=密码    # 下载ftp文件
wget --no-proxy www.baidu.com             # 不使用代理
wget -S www.baidu.com                     # 显示response header
```

### 代理设置

在环境变量中有  http_proxy=http://127.0.0.1:1197 或 https_proxy=xxx 就可以生效, http_proxy和https_proxy分别对应域名中的http和https，

不需要代理的域名配置 no_proxy 环境变量，多个域名使用逗号分割

wget 无法支持socks5代理

### RTFM

10.5 done

## curl介绍

### 示例

```text
curl www.qq.com
curl -L www.facebook.com                                               # Follow Redirection, curl默认不会
curl --socks5 127.0.0.1:1080 www.qq.com
curl -XGET -H "X-Forwarded: 104.107.31.37" "http://xxx..com/myip"      # 发送GET请求，指定Header
curl -X POST -H 'Content-Type: application/json' "http://xxx.com" -d @datafile.txt  # 通过-d @+文件名，指定post的数据从文件读取
```

POST请求示例

```text
curl -XPOST localhost:9000/graphs/getEdges -H 'Content-Type: Application/json' -d '
{
  "srcVertices": [{"serviceName": "KakaoFavorites", "columnName": "userName", "id":"Elmo"}],
  "steps": [
    {"step": [{"label": "friends", "direction": "out", "offset": 0, "limit": 10}]}
  ]
}
'
```

### RTFM


## References

- [wget整站下载被robots.txt阻挡时的处理方法](https://www.sudops.com/wget-recursive-download-blocked-by-robots-txt.html)

