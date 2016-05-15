## 版本回退

在[上一章节](./contral.md)中，说到如何将修改后的文件添加并提交到Git仓库。可以对文件重复此过程，直到修改满意为止。但是这个过程只是在前进，有时我们会觉得最后的一次修改不如前面的修改，这就需要版本回退啦。

首先使用`git log`命令，显示从最近到最远的提交日志如下面：
```
commit 3ae580414096344504a8b45438ae86daf796889b
Author: Super-Qian <weiczhilian@gmail.com>
Date:   Tue Mar 22 17:24:10 2016 +0800

    add counting sort

commit 8232e2fbf0aa5c52887640f2f10eb37b75e7ce74
Author: Super-Qian <weiczhilian@gmail.com>
Date:   Tue Mar 22 16:32:55 2016 +0800

    change some file

commit 69ee5180b978eff6bee6ad3b1795d34d3de3b323
Author: Super-Qian <weiczhilian@gmail.com>
Date:   Tue Mar 22 16:16:21 2016 +0800

    add quick sort
```

也可以使用`git log --pretty=oneline`，让这些信息显示为一行:
```
3ae580414096344504a8b45438ae86daf796889b add counting sort
8232e2fbf0aa5c52887640f2f10eb37b75e7ce74 change some file
69ee5180b978eff6bee6ad3b1795d34d3de3b323 add quick sort
```
或者使用`git log --graph`图形化显示

对于每次提交都会显示出来，并且在每次提交记录后面都有提交时的`comment`，找到想回到的那个版本，然后使用`git reset --hard commit_id`即可，`commit_id`就是`git log`中的那一串字符，只用开头的几个就行，不必全写。另外一种方法是不用`commit_id`，使用`HEAD`指针，例如回到上一个版本使用`git reset --hard HEAD^`，上上一个版本就是`git reset --hard HEAD^^`，依此类推，往上100个版本可以写成`git reset --hard HEAD~100`。

还有就是当回退到某个版本后，就无法找到此版本后面版本的`commit_id`的，就像你不能知道未来的事一样，不过在Git中就不一样啦，使用`git reflog`命令考验查看每一次的操作：
```
69ee518 HEAD@{0}: reset: moving to 69ee518
8232e2f HEAD@{1}: reset: moving to 8232e2
3ae5804 HEAD@{2}: commit: add counting sort
```

这样就可以再使用`git reset --hard commit_id`命令回到想回到的版本啦。