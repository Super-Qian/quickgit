## 克隆远程库

前一章节说的是在本地已有仓库的情况下关联远程库，如果想从零开发，那么最好的方式是先创建远程库，然后从远程库克隆。

具体步骤如下：

1. 和前一章节的1、2步相同，登陆GitHub，创建一个新的仓库，名字叫`repo`。然后勾选`Initialize this repository with a README`，这样GitHub会自动创建一个`README.md`文件，创建完毕后，可以看到README.md文件。
2. 克隆一个远程库，在本地执行：
	```
	git clone git@github.com:yourid/repo.git
	```
	其中，`yourid`是你GitHub的ID，`repo`是你在GitHub上建立的远程库名，然后本地会多了一个`repo`目录，进入后会看到`README.md`文件。另外，克隆时还可以用`https://github.com/yourid/repo.git`这样的地址，实际上Git支持多种协议，默认的`git://`使用ssh，但也可以使用https协议，只不过速度慢，而且每次推送都必须输入口令