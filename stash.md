## 使用Stash

假如你正在`newbranch`分支工作，由于工作尚未完成，不能提交，但是因为某种紧急原因，例如修复一个Bug，必须创建另外一个分支进行一些临时工作，这时就要用`stash`啦。

具体操作如下：

1. 在你工作尚未完成的`newbranch`分支中使用
	```
	git stash
	```

	这时可以使用`git status`，显示工作区空白(clear)

2. 切换到将来需要把临时分支合并到上面来的分支，以`master`主分支为例：
	```
	git checkout master
	```

3. 创建并切换到临时分支
	```
	git checkout -b temp
	```

4. 这时候就可以在`temp`临时分支上进行紧急工作啦，工作完成后，使用`git add filename`和`git commit -m "comment"`将所做的工作提交，临时工作完成

5. 切换到需要把临时分支合并到上面来的分支，这里是`master`主分支
	```
	git checkout master
	```

6. 将临时分支合并
	```
	git merge temp
	```

7. 删除临时分支
	```
	git branch -d temp
	```

8. 切换到工作尚未完成的`newbranch`分支
	```
	git checkout newbranch
	```

9. 此时使用`git status`，仍然会显示工作区空白(clear)，使用`git stash list`查看`stash`列表：
	```
	stash@{0}: WIP on newbranch: 5223874 add merge
	```

	因为这里只进行了一次`git stash`操作，所以只有一项内容。

10. 接下来是回复工作区继续之前的工作，方法有两个：

	**a.** 使用`git stash apply stash@{num}`，`num`就是上面列表中你要恢复的编号，这样恢复后，`stash`内容并不删除，需要用`git stash drop`来删除

	**b.** 使用`git stash pop`命令，这条命令恢复的是`stash`列表中最上层的那个编号，同时把对应的`stash`在列表中删除