
# vimdiff

## 介绍

是vim的软链, 用于处理多个文件的差异，可用于git或svn处理版本冲突

## git使用

通过buffers查看各个窗口编号，默认 1 LOCAL INDEX 当前版本，2 为Merge的两个版本的共同源头版本，3为远端合并版本，4为git 尝试合并的版本，同时显示冲突

处理流程与命令: 

- `]c` 下一个冲突
- `[c` 上一个冲突
- `:diffget $num` 获取第几个窗口的变更
- `:wqa` 保存退出

## References

- http://vim.wikia.com/wiki/A_better_Vimdiff_Git_mergetool
- https://www.rosipov.com/blog/use-vimdiff-as-git-mergetool/
- https://yodalee.blogspot.com/2013/03/vimdiffgit-merge-conflict_28.html

