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

### Wrapping Up
1. `git checkout .` 会取消所有本地工作区修改，应该不轻易使用。如果希望抛弃本地工作区的某个文件的修改，可以使用`git checkout filename`
2. `git commit -a`命令应避免使用。所有的操作应该遵循权限最小化的原则。
3. 对于checkout和diff命令，如果不指明HEAD，都是默认缓存区和工作区之间的操作。
4. 冲突的出现是在不同分支合并或多人协作开发同一分支时遇到的。
5. rebase命令为了保持分支的开发和主分支的开发紧密相连。避免出现分支的开发与主分支脱节的情况。
6. `git stash`命令用来保存当前分工作区的修改。因为切换分支的前提的Nothing to be committed。
7. `git push`命令会把本地版本库推送到远端版本库。默认会推送到Origin，如果希望可以默认推送到其他位置，可以在推送时使用`-u`参数。
8. `git reset`命令会使缓存区与HEAD保持一致。`--hard`参数会使工作区、缓存区和HEAD保持一致。
9. 克隆的版本库只有一个主分支，但是所有的分支是保存着的。可以使用`git branch -r`来查看。想使用别的远程分支可以`git branch your_branch repo_branch`来创建分支。

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

### 参考资料

1. [Ruby开发推荐的插件](http://ruby-china.org/wiki/tools)
2. [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)
