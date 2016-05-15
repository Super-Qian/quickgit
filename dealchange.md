## 管理修改

从前的章节中可以看出，文件在工作区，由人进行管理，而不是Git，Git负责跟踪管理的是修改。

加入对一个文件进行如下操作：

`修改`—>`git add filename`—>`再修改`—>`git commit -m "comment"`

然后再执行`git status`后，提示信息中会有`modified: filename`，表示`filename`文件修改但并没有提交。这是因为Git管理的是修改(再次强调)，当用`git add`命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，`git commit`只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。也就是说，每次修改，如果不`git add filename`到暂存区，那么`git commit -m "comment"`就不会提交到版本库。