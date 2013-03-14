Learn to Use Git&Vim
====================

Git是一个开源的分布式版本控制系统，是Linus Torvalds为了帮助管理Linux内核开发而开发的一个开放源码的版本控制系统。
Github是当前最知名的远程版本库，上面托管了很多有名的repos。

## Git参考

可供参考的资料非常多:

* git手册：`man git`
* git快速参考: `git -h`
* [Git Reference](http://gitref.org)
* [Pro Git](https://github.com/progit/progit)
* *[My Git Workflow](http://osteele.com/posts/2008/05/my-git-workflow)*

### Wrapping Up 16条

1. `git checkout .` 会取消所有本地工作区修改，应该不轻易使用。如果希望抛弃本地工作区的某个文件的修改，可以使用`git checkout filename`
2. `git commit -a`命令应避免使用。所有的操作应该遵循权限最小化的原则。
3. 对于checkout和diff命令，如果不指明HEAD，都是默认缓存区和工作区之间的操作。
4. 冲突的出现是在不同分支合并或多人协作开发同一分支时遇到的。
5. rebase命令为了保持分支的开发和主分支的开发紧密相连。避免出现分支的开发与主分支脱节的情况。
6. `git stash`命令用来保存当前分工作区的修改。因为切换分支的前提的Nothing to be committed。
7. `git push`命令会把本地版本库推送到远端版本库。默认会推送到Origin，如果希望可以默认推送到其他位置，可以在推送时使用`-u`参数。
8. `git reset`命令会使缓存区与HEAD保持一致。`--hard`参数会使工作区、缓存区和HEAD保持一致。
9. 克隆的版本库只有一个主分支，但是所有的分支是保存着的。可以使用`git branch -r`来查看。想使用别的远程分支可以`git branch your_branch repo_branch`来创建分支。
10. 关于revert和reset的区别。reset到之前的某个分支会是之后的信息丢弃。而revert则不会，它会保留记录，继续向前。
11. 关于合并。 把new_features分支合并到master中，master便拥有了两个分支的所有commits记录。master可以reset到任何一个commit状态。
12. `git log -p -2` 显示差异，最近两条。
13. `git commit --amend`，重新提交。和上次提交为一个提交。
14. `git pull` == `git fetch | git merge origin/branch`。 如果只写了master，无法合并。
15. 设置分支跟踪远端分支，git branch --set-upstream your_branch origin/branch
16. git reflog的会显示gco的操作。HEAD的操作都会显示在该命令中，所以git commit的message非常重要。初创分支跟踪可以参考第9条
17. 可以才有工作区的远程分支克隆版本库，但是推送，只可以面向裸库

### git考核的内容

1. clone的使用，创建裸库。（首先创造一个多人工作的环境）
2. 一次提交，补充提交
3. 创建分支
4. 分支合并中的冲突制造和解决。
5. 2号版本库的操作：创建分支，跟踪分支。
6. git fetch / git pull
7. git push
8. git reset,恢复到某一状态
9. checkout out 

### 关于配置

1. 如果你的github帐号绑定了多个邮箱,可以在库中单独配置。
	
	> 比如我全局配置使用的自己的帐号。在公司的版本库中单独使用公司的email。

2. Color: auto就好。
3. ssh: 照着github help做即可。

## git-flow

### 安装:

	sudo apt-get install git-flow

### 参考资料

* [gitflow开发流程](http://ihower.tw/blog/archives/5140)
* [Github/gitflow](https://github.com/nvie/gitflow)

### Wrapping Up

1. 使用oh-my-zsh的好处就是可以使用git-flow插件，可以很快速的补全命令。
2. 对于develop和master分支，任何的修改添加是不允许在之上进行操作的。
3. 新的功能和修改在feature分支。准备发布的版本使用Release分支进行最后debug。发行后出现的bug在hotfix分支中进行修改，完成之后会自动合并到master和develop中。

## vim

小白遇到vim会很发愁。的确vim的学习曲线挺陡的，但是熟悉之后便是坦途。

第一个问题自然是配置文件了。可以从网上找到高手的配置文件拿下来使用，尽管很多地方会不明白。这是一条很好的进阶之路。

插件的使用，可以安装pathogen插件来管理插件（见Installation_Configuration.md）。

### Wrapping Up

1. 全文查找替换`:g/find/s//replace/g`

### 参考资料

1. [Ruby开发推荐的插件](http://ruby-china.org/wiki/tools)
2. [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)
