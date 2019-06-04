---
layout: post
title: '朋友圈百分之百不折叠方案，了解一下'
subtitle: '快来了解一下~'
date: 2019-06-04
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}


## 0 前言
朋友圈发动态，复制的文字过多会被折叠.各路大神开始了骚操作来防止折叠，前些天我想了想，其实我勉勉强强也能实现。

于是我用 Auto.js 实现了.

## 1 下载和安装 Auto.js

酷安可以下载：<https://www.coolapk.com/apk/129872>

Github 也可以下载：<https://github.com/hyb1996/Auto.js/releases>

试试是哪个吧，我忘记是哪个了🤣
![](https://upload-images.jianshu.io/upload_images/2989110-29d407201663146d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2 黏贴代码
代码其实挺好理解的，不解释了。

```JavaScript
auto();
//打开微信
launch("com.tencent.mm");
toast("请进入发朋友圈入口");
//等待发布朋友圈
waitForActivity("com.tencent.mm.plugin.sns.ui.SnsUploadUI");

//复制剪贴板上的内容
var str = getClip();
var array = str.split("");
var len = array.length;

//把剪贴板上的内容一个一个输出
for (var i = 0; i < len; i++) {
    input(array[i]);
}

toast("搞定收工~\n\n 公众号：伪君子的梦呓");
exit();
```
复制黏贴，能跑就行。复制黏贴的操作看下图，不同的 Auto.js 版本可能会不一样，但是思路都是一样的。
![](https://upload-images.jianshu.io/upload_images/2989110-1ad99fb9aadc665d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
视频如下，先复制好想输入的，然后运行代码。

为了方便使用，我打包了一下

公众号菜单栏那输入【朋友圈不折叠】就可获得下载链接~

![公众号](https://upload-images.jianshu.io/upload_images/2989110-97448888836e388b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

app的使用视频如下，得打开无障碍服务，然后回到桌面，再点击图标才能运行，一次不行就再来一次😂

## 3 相关说明
这个代码运行的结果还是有缺陷的，中文版微信，动态的开头会带有『这一刻的想法...』；英文版的微信，动态的开头会带有『Say someth...』，解决不了，不解决。

Auto.js：<https://github.com/hyb1996/Auto.js>

Auto.js文档：<https://hyb1996.github.io/AutoJs-Docs/#/>

Auto.js论坛：<https://www.autojs.org/categories>
