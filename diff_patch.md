
# diff/patch 

## diff介绍

逐行比较两个文件或者目录

### 示例

```text
diff test1 test2             # 正常模式输出
diff -ruN test1 test2        # 统一格式输出
```

#### normal mode

    [root@centos test]# diff test1 test2
    1a2
    > one
    7c8,10
    < over
    ---
    > two
    > fail
    > over game
    9d11
    < that

默认为normal模式，有三个提示分别为

- a: append
- c: change
- d: delete

#### unify mode

    [root@VM test]# diff -u test1 test2
    --- test1    2018-10-05 22:15:15.852942594 +0800
    +++ tett2    2018-10-05 22:44:59.253295846 +0800
    @@ -1,9 +1,11 @@
     hello
    +one
     world
     nice
     neet
     you
     good
    -over
    +two
    +fail
    +over game
     night
    -that

#### context mode


    [root@VM_0_8_centos bar]# diff -c  d1/b.txt d2/b.txt
    *** d1/b.txt    2018-10-06 20:46:52.248869354 +0800
    --- d2/b.txt    2018-10-06 20:39:12.077813033 +0800
    ***************
    *** 1,2 ****
    ! hello
      world
    --- 1,3 ----
    ! hellk
      world
    + new

### RTFM

10.5 done

## patch

利用文件差异进行打补丁

### 示例

```text
patch test.txt test.patch       # 将补丁文件test.patch 打到test.txt上
patch -o tmp.output.txt test.txt test.patch     # -o 表示输出到新文件，而不是in-place模式
patch -p0 <all.patch            # -p 表示patch文件中的路径是否需要剥离(strip), 此处为0表示不用剥离，
                                # 若没有-p命令将剥离所有目录，只保留文件名，即在当前目录查找需要打补丁的文件
```

### RTFM

10.6 7%

## References

- http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html
- https://www.ibm.com/support/knowledgecenter/zh/ssw_aix_71/com.ibm.aix.cmds4/patch.htm
- https://www.ibm.com/support/knowledgecenter/zh/ssw_aix_71/com.ibm.aix.cmds2/diff.htm

