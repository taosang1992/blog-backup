---
title: 单列定宽单列自适应如何布局
date: 2017-03-16 12:14:10
tags:	HTML/CSS
---
做过主要内容自适应两列定宽之后，单列定宽单列自适应就显得容易多了，没有立马着手做，而是先把HTML结构撘起来，如代码所示：
```html
<header></header>
<div class="sideBox"></div>
<div class="content"></div>
<footer></footer>
```

接着思考如何让左边自适应，我的办法是先让右边的部分浮动到右边，左边不设宽度值，这样左边的部分有多宽占多宽，反正就给他留那么大点地，随他折腾。
主要CSS代码如下：
```css
* {
	margin: 0;
	padding: 0;
}
.sideBox{
	background-color: orange;
	width: 300px;
	float: right;
	height: 90vh;
}
.content{
	background-color: greenyellow;
	eight: 90vh;
}
header,footer{
	height: 60px;
	width: 100vw;
	background-color: black;
}
```
demo 预览地址：https://taosang1992.github.io/baidu-ife-homework/two-col-layout.html