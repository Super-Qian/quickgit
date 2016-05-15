## 关联远程库

如果已经在本地创建了一个Git仓库，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以和其他人通过该仓库协作。

具体步骤：

1. 登陆GitHub，然后，在右上角找到`Create a new repo`按钮，创建一个新的仓库
2. 在`Repository name`填入任意仓库名，以`reponame`为例，其他保持默认设置，点击`Create repository`按钮，就成功地创建了一个新的Git仓库
3. 在本地你想关联的目录下执行：
	```
	git remote add origin git@github.com:yourid/repo.git
	```

	其中，`yourid`是你GitHub的ID，`repo`是你在GitHub上建立的远程库名，添加后，远程库的名字是Git默认的`origin`
4. 将本地仓库的内容推送到远程库上：
	```
	git push -u origin master
	```

	第一次推送master分支时，加上`-u`参数，这样Git不但会把本地的master分支内容推送的远程master分支，还会把本地的master分支和远程的master分支关联起来，以后推送时就可以不会加`-u`啦

#### SSH警告

当第一次使用Git的clone或者push命令连接GitHub时，会得到一个警告：
```
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
```

这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入yes回车即可。

这时会出现一个Warning，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：
```
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.
```

这个警告只会出现一次，后面的操作就不会有任何警告了。