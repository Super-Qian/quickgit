## 版本控制

`git status`命令可以让我们随时掌握工作区(参考[工作区与版本库](./direction.md)章节)的状态。

如果`git status`提示有文件被修改过，可以用`git diff`可以查看修改内容。

例如我们对已经添加并提交到仓库的`filename`文件进行了修改，这时使用`git status`命令，提示信息中会有一句`modified: filename`，表示`filename`文件已经被修改但是没有添加并提交到仓库，这时使用`git diff filename`命令就会显示被修改过的内容啦。如果确认修改正确，再使用`git add filename`和`git commit -m "comment"`命令将修改后的文件添加并提交到仓库，这时再使用`git status`，提示信息为`nothing to commit (working directory clean)`表示工作区没有需要提交的文件。如果还有需要提交的文件，重复此过程即可。
