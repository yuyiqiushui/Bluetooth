Git is a version control system.
Git is free software.
mkdir learngit

1、创建文件
cd learngit
2、查看当前目录
pwd
3、添加到reposive
git add filename
4、提交到reposity
git commit -m "filename"
5、查看状态
git status
6、查看不同
git diff

7、查看log信息
git log
8、 回退版本
git reset  --hard HEAD^
9、前进到哪一个版本
git reset --hard commit id
10、查看commit id
git reflog

11、git暂存区
12、管理和修改
只有git add添加到暂存区的可以commit到master
13、撤销修改
	git暂存区
	git checkout -- readme.txt
	git reset HEAD readme.txt
	
	场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

	场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

	场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。


