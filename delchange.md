## 撤销修改

#### `git add filename`之前

如果只是在工作区修改了`filename`文件，这时使用`git check -- filename`，把工作区变成和版本库一样。

注意：和[分支创建与切换](./createbranch.md)的不同，`checkout`后必须要有`--`

#### `git add filename`之后，`git commit -m "comment"`之前

如果在`git add filename`之后，`git commit -m "comment"`之前又对`filename`进行了修改，那么

1. 使用`git check -- filename`，把修改撤销，回到添加到暂存区后的状态
2. 使用`git reset HEAD filename`把暂存区的修改撤销掉，重新放回工作区，然后使用`git check -- filename`，把工作区变成和版本库一样

注意：和[分支创建与切换](./createbranch.md)的不同，`checkout`后必须要有`--`

#### `git commit -m "comment"`之后

参考[版本回退](./back.md)章节