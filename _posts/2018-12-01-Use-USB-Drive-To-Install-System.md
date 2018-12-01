---
layout: post
title: '用启动盘安装系统'
subtitle: '可还行'
date: 2018-12-01
author: 伪君子
categories:
cover: ''
tags: 

---

* content
{:toc}
#  0 前言
一周前写了怎么[把 U 盘制作成启动盘](https://weijunzii.github.io/2018/11/21/The-Flash-Drive.html)，有启动盘肯定就是装系统了，那我就写一下怎么用启动盘装一个 Win10 系统吧。

#  1 安装

插入 U 盘，开启电脑、接着进入快捷启动项选择界面。不同电脑进入的方式不一样，清华同方台式机的是点击开机后直接按 F12 就能进入快捷启动项选择界面。

具体的需要自行查询进入方式。如果不确定什么时候按，那就一直按，直到出现快捷启动项选择界面。
![](https://upload-images.jianshu.io/upload_images/2989110-93b37db409396e44.png)

进入之后选择 U 盘所在的位置,比如我这里是金士顿的 U 盘，所以显示的是 KingstonDataTraveler，按回车进入。
![](https://upload-images.jianshu.io/upload_images/2989110-8f6ac9e187df6b43.png)

进入之后选择 【02】 U 深度 WIN8 PE 标准版，如果不行，那就选择其他的选项。
![](https://upload-images.jianshu.io/upload_images/2989110-ac0131c58f8f75fa.png)
选择了之后就能看见 U深度 PE 装机工具（自动弹出），映像文件路径会自动选择好，如果选择到的不是想安装的系统，点击**浏览**就能进入选择想要文件，最后选择确定。
![](https://upload-images.jianshu.io/upload_images/2989110-6aaa70e29ad6fe5d.jpg)
进入后谨慎选择格式化分区。选择了之后，原本 C 盘的文件都会清除，但是不影响其余盘的文件。
![](https://upload-images.jianshu.io/upload_images/2989110-d0af69dd6b15311b.jpg)
接着就会自动搞定，电脑会重启。启动了之后就能看见 Win10 的欢迎界面。
![](https://upload-images.jianshu.io/upload_images/2989110-9f5ef6d767c0c339.png)

#  2 说明
我用的是 U 深度装机版，装完之后自动给我安装了腾讯视频等一些软件，我基本上能确定我下载的 Win 10 是纯净的系统，那么为什么会出现这种问题，我也不好说，之前用 U 深度 UEFI 版是没问题的。

纯净版的系统去下面这个网站下载，[把 U 盘制作成启动盘](https://weijunzii.github.io/2018/11/21/The-Flash-Drive.html#3--%E4%B8%8B%E8%BD%BD%E7%BA%AF%E5%87%80%E7%89%88%E7%B3%BB%E7%BB%9F)这篇文章稍微介绍了一下。
>https://msdn.itellyou.cn/

有空我再测试一些是不是 U 深度装机版的问题，用下载回来的 Win10 装个虚拟机就能确定了。