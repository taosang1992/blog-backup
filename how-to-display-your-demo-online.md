---
title: 如何用 github pages 在线展示你的Demo
date: 2017-03-15 19:04:55
tags: Github Pages	
---
今天收到了我在 IFE 学习 以来第一个评论，有同学问我如何在线展示自己的 Demo，在写答案的时候发现三言两语真的很难说清楚，就打开编辑器把思路整理写了下来，然后回复了这位同学。

#### 读这篇文章的时候默认你符合以下条件：
1.有 github 账号；
2.知道如何创建仓库；
3.会把自己的作业上传到 github 上

OK，接下来我们说重点
#### 如何在线展示 Demo ：
1.将你的作业上传到 github 上对应的仓库；
2.进入这个仓库的页面，默认是进入了 code 选项卡，可以看到下面是 master 分支；
3.点击 master，有弹出框，在这个弹出框输入 gh-pages（分支只能叫这个），这就建立了 gh-pages 分支，这个分支就是我们用来展示自己 Demo 的分支；
4.换到 settings 选项卡，往下找，会看到 github pages 部分，根据提示开通你的 github pages 服务；
5.之后就可以在线查看我们的demo了。

如果你的 Demo 没有 index.html,当你用 yourname.github.io/demoname 访问时候，默认显示的就是仓库的 readme 信息，有的话就是 index.html 的内容。

#### 怎么访问我们的作业呢？ 
按照文件路径访问即可，比如我的仓库叫 baidu-ife-homework，作业一叫 homework1.html，https://taosang1992.github.io/baidu-ife-homework/homework1.html 这样就可以访问了。

顺便说一句：github改版之后，网上很多教程过时了，单纯展示Demo是没必要搭建hexo博客的。
展示用的仓库叫啥名都成，不必是yourname.github.io，因为github pages会给你自动生成这个域名；另外你的任何仓库创建gh-pages分支之后，都可以在线展示。