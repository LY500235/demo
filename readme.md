# git使用
#1、创建一个git的本地仓库

	git mkdir git_demo
	cd  git_demo 
	git init
	# 查看状态	
	git status
在github 上面创建一个仓库关联本地仓库和github
	
	git remote add origin ssh地址
    (例：git remote add origin git@github.com:LY500235/demo.git）

在主分支（master）上面修改内容后， 需要经过三部提交到github上面

	git add .
	git commit -m "提交的注释"
	git push -u origin master
这样就提交到 github 上面了

#2 、git分支

	通常情况下，当我们需要添加一个新功能的时候，我们不能再主线程上添加修改， 需要新建一个分支来修改。好处： 可以及时的回滚代码。
	# 新建分支
	git branch iss1
	# 切换工作区
	git checkout iss1
    (等价于 git checkout -b iss1)
	# 修改代码后添加修改到本地
	git add .
	git commit -m "注释"
	推送到远程 因为远程仓库还没有分支就需要添加 --set0-upstream
	git push --set-upstream origin iss1

	功能iss1完成后，把修改部分合并到master,并删除iss1分支
     # 切换回主线程， 
	get checkout master
	合并分支 
	git merge iss1
	删除分支
	git branch -d iss1
	
	git push 
	
	git push origin:iss1

	
#3、解决冲突

	vim  file1
	
	<<<<<<HEAD
	fiel1  add
	======
	fiel + del 
	>>>>>>
	
	退出保存(:wq)
	git add 
	git commit
	git push
	推送到远程分支

