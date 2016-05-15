## 抓取分支

多人协作时，大家都会往`master`主分支和开发分支上推送各自的修改，就会造成推送失败，这时就需要抓取分支啦

当有人从远程库`clone`时，默认情况下，他只能看到本地的`master`分支，当他需要在开发分支(以`newbranch`为例)上开发时，就必须创建远程`origin`的开发分支`newbranch`到本地，命令如下：
```
git checkout -b newbranch origin/newbranch
```

现在，他就可以在`newbranch`上工作，然后把`newbranch`分支`push`到远程：
```
git add filename
git commit -m "comment"
git push origin newbranch
```

当他完成这些后，如果你也对`newbranch`分支上的`filename`文件做了修改，并进行推送：
```
git add filename
git commit -m "comment"
git push origin newbranch
```

这时返回信息中会有类似下面的语句：
```
 ! [rejected]        newbranch -> newbranch (non-fast-forward)
error: failed to push some refs to 'git@github.com:yourid/sample.git'
hint: Updates were rejected because the tip of your current branch is behind
```

说明你的推送失败，因为其他人的最新提交和你推送的提交有冲突

这时应该先用`git pull`把最新的提交从origin/dev抓下来：
```
git pull
```

如果返回信息中有：
```
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
```

说明`git pull`失败，原因是没有指定本地`newbranch`分支与远程`origin/newbranch`分支的链接，这时需要设置`newbranch`分支和远程`origin/newbranch`分支的链接：
```
git branch --set-upstream newbranch origin/newbranch
```

然后再执行：
```
git pull
```

如果返回信息中有：
```
CONFLICT (content): Merge conflict in filename
Automatic merge failed; fix conflicts and then commit the result.
```

说明`git pull`成功，但是合并有冲突，需要手动解决，解决的方法和[分支冲突](./confliction.md)中的解决冲突完全一样。解决后，提交，再push即可：
```
git commit -m "comment"
git push origin newbranch
```