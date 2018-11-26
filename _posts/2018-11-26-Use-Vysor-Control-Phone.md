---
layout: post
title: '电脑使用 Vysor 控制手机'
subtitle: '再丢 U 盘我就是狗！！'
date: 2018-11-26
author: 伪君子
categories:
cover: ''
tags: 扩展程序 工具

---

* content
{:toc}
## 0  前言
想用安卓手机一步一步演示个东西给别人看的时候，恰巧遇到对方不在身边；安卓手机上的东西想投影到 Windows 电脑上，用电脑控制手机，却没找到合适的方式；上班时间想摸鱼，用手机又太明显了。那么 Vysor 就是一个挺好的选择。 

这里我测试使用的环境是 Win7 32 位的电脑，手机是联想 ZUK Z2，浏览器用的是 360 安全浏览器和谷歌浏览器。

##  1  电脑安装 Adb
>[https://adb.clockworkmod.com/](https://adb.clockworkmod.com/)

![](https://upload-images.jianshu.io/upload_images/2989110-dd776fa599c9d504.png)
下载回来后直接点击安装，直接选择 Finish。
![](https://upload-images.jianshu.io/upload_images/2989110-0449733f4b843248.png)
然后点击 Next 进行安装，安装路径可以修改的，我只是懒得修改。
![](https://upload-images.jianshu.io/upload_images/2989110-f1e78eb27c5fce5f.png)
之后就是等它自动安装了。
## 2  手机打开开发者模式

手机要打开开发者模式，通常从『设置』里找『关于本机』找到手机版本，比如 MIUI 系统，『MIUI 版本』选项；ZUI 找 『ZUI  版本』版本。

连续点击多次就会提示打开了『开发者选项』，然后找到『开发者选项』，进去把 USB 调试打开，USB 配置选择 MTP（媒体传输协议）。
## 3 安装
### 3.1  安装和使用客户端
>[http://www.vysor.io/download/](http://www.vysor.io/download/)

下载对应的就好，我这里下载的是 Windows 版本的，安装简单到不行，直接点击安装包，然后安装好了，直接会自动打开软件。

![](https://upload-images.jianshu.io/upload_images/2989110-04c1395e4c3ef504.png)

进入之后会提示要 Sign in with Google。
![](https://upload-images.jianshu.io/upload_images/2989110-55026795eb010c05.png)
点击登录，允许访问谷歌账号。
![](https://upload-images.jianshu.io/upload_images/2989110-9faf0ea595ea231a.png?)
接着把代码复制粘贴到 Vysor 内就好，手机用数据线连接到电脑，然后就可以愉快地使用了。
![](https://upload-images.jianshu.io/upload_images/2989110-f4d827904696a0b7.png)
### 3.2  安装和使用扩展程序
>链接: [https://pan.baidu.com/s/18k19h2jeE8QQP4zyzB0m3w](https://pan.baidu.com/s/18k19h2jeE8QQP4zyzB0m3w )
>提取码: b8aa

这个扩展是别人汉化修改过的，介意的就用客户端或者官方的扩展程序。(如果连接失效，请留言)
>[https://chrome.google.com/webstore/detail/vysor-beta/gidgenkbbabolejbgbpnhbimgjbffefm?authuser=1](https://chrome.google.com/webstore/detail/vysor-beta/gidgenkbbabolejbgbpnhbimgjbffefm?authuser=1)

把扩展程序下载回来，然后把压缩包解压。
![](https://upload-images.jianshu.io/upload_images/2989110-556676ee6cfc8ca8.png)
进入扩展中心， 360 安全浏览器的是 [se://extensions/](se://extensions/)，安装下图操作，先启用开发者模式，然后再选择加载已解压的扩展程序。选择扩展程序目录的时候要选到 VysorPro_1.7.7，这个文件夹，然后就能看到扩展程序了。
![](https://upload-images.jianshu.io/upload_images/2989110-b4599d0d4c668ecc.png)
谷歌浏览器的话，先进入 [chrome://extensions/](chrome://extensions/)，之后的操作和上面的一样。

如果出错了，那就是没选对文件夹，加载来源是： 路径\Vysor_Pro_for_Chrome_1.7.7\VysorPro_1.7.7
![](https://upload-images.jianshu.io/upload_images/2989110-3771d844be28ab64.png)
一开始使用的时候可能玄学一段时间，选择不了分辨率，手速快的话就能选择了，慢的话，等用一段时间就好了。

360 安全浏览器直接点击启动就能打开了，但是我这里测试的时候发现使用不了，提示是『该插件不受支持』。
![](https://upload-images.jianshu.io/upload_images/2989110-bf959f4ebc02e11a.png)

谷歌浏览器直接进入 [chrome://apps/](chrome://apps/) 就能看见 Vysor 了，手机用数据线连接到电脑后，点击进去就能使用 Vysor 了。
![](https://upload-images.jianshu.io/upload_images/2989110-68646f0380052f5f.png)



##  4 相关说明和演示
无论是使用客户端还是扩展程序，手机上都会安装 Vysor 的客户端。选定一个使用就好，个人没必要两个一起使用。

使用了之后打开屏幕旋转，如果不需要的话，记得关闭。

如果电脑右下角出现下面这个图，意思是要你在手机上确认一下，允许电脑对手机的调试。
![](https://upload-images.jianshu.io/upload_images/2989110-9d5889e26eef2d90.png)
如果电脑右下角出现下面这个图，说明已经成功连接了，可以愉快地玩耍了。
![](https://upload-images.jianshu.io/upload_images/2989110-355c3183bd7b2603.png)
进入之后的样子，截图的是汉化版，方便那些使用客户端的了解一下具体的功能。
![](https://upload-images.jianshu.io/upload_images/2989110-7f8249abae9d6c12.png)
圈住的图标的功能从左到右分别是，打开设备设置、录制屏幕、截图、降低音量、提高音量、旋转屏幕、切换屏幕开/关
![](https://upload-images.jianshu.io/upload_images/2989110-af0290ad1a35ee53.png)
 Vysor 可以用数据线连接，也可以用无线连接（手机连接的 wifi 和电脑需要在同一个网段下 ），个人觉得用数据线连接比无线连接好。

先给 Windows 下使用 Vysor 客户端的视频，

接着就是 Windows 下使用 Vysor 扩展程序的视频，没错，我用的是汉化版的。
