
# chmod/chown/chgrp

## chmod

改变文件的权限

### 常用示例

```text
chmod 644 a.sh
chmod u+x a.sh
chmod -R u+x ~/scripts/                # 目录下所有文件
chmod --reference=b.sh u+x a.sh        # copy b.sh的权限
```

symbolic representation 解释

    [ugoa...][[+-=][perms...]...], where perms is either zero or more letters from the set rwxXst, 
    or a single letter from the set [ugo]. (注：这里ugo分别表示user/group/other的权限)
    Multiple symbolic modes can be given, separated by commas.

perms 介绍

- r 可读
- w 可写
- x 可执行
- X 
- s 指set user or group 执行的权限
- t

### SETUID AND SETGID BITS

TO ADD

### RTFM

9.29 done

## chown

改变文件的owner和group

### 示例

```text
chown testuser a.sh
chown testuser:testgroup a.sh
chown -R testuser ~/scripts/
```
### RTFM

9.29 done

## chgrp

只改变group，其他同chown

### 示例

```text
chgrp staff /u
```

### RTFM

9.29 done

## References

