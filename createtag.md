## 标签创建

在Git中打标签非常简单，步骤如下：

1. 切换到需要打标签的分支上(以`master`主分支为例)：
	```
	git checkout master
	```

2. 使用`git tag <tagname>`打一个新标签，如：
	```
	git tag v1.0
	```

3. 查看所有标签：
	```
	git tag
	```

4. 默认标签是打在最新提交的`commit`上的，如果想在以前的`commit`上打标签，先查看提交历史：
	```
	git log --pretty=oneline --abbrev-commit
	```

	输出如下：
	```
	48acf4d change quick_sort_cookbook
	0f85073 change quick_sort_cookbook
	3ae5804 add counting sort
	8232e2f change some file
	69ee518 add quick sort
	```

	找到想打标签的`commit id`，这里以第四个`change some file`为例，使用：
	```
	git tag v0.7 8232e2f
	```

另外，还可以创建带有说明的标签，用`-a`指定标签名，`-m`指定说明文字：
```
git tag -a v0.8 -m "version 0.8" 3ae5804
```

需要注意的是，使用`git tag`后，标签不是按时间顺序列出，而是按字母排序的。可以用`git show <tagname>`查看标签信息：
```
git show v1.0
```

输出如下：
```
tag v1.0
Tagger: Super-Qian <weiczhilian@gmail.com>
Date:   Sat May 14 14:27:13 2016 +0800
```