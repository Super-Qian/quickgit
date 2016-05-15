## 使用GitHub

1. 进入[GitHub](./https://github.com/)网站，注册一个GitHub账号
2. 由于本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以需要设置SSH秘钥：在用户主目录下，如果有`.ssh`目录并且这个目录下有`id_rsa`和`id_rsa.pub`这两个文件，可直接跳到下一步。如果没有，打开Shell(Windows下打开Git Bash)，然后创建SSH Key：
	```
	ssh-keygen -t rsa -C "youremail"
	```

	其中，`youremail`是你的邮箱地址，然后一路回车，使用默认值即可，完成后可以在用户主目录里找到`.ssh`目录，里面有`id_rsa`和`id_rsa.pub`两个文件，这两个是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以告诉任何人。
3. 登陆GitHub，打开`Account settings`的`SSH Keys`页面，然后点`Add SSH Key`，填上任意Title，在Key文本框里复制粘贴你的`id_rsa.pub`文件里的内容，最后点`Add Key`，就可以看到已经添加的Key。

在GitHub上，可以任意Fork开源仓库，自己拥有Fork后的仓库的读写权限，并且可以推送pull request给官方仓库来贡献代码（不一定会接受你的代码）。

注：第一步是必须的，最后一段是想参加开源项目时所需要做的，不过你都有能力参与开源项目啦，估计Git早就玩的团团转啦，应该不会看这么low的东西。