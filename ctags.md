
# ctags 

## 介绍

为源代码生成tag信息，方便vim等编辑器使用

## 示例

```text
ctags -R . 				# 当前目录生成ctags文件, vim直接打开目录下文件，就可以用到tag信息了
```

### 增加库函数

生成系统头文件tags, 放于 ~/.vim/systags 下 (达到50M+)

ctags --fields=+iaS --extra=+q -R -f ~/.vim/systags /usr/include /usr/local/include

~/.vimrc 增加tags

set tags+=~/.vim/systags                

### 结合vim使用

- :ta tagname                   	# 跳转到指定tagname

## RTFM

10.17 

## References

