## 搭建Git服务器

搭建Git服务器只需要能上网的Linux机器即可，同时还必须要有`sudo`权限。

操作步骤如下：

1. 安装Git，和[安装Git](./installgit.md)中Linux平台的操作一样

2. 创建一个git用户，用来运行git服务：
	```
	sudo adduser git
	```

3. 创建证书登录：收集所有需要登录的用户的公钥，也就是他们的id_rsa.pub文件，把这些公钥都导入到`/home/git/.ssh/authorized_keys`文件里，一行一个

4. 初始化Git仓库：选定一个目录作为Git仓库，以`/test/sample.git`为例，在`/test`目录下输入命令：
	```
	sudo git init --bare sample.git
	```

	Git会创建一个没有工作区的裸仓库，服务器上的Git仓库通常都以`.git`结尾

5. 修改属主，把owner改为git：
	```
	sudo chown -R git:git sample.git
	```

6. 禁用shell登录：让第二步中创建的git用户不允许登录shell，在`/etc/passwd`文件中找到类似下面的一行：
	```
	git:x:1001:1001:,,,:/home/git:/bin/bash
	```

	改为：
	```
	git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell
	```

	这样，用户`git`可以正常通过ssh使用git，但无法登录shell

7. 克隆远程仓库：
	```
	git clone git@server:/test/sample.git
	```

	其中`server`是主机名，这样就克隆了远程仓库，可以在各自的电脑上运行啦