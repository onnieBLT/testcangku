###### 这是一个测试的readme文件 测试windows 下的git使用。

```
Workspace：工作区
Index / Stage：暂存区
Repository：仓库区（或本地仓库）
Remote：远程仓库
```
1. 允许该目录使用#git#管理(文件中的.git 文件夹请勿胡乱修改)
	`git init`

2. 把命令推到暂存区 
	`git add readme.md`
	`git add 1.txt 2.txt 3.txt`可以提交多个文件到暂存区，按空格分隔

3. 把文件推送到本地仓库
	`git commit -m "本次修改了xxxxx"

4. git status 可以用来查看是否有没推到仓库的 文件或者修改未提交的内容