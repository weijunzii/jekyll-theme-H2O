---
layout: post
title: '把网页制作成 Chrome App'
subtitle: '好玩又好用'
date: 2018-12-13
author: 伪君子
categories:
cover: ''
tags: 有趣的

---

* content
{:toc}
#  0 前言
在即刻看见了一篇文章，内容是关于把网页制作成一个桌面应用，试了一下，感觉挺好的。干脆写一篇文章记录一下，感觉美滋滋~

#  1 创建快捷方式
将想转换的网页收藏到书签栏，进入[chrome://apps/](chrome://apps/)，把收藏的书签下拉到页面中间的空白处。
![](https://upload-images.jianshu.io/upload_images/2989110-f3d6ed89426cfa90.gif)

选中想创建快捷方式的图标，然后右键，接着选择在窗口中打开，点击创建快捷方式，在弹出的界面里选择创建。
![](https://upload-images.jianshu.io/upload_images/2989110-1fc058863426bcd3.gif)

在桌面就能看见一个丑丑的快捷方式，在应用程序里面就能看见 Chrome 应用下面有一个微信的快捷方式。


![](https://upload-images.jianshu.io/upload_images/2989110-3f82dafb21f8d23f.png)

还有另一个方法，那就是在想创建快捷方式的网页里点击设置按钮，接着在更多工具里面点击 **创建快捷方式**，这时开始菜单和桌面就都有快捷方式了。
![](https://upload-images.jianshu.io/upload_images/2989110-3fc3c85b204b37da.png)
再进入 [chrome://apps/](chrome://apps/) 里面勾选一下在窗口打开，这样就是一个独立的应用了。
![](https://upload-images.jianshu.io/upload_images/2989110-8434d03e94b07399.png)

#  2 替换图标
快捷方式的名字是 URL，自行修改就好；图标是网页的 favicon.ico，好像因此图标就变得模糊。

图标是可以替换的，可以直接下载 .ico 格式的文件进行替换，也可以把图片或图标转化为ico 格式的文件再进行替换。

直接下载.ico 格式图标的链接：
>[https://www.easyicon.net](https://www.easyicon.net)

下载图标的链接
>[http://iconfont.cn/](http://iconfont.cn/)

把图片或图标转化为ico 格式文件的链接：
>[http://www.uupoop.com/ico](http://www.uupoop.com/ico)
>[http://www.faviconico.org](http://www.faviconico.org)

先在开始菜单里右键一下快捷方式，在更多里面打开文件位置（桌面的快捷方式打开的文件位置是谷歌浏览器的文件位置，不是快捷方式的文件位置）
![](https://upload-images.jianshu.io/upload_images/2989110-1ee88558e2428663.png)
接着就会进入类似下面的文件路径，因为每一个人的用户名都不一样。

C:\Users\weiju\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Chrome 应用
![](https://upload-images.jianshu.io/upload_images/2989110-d4c835d1862aaa81.png)
右键快捷方式，选择属性，在属性页中带你就快捷方式，接着选择更换图标，在打开的界面内选择你浏览就能找到下载回来的图标了。
![](https://upload-images.jianshu.io/upload_images/2989110-631589e7f45d68ef.png)

下图就是打开快捷方式之后的样子，微信网页版是会显示 URL 的，别的好像都不会。我试了 notion 和微信，只有微信是显示 URL 的。
![](https://upload-images.jianshu.io/upload_images/2989110-8a78f537be2e69f6.png)
# 3 说明
我因为不喜欢微信的 Windows 客户端，所以才使用把网页版微信制作成 Chrome App。制作成 Chrome App 之后还可以使用谷歌浏览器的扩展，美滋滋。

这篇文章是看了少数派作者 SpencerWoo 的文章后写的，SpencerWoo 的文章还提到了 Nativefier 和 Web2Desk 把网页转制成为一个 **可安装的** 桌面应用，我试了一下 Web2Desk，感觉也挺简单的。

参考文章链接：[看不惯糟糕、老旧的桌面客户端？直接让网页版应用做你的桌面 App](https://sspai.com/post/50250)
