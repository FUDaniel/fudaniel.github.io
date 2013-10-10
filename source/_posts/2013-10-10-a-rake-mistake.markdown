---
layout: post
title: "在部署新文章时遇到的问题"
date: 2013-10-10 10:09
comments: true
categories: 
---
## 问题描述 ##
在执行rake deploy或者rake gen_deploy时出现如下错误  
Pushing generated _deploy website
	
	fatal: https://github.com/fudaniel/fudaniel.github.io/info/refs?service=git-receive-pack not found: did you run git update-server-info on the server?

## 解决办法 ##
在google上搜索没有找到好的解决办法。今天早上突然想到，git用于版本控制，昨天遇到过github客户端提示当前commit版本较remote版本小。也就是版本号不一致，产生了冲突。所以我将remote端同步到本地，将.git隐藏文件复制到_deploy文件夹覆盖新生成的.git文件夹。再执行rake deploy就会成功啦。  
## 犯的错误 ##
我这里导致版本不一致的操作是多次执行rake setup_github_pages命令，这会导致它完全删除原来的_deploy文件夹，然后重新生成新的。这样版本就会与remote的不一致。
## 正确的发布新文章流程 ##
1. 执行rake new_post['title']来生成一个博文；

2. 找对生成的markdown文件，编辑内容，当然是使用markdown语法来编辑；

3. 执行rake generate来生成文章；

4. 执行rake preview在本地预览；

5. 执行rake deploy发布到Github中。

6. 执行下面命令将修改的源码推送到source分支：

	git add .  
	git commit -m “your message”  
	git push origin source  
## 参考链接 ##
[windows下搭建octopress博客](http://www.cnblogs.com/oec2003/archive/2013/05/27/3100896.html)