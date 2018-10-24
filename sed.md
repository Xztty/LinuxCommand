
# sed 

## 介绍

流编辑器，用于过滤和转换文本

## 示例

```text
sed -n '1,$p' text.txt                 # 原文打出来, 可以指定部分地址
sed -n '!1,3p' text.txt                # !对不匹配的地址执行命令
echo "a,b" | sed -e $'s/,/\\\n/g'      # 替换换行符的写法
sed -n '/Hi/,/Good bye/p' text.txt     # sed中的address可以使用regexp来指定，分别为第一个匹配的位置
sed -i 's/match_text/replacement_text/g'    text.txt   # in-place替换
sed -i "s/\${kafka_nodes}/192.186.1.1/g" text.txt      # 当时用"双引号时且替换文本中含有 $特殊字符，需要转义(其实是Bash层)，sed遵循GNU BRE，{/}等字符非特殊字符
sed -i "s~$var~replace~g" text.txt                     # 变量中含有 / 字符，可以使用其他最为语法分割符如 ~
sed 's/ AUTO_INCREMENT=[0-9]*\b//g' a.sql              # 删除mysqldump中的AUTO_INCREMENT
sed -i '/match_text/a\this is append text' text.txt    # 在匹配后增加一行内容
sed -i '/match_text/a this is append text' text.txt    # 在匹配后增加一行内容, 这里a命令后也可以使用空格
sed -i '/match_text/i\this is append text' text.txt    # 在匹配前增加一行内容
sed -i '/match_text/i this is append text' text.txt    # 在匹配前增加一行内容, 同a命令，使用空格
sed -i '/match_text/d' text.txt  或  sed -i '/match_text/c replace line'               '# 同样的还有c 替换行命令、d 删除命令
```

sed的scripts部分最好使用'(Single Quote)，避免有些符号bash进行特殊处理，如$/!等。

## address

`[address[,address]][!]{cmd}` 几乎上述所有的命令都是这样的（注：其中的!表示匹配成功后是否执行命令）

## PatternSpace & HoldSpace

PatternSpace: `sed reads one line from the input stream, removes any trailing newline, and places it in the pattern space.`, PatternSpace 在命令执行（scripts）完成后，如果有 无- n 选项的 Pattern Space的内容会大于到标准输出。

HoldSpace: 顾名思义 HoldSpace会在命令(scripts)执行周期继续保留的一块区域，可以使用 ‘h’, ‘H’, ‘x’, ‘g’, ‘G’ 将内容与 PatternSpace 进行移动。

具体如下：

- g： 将hold space中的内容拷贝到pattern space中，原来pattern space里的内容清除
- G： 将hold space中的内容append到pattern space\n后
- h： 将pattern space中的内容拷贝到hold space中，原来的hold space里的内容被清除
- H： 将pattern space中的内容append到hold space\n后
- x： 交换pattern space和hold space的内容

根据以上示例

```text
sed '1!G;h;$!d' t.txt      # 类似 tac 命令功能
```

## RTFM

10.7 done

## References

- https://coolshell.cn/articles/9104.html   SED 简明教程
- https://www.gnu.org/software/sed/manual/sed.html
