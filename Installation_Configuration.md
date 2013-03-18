环境的配置
==========

## vim

### 使用spf13.vim

### 安装Pathogen.vim

使用它可以轻松地安装各种插件。 
使用 `sudo apt-get install vim` 安装vim.
在shell中拷贝粘贴以下内容:

	mkdir -p ~/.vim/autoload ~/.vim/bundle; \
	curl -Sso ~/.vim/autoload/pathogen.vim \
			https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim

### 配置vimrc

打开vimrc，添加以下内容:

	execute pathogen#infect()

以后想安装的插件都可以解压到 `~/.vim/bundle` ,便可以使用

*zencoding*是一款快速写HTML的插件。只需执行以下代码:

	git clone http://github.com/mattn/zencoding-vim.git ~/.vim/bundle/zencoding

打开vim，输入 `html:5` , 再按`(Ctrl + y + ',')`，便自动生成html5框架代码。

此外，可以根据自己的需要添加一些配置到vimrc中，这个看个人需要。

## git&git-flow

在shell中输入 `sudo apt-get install git git-flow` 进行安装。

## rvm&ruby

具体内容和使用说明可以上RVM的官方网站[rvm.io](https://rvm.io)进行查阅

安装：

```shell
curl -L https://get.rvm.io | bash -s stable
```

安装完成之后选装安装自己使用的Ruby版本。我安装的是MRI 1.9.3。也就式Matz实现的版本。

```shell
rvm install 1.9.3
```

默认使用1.9.3版本:

```shell
rvm use 1.9.3
```

最后，为了使每次启动都可以使用rvm的命令，可以向 `~/.bashrc` 文件种添加以下代码:

```shell
source ~/.rvm/scripts/rvn
```

至此，环境的配置已经完成。
	
##Nginx

Nginx是一款非常强大的web服务器,经常被用来做反向代理服务器。同时它也是性能非常优秀的HTTP服务器。 
Nginx的安装非常简单。因为Ruby开发经常使用到Passenger的缘故，我们这里使用Passenger来安装Nginx。

```shell
$ gem install passenger
$ passenger-install-nginx-module
```

安装过程中会被询问nginx的安装路径，使用默认路径就可以了 `/opt/nginx`。

安装完成之后，将nginx命令程序链接到`/usr/sbin`

```shell
$ sudo ln -s /opt/nginx/sbin/nginx /usr/sbin/
```

## Node.js & CoffeeScript

Node.js是CommonJS的一种实现，他是一个建立在Chrome的JavaScript运行时之上的平台。
CoffeeScript的安装需要npm，npm的全称是Node Package Modules

### 安装

```shell
sudo apt-get install python-software-properties python g++ make
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs npm
sudo npm install -g coffee-script
```

npm的参数可以使用`npm -h`命令查看，在这里，`-g`代表全局环境。

## zsh&oh-my-zsh

使用`apt-get`来安装zsh。oh-my-zsh可以使用以下步骤安装: 

1. 克隆oh-my-zsh的版本库
	
	git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh

2. （可选）备份你之前的配置文件：`~/.zshrc`
	
	cp ~/.zshrc ~/.zshrc.orig

3. 使用oh-my-zsh的配置文件`~/.zshrc`
	
	cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

4. 将zsh设置为默认的shell:
	
	chsh -s /bin/zsh

5. 尽情享受zsh带给的快感。

### 插件和皮肤的设置

在Github上，oh-my-zsh的wiki中有可供使用的插件和皮肤。可以按需选择。

这里我使用了`sunrise`皮肤和`git`、`git-flow`、`rvm`和`ruby`插件。

打开`~/.zshrc`，如下设置:

	 ZSH_THEME="sunrise"

	 source $ZSH/oh-my-zsh.sh

### 参考

[Cheatsheet](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
