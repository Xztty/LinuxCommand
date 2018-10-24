
# useradd/passwd/usermod

## useradd介绍

创建用户和更新新用户配置

### 常用示例

```text
useradd testuser
useradd -c "this is a testuser" testuser
useradd -s /bin/sh testuser                 # 指定shell
```

### RTFM

10.1 done

## passwd

管理用户密码，支持过期，密码有效时间

### 常用示例

```text
passwd                                  # 更新读取用户密码
passwd testuser                         # 为testuser设置密码
echo -n "newpassword" | passwd --stdin  # 允许从stdin读取密码，从而允许pipe
passwd -e                               # 使密码过期
passwd -d testuser                      # 删除密码
```

### RTFM

9.29 done

## usermod

管理用户基本信息：所在组、密码有效时间、目录、组id、用户id等

### 常用示例

```text
usermod -G wheel testuser               # 将用户加入wheel组
usermod -l newusername oldusername      # 修改用户名
usermod -L testuser                     # 锁定用户
usermod -U testuser                     # 解锁用户
```

### RTFM

10.13 done

## References

