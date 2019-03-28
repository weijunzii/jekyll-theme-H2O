---
layout: post
title: '蓝桥杯历届试题-回文数字'
subtitle: '回得太多了'
date: 2019-03-23
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


##  0 前言
前面有一篇文章是介绍[用 TranslucentTB 让任务栏变透明](https://weijunzii.github.io/2019/03/14/TranslucentTB-Make-You-Taskbar-Clear.html)，要是有个类似 Mac 的 Dock（程序坞）就更好了。

我看中了 RocketDock 这个软件，用起来也舒服，实测 64 位的 Win 7 和 Win 10都能使用，占用的资源小。
## 1 下载

>[https://punklabs.com/](https://punklabs.com/)

![](https://upload-images.jianshu.io/upload_images/2989110-2f6f3811fc8c0970.png)
## 2 安装
下载回来后双击安装，基本上是一路 Next。
![](https://upload-images.jianshu.io/upload_images/2989110-9fa969719e2f0742.png)
同意，然后 Next
![](https://upload-images.jianshu.io/upload_images/2989110-ea0c2274651e83e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择语言这里直接默认的英语就好，后面可以修改语言的。
![](https://upload-images.jianshu.io/upload_images/2989110-2acbd56700fc4ac2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
安装路径最好修改一下，当然，不改也行。
![](https://upload-images.jianshu.io/upload_images/2989110-57feb73219c528f1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在桌面创建一个快捷方式还是有必要的。
![](https://upload-images.jianshu.io/upload_images/2989110-650bef9ac907fba9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击安装
![](https://upload-images.jianshu.io/upload_images/2989110-0a20a2166aff4689.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

安装好之后就能在屏幕顶部看到 Dock 栏了。
![](https://upload-images.jianshu.io/upload_images/2989110-bc063ccf54c2fbcb.gif)

## 3 配置
点击程序设置进入 RocketDock 的设置页，把语言改成中文，勾选启动时自动运行。
![](https://upload-images.jianshu.io/upload_images/2989110-ac5194ccc5dc7b90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
位置可以修改成在屏幕的别的地方。上下左右都可以，图层位置看个人喜好。
![](https://upload-images.jianshu.io/upload_images/2989110-af6bff528ff602b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
图标和风格也是看个人喜好，行为这里我倒是勾选了自动隐藏。
![](https://upload-images.jianshu.io/upload_images/2989110-de280327d894459a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

整体效果可以看下面这个 gif，win 10 和 win 7 都安装了 RocketDock ，都是64位的电脑。
![](https://upload-images.jianshu.io/upload_images/2989110-5111b2def14d2965.gif?imageMogr2/auto-orient/strip)
## 4 相关说明
RocketDock 占用的 CPU 和内存都非常小
![](https://upload-images.jianshu.io/upload_images/2989110-897d13fbd89a2936.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>[https://punklabs.com/blog/saying-goodbye-to-rocketdock](https://punklabs.com/blog/saying-goodbye-to-rocketdock)

这篇文章说 RocketDock 已经死了，应该就是说以后不会再维护了，有点可惜。
