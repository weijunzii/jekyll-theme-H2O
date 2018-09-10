---
layout: post
title: '安装和配置 Eclipse'
subtitle: '不难的~'
date: 2018-09-10
author: 伪君子
categories: 技术，编程
cover: ''
tags: Java 安装

---

* content
{:toc}
## 0 前言

之前安装了 [Java](https://weijunzii.github.io/2018/09/08/Install-Java.html) 并且配置好了 Java 的环境变量，现在来搞一下开发环境，下面就是下载安装和配置 Eclipse 的教程。

## 1 下载和安装

[https://www.eclipse.org/downloads/packages/installer](https://www.eclipse.org/downloads/packages/installer)

选择合适的进行下载，链接下面也有安装的教程，虽然只有英文，但是也很贴心了。
![](https://upload-images.jianshu.io/upload_images/2989110-bdb70049ad37ca4b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

因为安装的是 Java，所以选择 `Eclipse IDE for Java Developers`
![](https://upload-images.jianshu.io/upload_images/2989110-206c172c4ec842c1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
可以更改安装路径，点击安装后需要同意一个东西
![](https://upload-images.jianshu.io/upload_images/2989110-fc6e3e1a777eb161.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
安装完直接点 LAUNCH 就好
![](https://upload-images.jianshu.io/upload_images/2989110-de991253093dde8f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2 打开和使用

Workspace 直译过来就是工作空间，用来保存设置的，可以更改。可以把圈住的这个勾选了，不然每一次打开都会提醒一次
![](https://upload-images.jianshu.io/upload_images/2989110-42a084fdef378997.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
打开来之后先关掉欢迎页面，再新建一个 Java 项目
![](https://upload-images.jianshu.io/upload_images/2989110-feebc3f88267b119.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
项目名选择一个好记住的，开头字母要大写，勾选 Use a project specific JRE，这一步很重要，不然下次会有点麻烦。
![](https://upload-images.jianshu.io/upload_images/2989110-6537481c56515d39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
新建一个的 test 包，在 src 那点击鼠标右键，New，然后选择 Package
![](https://upload-images.jianshu.io/upload_images/2989110-a3aa8cd0a3a21687.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
名字嘛，看缘分命名了
![](https://upload-images.jianshu.io/upload_images/2989110-134431e9531e26ae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在新建的 test 包那点击一下右键，然后 New 一个 Class。
![](https://upload-images.jianshu.io/upload_images/2989110-8fa159fe77bb34fd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Class 的名字也就是类的名字首字母要大写。
![](https://upload-images.jianshu.io/upload_images/2989110-75a0a63c7d67d816.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
全部完成之后就是下图这样，当然，我这里的命名都是皮一下的，正式项目千万不要这样来命名。
![](https://upload-images.jianshu.io/upload_images/2989110-c092e5e2fe9a406e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
写完代码后，点击图中标识的那个按键就可以运行了。
![](https://upload-images.jianshu.io/upload_images/2989110-df479986e4571353.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 3 修改主题和字体

点击 Window ，接着点击 Preferences
![](https://upload-images.jianshu.io/upload_images/2989110-08da0b3375e5af1a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
找到 General，接着找到 Appearance，接着选择自己喜欢的主题样式，点击 Apply 就是应用
![](https://upload-images.jianshu.io/upload_images/2989110-989e0f44638b02f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
把 Appearance 展开就能看见 Colors and Fonts，进入后双击 Java，打开后找到 Java Editor Text Font，接着按 Edit Default。
![](https://upload-images.jianshu.io/upload_images/2989110-54f6f045aeb1ea02.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着就是修改一下字体和字体大小，修改完后确定
![](https://upload-images.jianshu.io/upload_images/2989110-97c8a9d4af491ea8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
确定主题和字体都合适之后，点击 Apply and Close 退出就好了。
![](https://upload-images.jianshu.io/upload_images/2989110-bca62686b352d572.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)