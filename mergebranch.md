## 分支合并与删除

合并分支使用：
```
git merge newbranch
```

`git merge`命令会将指定分支合并到当前分支。

合并分支时，如果可能，Git会用`Fast forward`模式，这种模式下，删除分支后会丢掉分支信息。加上`--no-ff`参数就可以用普通模式合并，这时Git会在`merge`时生成一个新的`commit`，这样从分支历史上就可以看出分支信息

合并完成后，删除分支使用：
```
git branch -d newbranch
```

如果没有合并就想删除分支的话，强制删除使用：
```
git branch -D newbranch
```

删除后，使用`git branch`命令查看，就只剩下master分支啦