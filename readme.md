###### 这是一个测试的readme文件 测试windows 下的git使用。

```
Workspace：工作区
Index / Stage：暂存区
Repository：仓库区（或本地仓库）
Remote：远程仓库
```
### 把文件添加到版本库
	1. 允许该目录使用#git#管理(文件中的.git 文件夹请勿胡乱修改)
	`git init`

	2. 把命令推到暂存区 
	`git add readme.md`
	`git add 1.txt 2.txt 3.txt`可以提交多个文件到暂存区，按空格分隔

	3. 把文件推送到本地仓库
	`git commit -m` "本次修改了xxxxx"
### 仓库状态
	4. 查看是否有没推到仓库的 文件或者修改未提交的内容
	`git status` 可以用来查看是否是否存在变更内容
	`git diff readme.md` 用来查看具体的变更内容
### 版本退回
	5. 在实际工作中，我们脑子里怎么可能记得一个几千行的文件每次都改了什么内容，不然要版本控制系统干什么。版本控制系统肯定有某个命令可以告诉我们历史记录，在Git中，我们用git log命令查看：
	`git log`
	git log命令显示从最近到最远的提交日志。如果嫌输出信息太多，看得眼花缭乱的，可以试试加上--pretty=oneline参数：
	`git log --pretty=oneline`

	6. 需要友情提示的是，你看到的一大串类似2e70fd...376315的是commit id（版本号）

	在 Git中，用HEAD表示当前版本，也就是最新的提交commit id，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。

	现在我们要把当前版本回退到上一个版本，就可以使用git reset命令：
	`git reset --hard HEAD^`
	
	然我们用git log再看看现在版本库的状态，最新的那个版本已经看不到了！好比你从21世纪坐时光穿梭机来到了19世纪，想再回去已经回不去了，肿么办？
	办法其实还是有的，只要上面的命令行窗口还没有被关掉，你就可以顺着往上找啊找啊，假设找到那个commit id是2e70fdf...，于是就可以指定回到未来的某个版本：
	`git reset --hard 2e70fdf`
	
	现在，你回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本怎么办？找不到新版本的commit id怎么办？

	Git提供了一个命令git reflog用来记录你的每一次命令：
	`git reflog`
	