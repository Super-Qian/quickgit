## 多人协作

我们在[克隆远程库](./clonerepo.md)章节中进行远程仓库克隆时，Git会自动把本地的`master`分支和远程的`master`分支对应起来了，并且远程仓库的默认名称是`origin`。

要查看远程库的信息，使用：
```
git remote
```

如果有推送权限，可以使用下面的命令查看push的地址：
```
git remote -v
```

输出如下：
```
origin	git@github.com:Super-Qian/algorism_with_python.git (fetch)
origin	git@github.com:Super-Qian/algorism_with_python.git (push)
```