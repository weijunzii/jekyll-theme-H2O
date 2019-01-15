---
layout: post
title: '安装脚本实现『一键教学评估』'
subtitle: '美滋滋美滋滋'
date: 2019-1-15
author: 伪君子
categories:
cover: ''
tags: 扩展程序 脚本

---

* content
{:toc}
# 0 前言
前段时间看博客的时候发现了一个很有意思的脚本『四川大学综合教务系统助手』，我最喜欢的两个功能是两周内不必登录和一键评教。

我校的教务管理系统和四川大学的教务管理系统是一样的，也就是说我是可以使用的。基本上，只要是 URP 高校教务管理系统就能使用这个脚本。
![](https://upload-images.jianshu.io/upload_images/2989110-dfd6155d94b638e1.png)
#  1 安装和准备

因为作者已经在他的博客内给了并且说明了怎么使用 Bookmarklet，那我就只展开讲讲怎么在 Tampermonkey 安装和设置脚本，而且我比较推荐使用 Tampermonkey 来运行脚本。
>[https://zhaoji.wang/sichuan-university-urp-assistant/](https://zhaoji.wang/sichuan-university-urp-assistant/)

首先得下载和安装油猴，请看[这篇文章](https://weijunzii.github.io/2018/10/20/Tampermonkey.html)，接着是进入下面这个链接安装脚本
>[https://greasyfork.org/zh-CN/scripts/368192-四川大学综合教务系统助手](https://greasyfork.org/zh-CN/scripts/368192-%E5%9B%9B%E5%B7%9D%E5%A4%A7%E5%AD%A6%E7%BB%BC%E5%90%88%E6%95%99%E5%8A%A1%E7%B3%BB%E7%BB%9F%E5%8A%A9%E6%89%8B)

安装完成后点击一下 Tampermonkey，在弹出的界面里点击管理面板
![](https://upload-images.jianshu.io/upload_images/2989110-92846eba733ad416.png)
进入后找到『四川大学综合教务系统助手』这一栏，然后点击编辑
![](https://upload-images.jianshu.io/upload_images/2989110-765f7942c078f424.png)
接着点击设置，在包括/排除那里的用户包括添加学校教务管理系统的网址，格式按照原始包括那的格式就好。可以是 ip 地址，也可以是域名，注意后面的 * 也是要加上的，搞定之后记得保存。
![](https://upload-images.jianshu.io/upload_images/2989110-06285d160226ccc0.png)

#  2 使用
安装和设置好之后运行脚本，登录页面会出现 SCU URP 助手 0.7.13 这样的提示以及两周内不必登录的选项。
![](https://upload-images.jianshu.io/upload_images/2989110-b61009f510afbb37.png)
登录进去之后也能看到提示
![](https://upload-images.jianshu.io/upload_images/2989110-6f9ae20c67c46c03.png)
在教学评估那里多了一个『一键评教』的功能，见文知意，我就不多说了。
![](https://upload-images.jianshu.io/upload_images/2989110-dfd6155d94b638e1.png)

#  3 说明
作者博客上的说明：[https://zhaoji.wang/sichuan-university-urp-assistant/](https://zhaoji.wang/sichuan-university-urp-assistant/)
