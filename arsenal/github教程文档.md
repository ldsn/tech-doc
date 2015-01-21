
###－－－－－－－－－－－－－第一课－－－－－－－－－－－－－－－

git 是什么 可以做什么？

	版本管理工具，可以管理你代码的版本

	基于git的代码托管平台：github.com、git.oschina.com

git 使用方法

	教程地址：
		http://my.oschina.net/dxqr/blog/134811
		http://rogerdudler.github.io/git-guide/index.zh.html
	windows操作系统下需要安装 git for windows （git的命令行）
		下载地址：http://msysgit.github.io/

安装好以后 就可以在终端使用git了。

在大家都有github账号的情况下

打开你的 git bash

第一步：在初始化
		git config --global
		
		git config --global user.name 'edire'
		git config --global user.name 'user.email'

第二步：配置ssh-key 这是github上传的凭证

		ssh-keygen
		cat ~/.ssh/id-rsa.pub
		把这串字符放到github的设置里面

测试： ssh -T git@github.com

###－－－－－－－－－－－－－－第二课－－－－－－－－－－－－－－

第三步：与远程库连接

		git clone git@github.com:username/repository.git
		git remote add origin git@github.com:username/repository.git
		git remote add others git@github.com:username/repository.git

第四步：拉取代码
		git pull origin develop

		git fetch origin develop

第五步：修改代码
		
		git diff 
		类似功能软件 beyond compare

第六步：提交代码
		git push

		git push origin master
		git push origin develop

###－－－－－－－－－－－－－－第三课－－－－－－－－－－－－－

分支：
	git branch

	本地新建当前分支的分支
	git branch name
	重命名
	git branch -m newname
	删除
	git branch -d name

	切换分支
	git checkout name

	创建并进入分支
	git checkout -b name master


###－－－－－－－－－－－－－－第四课－－－－－－－－－－－－－

推送代码到线上：
	git push

	推送当前分支代码到线上某库
	git push origin master

	推送本地某分支代码到线上某分支
	git push origin aaa:master

	删除线上主干
	git push origin :master

###－－－－－－－－－－－－－－第五课－－－－－－－－－－－－－

merge 合并代码：
	
	git merge 
 	把B分支合并到A分支。
		git checkout A
		git merge B
