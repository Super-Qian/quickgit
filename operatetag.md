## 标签管理

标签打错时使用`git tag -d tagname`删除标签：
```
git tag -d v1.0
```

使用`git push origin tagname`推送某个标签到远程：
```
git push origin v1.0
```

一次性把本地所有标签推送远程：
```
git push origin --tags
```

删除远程标签：
```
git tag -d v1.0
git push origin :refs/tags/v1.0
```