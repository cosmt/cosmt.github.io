---
title: zssh介绍
---

### zssh
支持Zmodem文件传输，可以直接穿透跳板机，避免多次scp.
- 下载方式
```shell
sudo apt install zssh
```
使用方式和zssh完全一样，只是在ssh加入了用于文件传输的“管道”
可以在~/.bashrc直接定义别名替代ssh
```shell
#讲以下代码添加至.bashrc文件末尾
alias ssh=zssh
```
- 上传文件
	- step1: zssh 目标机器
	- step2: ctrl + space
	- step3: sz 需要发送的目标文件
- 下载文件
	- step1: ssh 目标机器
	- step2: sz 需要下载的文件
	- step3: ctrl + space
	- step4: rz

[详细介绍点击此处](https://www.cnblogs.com/pied/p/5813018.html)

- 定义别名之后tab不能自动补全的解决方法
	- bash
	```sehll
	cd /usr/share/bash-completion/completions/
	# 将ssh文件中的
	shopt -u hostcomplete && complete -F _ssh ssh slogin autossh sidedoor
	#改为以下内容
	shopt -u hostcomplete && complete -F _ssh zssh ssh slogin autossh sidedoor
	# 没有此文件的需要安装bash-completion
	sudo apt install bash-completion
	```
	想研究的朋友可以搜索学习下 bash-completion
	- zsh
	```shell
	compdef '_dispatch ssh ssh' zssh
	```
	[详细内容点击此处](https://stackoverflow.com/questions/4221239/zsh-use-completions-for-command-x-when-i-type-command-y)
- 另外使用zsh中使用incr时scp自动补全失效的解决方法如下
	注释incr-2.0.zsh文件中以下内容
	```
	# compdef -d scp
	```
[zsh自动完成介绍](http://zsh.sourceforge.net/Doc/Release/Completion-System.html)