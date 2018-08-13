---
layout: post
title: '设置一个计划任务，到了时间就运行代码'
subtitle: '大佬带带我'
date: 2018-08-13
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程

---

* content
{:toc}
##  前言
其实这篇文章的内容很简单，说白了就是设置一个计划任务，当触发到设定的条件后就运行。

下面的演示是 Win10 系统下 Python3，需要 Python 环境，因为代码就是 Python 的。
##  开始
找到**计划任务**，然后打开
![](https://upload-images.jianshu.io/upload_images/2989110-8c969704d4e883b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
右键**任务计划程序（本地）**，然后选择**创建基本任务**

![](https://upload-images.jianshu.io/upload_images/2989110-7771824effc8d853.gif)
名称和描述写自己能记住的，然后选择下一步
![](https://upload-images.jianshu.io/upload_images/2989110-d47737c97ced7ff7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
触发器看个人情况，下面的演示触发器是一次的
![](https://upload-images.jianshu.io/upload_images/2989110-b274b8fcc13f1eec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
设置好时间就选择下一步
![](https://upload-images.jianshu.io/upload_images/2989110-63a66b49b0bf7622.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
操作这里也就只有启动程序了
![](https://upload-images.jianshu.io/upload_images/2989110-8cefb04f0ab11d32.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
按照下图的格式来填写就好，也可以选择 pythonw.exe ，区别在于没有 python.exe 这个黑窗口。个人是喜欢加上的 python.exe ，而不是 pythonw.exe 。

因为 pythonw.exe 弹出的窗口可能会被遮挡住，python.exe 的则不会在弹出时就被遮挡住。
![](https://upload-images.jianshu.io/upload_images/2989110-044313c02e9bb5c3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着会看到一个完整的展示，点击完成就好
![](https://upload-images.jianshu.io/upload_images/2989110-2030eac53c54586a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
到了设置好的时间就会运行代码。

![](https://upload-images.jianshu.io/upload_images/2989110-7a23817902e1fc21.gif)

##  补充
如果需要修改，需要点击任务计划程序库，然后找到你设置好的任务，双击，然后就可以修改了
![](https://upload-images.jianshu.io/upload_images/2989110-afe0e5d77f67f14e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
需要注意一下条件那里，默认好像是勾选只有在计算机使用交流电源才启动此任务，说白了就是接上了电源才能启动任务，不接电源就不启动。取消勾选，什么时候都能运行。
![](https://upload-images.jianshu.io/upload_images/2989110-c5141705c360e2dd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  相关说明

演示的代码[这篇文章](https://weijunzii.github.io/2018/07/21/Use-Python-Draw-a-Heart.html)里面有