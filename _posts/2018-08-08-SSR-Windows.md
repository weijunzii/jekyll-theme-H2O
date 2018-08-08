---
layout: post
title: 'ssr Windows 教程'
subtitle: '没有介绍'
date: 2018-08-08
author: 伪君子
categories: 技术，编程
cover: ''
tags: 
---

* content
{:toc}


#  说明

一般来说，提供 SSR 服务的网站会有说明的，按着网站给的说明来就好，如果没有，那就看这个吧，这里介绍用订阅地址导入，扫描二维码、从剪贴板导入非常简单，我决定不写。

[点击下载](https://kejibear.xyz/ssr-download/ssr-win.7z) ,也可以选择[下载这个](({{ site.url }}/screenshot/ssr-win.7z)),区别在于前者你可能下载不到，后者下载有点慢。

#  用订阅地址

下载，解压，打开文件夹

订阅地址需要[注册](https://weijunzii.github.io/2018/07/31/To-Climb-Over-The-Wall.html#3ss%E6%88%96ssr%E7%BF%BB%E8%B6%8A)才能获得，或者自己用 vps 搭建一个服务器。

运行 ShadowsocksR-dotnet4.0，不行的话再用 2.0

![](https://upload-images.jianshu.io/upload_images/2989110-192e9cac5e46b9be.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Windows 右下角会多出一个小飞机

![](https://upload-images.jianshu.io/upload_images/2989110-814925cb166e2e2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右键那个小飞机，选择 '服务器订阅' -> 'SSR服务器订阅设置...'

![](https://upload-images.jianshu.io/upload_images/2989110-3e7451fd53c88e6a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击 'Add'，清空网址框内的内容，然后将此订阅地址贴在网址内，勾选左下角的自动更新，然后点击 '确定'。

![](https://upload-images.jianshu.io/upload_images/2989110-d30451dae1211035.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右键小飞机，选择'服务器订阅' -> '更新SSR服务器订阅（不通过代理）

![](https://upload-images.jianshu.io/upload_images/2989110-a9c63164dd4d36c1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右键小飞机，选择'服务器' -> '对应的站点名字' -> 选择需要的节点

![](https://upload-images.jianshu.io/upload_images/2989110-19233d37d64780db.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右键小飞机，选择'系统代理模式' -> 勾选 '全局模式'

![](https://upload-images.jianshu.io/upload_images/2989110-166027c5f709ca85.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右键小飞机，选择'代理规则'，选择'绕过局域网和大陆'

![](https://upload-images.jianshu.io/upload_images/2989110-9f69c6b47cb5ade0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



如果不想用代理，退出小飞机既可。



#  win10该怎么关掉代理

 打开设置，选择‘网络和Internet’

![](https://upload-images.jianshu.io/upload_images/2989110-50d3035d4937b3c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 找到代理，然后把使用代理服务器关了

![](https://upload-images.jianshu.io/upload_images/2989110-e0a084636e1327ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这样就关掉了代理，如果使用过 SSR 之后不能上网，那就来这里把代理服务器关掉。

是这样的，用了 SSR 之后不退出它就直接关电脑，那就会造成电脑开机后连接不到网络，把使用代理服务器关了就好了。也可以选择电脑开机后直接打开 SSR，这样也可以使用网络/
