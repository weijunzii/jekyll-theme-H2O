---
layout: post
title: '让你的二维码变得好看'
subtitle: '彩色二维码了解一下~~'
date: 2018-04-27
author: 伪君子
categories: 技术
cover: ''
tags: 有趣的 二维码

---

* content
{:toc}
#  0  前言

***

老老实实地说一句话，我真的看到那种黑白且单调的二维码就觉得烦厌和难受，一直都觉得难受的那种。所以，希望下面的内容对正在看这篇文章的你有所帮助，也希望朋友圈的微商能够长点心，换一个好看的二维码，至少我看了开心啊。
#  1  解码

***

想要获得一张好看的二维码，那就少不了需要的文本（对于那些只提供二维码，却不给链接的行为表示强烈谴责。）

去这个网站 [http://jiema.wwei.cn/](http://jiema.wwei.cn/)，把保存的二维码上传就可以得到链接。
![](https://upload-images.jianshu.io/upload_images/2989110-2716d5bc395bff86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果使用 Telegram 这个软件的话，可以使用这个机器人，把带二维码的照片发过去就直接可以解析出链接。

[http://telegram.me/QRCodeRoBot](http://telegram.me/QRCodeRoBot)

iOS 请用自带的相机，更加方便。
#  2  生成二维码

***

拿到了链接，下面该怎么折腾就怎么折腾。前面三个是网页的，第四个是 Android 的，第五个是iOS 的。
##  2.1  半色调二维码
进入网站，填写链接，选择上传图片，然后就生成二维码了，黑白的二维码，调到喜欢就下载吧。（实在是不建议用这个，黑白实在是难看）

[https://research.swtch.com/qr/draw](https://research.swtch.com/qr/draw)
![Snipaste_2018-04-26_20-25-24.png](https://upload-images.jianshu.io/upload_images/2989110-a16601d29443e748.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  2.2  彩色动态二维码
**Amazing QR Code**

把链接填入，上传图片或者 Gif，然后点击提交。等一会就会出现二维码了。

建议是上传合适大小的图片或 Gif，请采用正方形或近似正方形的图片，不然会出现一点小偏差。（我这里测试只能填入链接，文本不行）

[http://www.amazing-qrcode.com/](http://www.amazing-qrcode.com/)
![](https://upload-images.jianshu.io/upload_images/2989110-3f131aa89382a96f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  2.3  带 logo 的彩色动态二维码
**Awesome-qr.js** 是英文，这个没办法，希望开发者能够尽快支持中文。

[https://www.bitcat.cc/webapp/awesome-qr/index.html](https://www.bitcat.cc/webapp/awesome-qr/index.html)

下面这图稍微解释了一下，大概就是这样。建议用谷歌浏览器，毕竟自带翻译。
![](https://upload-images.jianshu.io/upload_images/2989110-353e89fcf6268668.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

把该弄的都弄好后，点击右下角的小勾勾就开始生成了。

是网页不假，可是这个只能网站中嵌入，有点坑...

##  2.4  Android 
据我了解，**Awesome-QR** 的开发者只把软件上架到了谷歌 Play 商店，所以，没【翻越思维的墙】的朋友就看缘分了。

[https://play.google.com/store/apps/details?id=com.github.sumimakito.awesomeqrsample](https://play.google.com/store/apps/details?id=com.github.sumimakito.awesomeqrsample)

Awesome-QR 支持条码/QR 二维码解码，也就是说可以通过扫描二维码来解析二维码，不过不支持扫描相册里的二维码。

基本功能一看就懂，简单好用。
![](https://upload-images.jianshu.io/upload_images/2989110-78fa7170cbbb9046.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这个应用免费下载，可是有内购。购买专业版后可以不受广告的侵扰、使用 GIF 裁剪工具、不限制 GIF 帧数等。

##  2.5  iOS 
**EFQRCode** 是免费的，与 iPhone、iPad 和 iPod touch 兼容。

[https://itunes.apple.com/cn/app/EFQRCode/id1242337058?mt=8](https://itunes.apple.com/cn/app/EFQRCode/id1242337058?mt=8)

没有测试机，也骗不到别人下载使用再和我说体验，所以，只能悲惨省略。
#  3  相关说明

***

Amazing QR Code 的 GitHub 链接：https://github.com/sylnsfar/qrcode/blob/master/README-cn.md

Awesome-qr.js 的 GitHub 链接:https://github.com/SumiMakito/Awesome-qr.js

Awesome-QR 的 GitHub 链接:https://github.com/SumiMakito/AwesomeQRCode

EFQRCode 的 GitHub 链接：https://github.com/EyreFree/EFQRCode

最后，请允许我皮一下~~

![关注微信公众号，和我聊聊天](https://upload-images.jianshu.io/upload_images/2989110-4a62ca05ab3d13ca.gif?imageMogr2/auto-orient/strip)