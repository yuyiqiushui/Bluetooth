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

14、添加远程库
git remote add origin git@github.com:yuyiqiushui/Bluetooth.git
git push -u origin master

15、从远程仓库克隆
git clone git@github.com:yuyiqiushui/Bluetooth.git

16、创建分支
gir checkout -b branchname  ==1、 git branch branchname   2、git checkout branchname
 
17、解决冲突
在先后两个分支修改内容，产生冲突后，手动更改，从新commit，合并分支


17、解决冲突
18、分支管理策略
19、Bug分支
首先存储当前分支
git stash
建立bug分支
git checkout -b issue-101
git add readme.txt
git commit --m "解决issue-101bug"
切换到主分支master
git branch master
合并分支
git merge --no-off --m "合并分支" issue-101
删除分支
git branch -d issue-101
恢复工作区
git stash list
git stash apply恢复
git stash drop删除内容
git stash pop恢复并删除
git stash apply stash@{0}
修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除
当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop,回到工作现场
