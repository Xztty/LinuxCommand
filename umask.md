
# umask 

## 介绍

设置文件权限掩码

## 示例

```text
umask              # 查看当前掩码
umask -S           # 以symbolic形式显示当前掩码
umask 002          # 设置文件权限为 664
umask u=rw,g=r,o=  # owner可以读写, group可以读，other不能读写 注意这里使用symbolic时不是掩码含义
umask g+w          # group 增加write权限
```

注：umask在文件的原有file mode bit上做减法，并不是指定文件的file mode bit，如：`touch a` 文件可以看到没有execute 权限
具体参考[这里][1]

## RTFM

10.1 done

## References

- [why-doesnt-umask-change-execute-permissions-on-files][1]

[1]: https://unix.stackexchange.com/questions/287278/why-doesnt-umask-change-execute-permissions-on-files