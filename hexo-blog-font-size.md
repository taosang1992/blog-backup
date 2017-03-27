---
title: Hexo 你的博客之修改字体大小
date: 2017-03-06 08:04:14
tags: Hexo
categories: Hexo
<<<<<<< HEAD
---
由于Hexo博客自带的 14 号字看起来实在太小了，所以决定折腾一番，改成 18 号字，看起来会更舒服一些。

Google 了一番，找到了一篇[详细教程](http://prozhuchen.com/2015/10/05/Hexo%E5%8D%9A%E5%AE%A2%E4%B9%8B%E6%94%B9%E5%AD%97%E4%BD%93/)，你可以点进去瞧瞧。想要改字体大小，首先要知道字体大小的值在哪个文件。

通常来讲，Next主题控制字体大小的文件是在主题文件夹中的 source\css\ _variables 目录下的 base.styl 文件。我的完整路径是：D:\hexo\themes\next\source\css\ _variables
=======
description: 这篇文章主要讲的是如何修改 Next 主题的字体大小
---
由于Hexo博客自带的 14 号字看起来实在太小了，所以决定折腾一番，改成 16 号字，看起来会更舒服一些。

Google 了一番，找到了一篇[详细教程](http://prozhuchen.com/2015/10/05/Hexo%E5%8D%9A%E5%AE%A2%E4%B9%8B%E6%94%B9%E5%AD%97%E4%BD%93/)，你可以点进去瞧瞧。想要改字体大小，首先要知道字体大小的值在哪个文件。

通常来讲，Next主题控制字体大小的文件是在主题文件夹中的 source\css\_variables 目录下的 base.styl 文件。我的完整路径是：D:\hexo\themes\next\source\css\_variables
>>>>>>> be4fa004de1917e9a7982d54f4f22516876f4319

接下来就是改成你想要的字体大小了，用编辑器打开 base.styl 文件，找到如下代码然后修改即可：
```
 // Font size
<<<<<<< HEAD
$font-size-base           = 18px    //修改以前是14，我改成了18
=======
$font-size-base           = 16px    //修改以前是14，我改成了16
>>>>>>> be4fa004de1917e9a7982d54f4f22516876f4319
$font-size-small          = $font-size-base - 2px
$font-size-smaller        = $font-size-base - 4px
$font-size-large          = $font-size-base + 2px
$font-size-larger         = $font-size-base + 4px

// Headings font size
$font-size-headings-step    = 2px
$font-size-headings-base    = 24px  //这个是标题大小，如果你觉得不满意，可以改的更大一点
```
修改完之后，保存文件。重新部署 hexo ，就可以看到博客字体已经变成你想要的大小了。
