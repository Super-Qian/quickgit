## 配置Git

首先是配置用户名和用户邮箱
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
配置Git的时候，加上`--global`是针对当前用户起作用的，该用户的所有仓库都用此配置，如果不加，那只针对当前的仓库起作用。

当前用户的Git配置文件放在用户主目录下的一个隐藏文件`.gitconfig`中；而每个仓库的Git配置文件都放在该仓库下`.git/config`文件中。

另外是一些常用命令的别名，使用别名可以节约时间，因为只需要输入几个字母就能代表一个命令，Git别名配置格式：
```
git config --global alias.别名  真正的命令
```

例如用`git st`代替`git status`的别名配置如下：
```
$ git config --global alias.st status
```

下面这些都是常用命令的别名配置：
```
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch
$ git config --global alias.st status
```