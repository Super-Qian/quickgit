## 分支冲突

如果我们在`newbranch`分支上修改并提交了`filename`文件，切换到`master`分支后，又对`filename`进行了修改和提交，这时如果合并分支，就会出现分支冲突，导致合并失败，此时使用`git status`命令，返回信息中会有一句类似与`both modified:	filename`的信息，这时可以直接查看`filename`文件，会发现如下形式：
```
This is a test file
hello
<<<<<<< HEAD
world
=======
git
>>>>>>> feature1
```

Git用`<<<<<<<`，`=======`，`>>>>>>>`标记出不同分支的内容，需要手动修改后再执行：
1. `git add filename`
2. `git commit -m "comment"`
3. `git merge newbranch`

最后删除`newbranch`分支即可