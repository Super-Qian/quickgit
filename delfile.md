## 删除文件

当文件已经提交到版本库，并且在工作区被删除时，可以使用`git status`，返回信息中会有一句`deleted:	filename`，表明是哪个文件被删除啦，此时可以有两种操作选择：
1. 确实要从版本库中删除该文件，用命令`git rm filename`，然后`git commit -m "comment"`提交修改
2. 属于误删，使用`git check -- filename`命令，(只能)把误删的文件恢复到和版本库一样