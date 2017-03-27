---
title: 如何在一台电脑上使用多个git帐号
date: 2017-03-27 21:17:12
tags: Git 
---
> 如何在一台电脑上使用多个git帐号？

我被这个问题，困扰了许久，今天终于搞成功了，必须总结一下。

谢谢廖雪峰老师的[git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)，让我学会了`git`如何使用。但是当时是这样配置的：
```shell
$ git config --global user.name "username"
$ git config --global user.email "email@example.com"
```
请注意里边的 `global ` 参数，这是全局配置，你在电脑里任何一个地方使用`git`都会默认使用这个账户。

然而问题来了，我要在一台电脑上使用多个帐号呢，公司一个帐号，自己一个帐号，或是 github 一个 ，oschina 一个怎么办呢？

首先你要忍痛把全局设置取消掉，而且每次创建新仓库都要设置这个仓库的用户。
如下代码所示：取消全局设置
```shell
$ git config --global --unset user.name
$ git config --global --unset user.email
```
设置仓库对应的用户
```shell
$ git config user.name "taosang1992"  
$ git config user.email "taosang1992@gmail.com"
```
以上是针对的是原来已经配置好的账户，如此设置之后就可以按照正常的流程提交代码了。

##添加新账户
###1. 生成新的ssh-key
```shell
$ ssh-keygen -t rsa -f ~/.ssh/id_rsa_2 -C "email@example.com"
```
email@example.com这里是你新账户的邮箱。
请注意** id_rsa_2**是生成新key的名字，可以自己命名，但不能和原来的ssh-key一样。
###2. 添加到 ssh-agent 信任列表
```shell
$ ssh-add ~/.ssh/id_rsa_2
```
**请注意：**此处有坑，你可能会遇到这样的问题
> Could not open a connection to your authentication agent.

解决方案：（也可以是其他的，参考资料里边stackoverflow里边的答案你都可以试试）
```shell
$ ssh-agent bash
```
这之后，再添加。看到如下所示的情况，就证明添加成功了
```shell
$ ssh-add ~/.ssh/id_rsa_2
Identity added: /c/Users/dong/.ssh/id_rsa_2 (/c/Users/dong/.ssh/id_rsa_2)
```
参考资料：
http://www.cnblogs.com/sheldonxu/archive/2012/09/17/2688281.html
http://stackoverflow.com/questions/17846529/could-not-open-a-connection-to-your-authentication-agent

### 3. 添加ssh-key到github
详见：https://help.github.com/articles/connecting-to-github-with-ssh/
### 4.在config文件配置多个 ssh-key
找到你的.ssh文件夹，打开config文件；如果没有config自己建一个，不要设置后缀名。
配置如下：
```
Host github.com
   User taosang1992
   Hostname github.com 
   IdentityFile C:\Users\dong\.ssh\id_rsa

Host username.github.com
   User username
   Hostname github.com 
   IdentityFile C:\Users\dong\.ssh\id_rsa_2
```
根据你自己的情况配，你的用户名是什么，就把username改成什么。
###5.为每个仓库单独设置用户：
```shell
$ git config user.name "username"  
$ git config user.email "email@example.com"
```
自此，你就可以按照git的正常工作流程干活了。