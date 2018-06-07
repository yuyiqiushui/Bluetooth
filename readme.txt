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
20、future分支
21、多人协作
	在本地创建和远程分支同样分支
	git checkout -b branchname origin/branchname
	1、多人协作
		首先，可以试图用git push origin <branch-name>推送自己的修改；

		如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

		如果合并有冲突，则解决冲突，并在本地提交；

		没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！

		如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream-to <branch-name> origin/<branch-name>。
	2、小结：
		查看远程库信息，使用git remote -v；

		本地新建的分支如果不推送到远程，对其他人就是不可见的；

		从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

		在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

		建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；

		从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

21、标签管理
	小结：
		命令git tag tagname 用于新建一个标签，默认为HEAD,也可以指定一个commit id;
		
		命令git tag -a tagname -m "信息注释blabla..."可以指定标签信息;
		
		命令git tag 可以查看所有标签
	操作标签：
	小结：
		命令git push origin tagname可以推送一个本地标签
		
		命令git push origin --tags可以推送全部未推送过的本地标签
		
		命令git tag -d tagname可以删除一个本地标签

		命令git push origin :refs/tags/tagname可以删除一个远程标签