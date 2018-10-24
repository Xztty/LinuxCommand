
# su/sudo 

## su

以其他用户/用户组执行命令

### 示例

```text
su -               # 默认切换到root，只保留TERM 环境变量
su - test          # 切换到test用户
su - test ls /     #
```

### RTFM

9.21 done


## sudo/visudo

sudo 用其他身份执行命令，一般为root

visudo 用于编辑sudoers文件，可以防止编辑冲突

### 示例

```text
sudo yum install -y gcc
visudo
```

### /etc/sudosers

默认的sudoers文件位置, 可以配置用户使用sudo可以执行的命令/host等信息。使用visudo修改后，会验证有效性，修改成功立即生效。

- `%wheel  ALL=(ALL)       NOPASSWD: ALL`                       # wheel 用户组无需密码
- `%wheel        ALL=(ALL)       ALL`                           # wheel 用户组sudo时需要密码
- `testuser        ALL=(ALL)       ALL`                         # privilege user 需要重新输入用户密码
- `testuser        ALL=(ALL)       NOPASSWD: ALL`               # 无需输入用户密码，即可执行命令

### RTFM

10.12 done 

## References

