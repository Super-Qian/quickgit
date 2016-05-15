## 分支创建与切换

还记得[版本回退](./back.md)里的`HEAD`指针吗，这个`HEAD`指针实际上是指向当前分支，当新创建一个分支时，实际上是新创建了一个指针，当切换到新分支时，实际上只是将`HEAD`指针指向了这个新分支。所以说切换速度是及其快的。

创建分支使用命令：
```
git branch newbranch
```

切换到新分支：
```
git checkout newbranch
```

注意：和[撤销修改](./delchange.md)的不同，`checkout`后没有`--`

创建并切换到新分支：
```
git checkout -b newbranch
```

查看当前分支使用：
```
git branch
```

`git branch`命令会列出所有分支，当前分支前面会标一个`*`号

然后就可以在`newbranch`分支上正常提交，工作完成后再`git checkout master`切换到`master`分支即可，不过在`newbranch`提交的内容不会出现在`master`上，因为还没有[合并分支](./mergebranch.md)