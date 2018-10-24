
# whoami/id/logname 

## whoami

查看当前Effective Uid

### 示例

```text
whoami
```

### RTFM

10.6 done


## id介绍

显示真实、有效的用户id和组id

### 示例

```text
id
id testuser                 # 查看指定用户
id -un                      # 同whoami一样，显示有效用户名(effective user name)
id -gn                      # 显示有效组名(effective group name)
id -Gn                      # 查看附加组名
id -urn                     # 查看real user name
id -grn                     # 查看real group name              
id -Grn
```

### RTFM

10.6 done

## logname介绍

显示初始登录的用户名，不会随着su切换而改变

### 示例

```text
logname
```

### RTFM

10.6 done

## References

- http://poincare.matf.bg.ac.rs/~ivana/courses/ps/sistemi_knjige/pomocno/apue/APUE/0201433079/ch08lev1sec11.html
- APUE 8.11 Changing User IDs and Group IDs

