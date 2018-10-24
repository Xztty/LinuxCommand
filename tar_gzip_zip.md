
# tar/gzip/zip 

## tar介绍

打包工具，将多个文件文件夹打包成存档文件，支持压缩

### 示例

```text
tar -cf bf.tar foo/a.txt bar/b.txt                                  # 创建存档文件
tar -tvf bf.tar                                                     # 显示存档文件内容
tar -xf bf.tar                                                      # 提取存档当文件
tar -czf bf.tar.gz foo/a.txt bar/b.txt                              # filter the archive through gzip
tar -xzf bf.tar.gz                                                  # extract the archive filter through gzip
tar -rzf bf.tar.gz soo/c.txt                                        # 在archive末尾追加文件，这个操作有更新文件的作用，通过 -tvf 可以看到两个相同的文件，提取文件时以最后一个为准
tar -xf  /tmp/bf.tar --strip-components=1  foo/a.txt                # strip 解压出来的文件的路径名 
tar -xf  /tmp/bf.tar --backup --strip-components=0  foo/a.txt       # --backup 表名需要备份
tar -C koo  -xf bf.tar                                              # 将解压内容放于 koo 目录中
tar -caf bf.tar.gz foo/a.txt bar/b.txt                              # 根据 存档文件后缀名自动选择压缩算法
tar --delete -f bf.tar bar/b.txt                                    # 删除存档中的某个文件操作
tar -Af result.tar other.tar                                        # 将other.tar的文件追加到 result.tar中
```

### RTFM

10.7 done

## gzip/gunzip/zcat 介绍

压缩和展开文件

### 示例

```text
gzip a.tar                                                          # 压缩文件增加后缀.gz，并删除源文件
gzip -c a.tar > a.tar.gz                                            # -c 压缩文件输出到stdout，并重定向到新文件
gzip -d a.tar.gz                                                    # 解压文件并去除.gz后缀，删除源文件
zcat a.tar.gz                                                       # 类似cat，查看压缩文件内容
gzip -l -v a.tar.gz                                                 # 查看压缩文件的信息 压缩方法、比率等
gzip -1 a.tar                                                       # -1 表示压缩速度最快，压缩率低，可以使用 --fast 替换
gzip -9 a.tar                                                       # -9 压缩速度最快，压缩率低，可以使用  --best 替换
```

## Q&A

- 试验发现，gzip可以基于数据流来压缩，如hdfs/kafka场景，具体原理是？（写了个脚本持续产生数据，发现间隔一段时间会压缩）
- 压缩文件过大，拆成多个文件传输再合并的命令？ 使用 split 分块，在使用 cat 合并

### RTFM

10.7 done

## zip/unzip 介绍

集打包和压缩一体的工具

### 示例

```text
zip -r a.zip src_code           # 打包压缩目录及目录下文件
unzip a.zip                     # 解压
```
### RTFM



## References

