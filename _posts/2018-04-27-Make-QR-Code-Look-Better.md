---
permalink: /2018/04/27/Make-QR-Code-Look-Better.html
title: 让你的二维码变得好看
subtitle: 彩色二维码了解一下~~
cover: ""
author: 君子
tags: 有趣的 二维码
date: 2018-04-27T00:00:00.000Z
layout: post
categories: 技术
---

* content
{:toc}


#  0  前言

上一篇介绍了用 [Python 来生成彩色动态的二维码](https://weijunzii.github.io/2018/04/26/Use-Python-Generate-Colorful-QRcode.html)，感觉对一般人来说用起来有点小麻烦，所以，今天介绍一下一些已经封装好了的，至少用起来舒服。

老老实实地说一句话，我真的看到那种黑白且单调的二维码就觉得烦厌和难受，一直都觉得难受的那种。

所以，希望下面的内容对正在看这篇文章的你有所帮助，也希望朋友圈的微商能够学一下下，换一个好看的二维码，至少看了开心啊。

#  1  解码

想要获得一张好看的二维码，那就少不了需要的文本（对于那些只提供二维码，却不给链接的行为表示强烈谴责。）

去这个网站 [http://jiema.wwei.cn/](http://jiema.wwei.cn/)，把保存的二维码上传就可以得到链接。
![二维码解码](https://img.lbjheiheihei.xyz/Fu4ZHJXcd2J4Gn74hptYTz1LKVj5 "二维码解码")

如果使用 Telegram 这个软件的话，可以使用这个机器人，把带二维码的照片发过去就直接可以解析出链接。

[http://telegram.me/QRCodeRoBot](http://telegram.me/QRCodeRoBot)

iOS 请用自带的相机，更加方便。

#  2  生成二维码

拿到了链接，下面该怎么折腾就怎么折腾。前面三个是网页的，第四个是 Android 的，第五个是iOS 的。
##  2.1  半色调二维码
进入网站，填写链接，选择上传图片，然后就生成二维码了，黑白的二维码，调到喜欢就下载吧。（实在是不建议用这个，黑白实在是难看）

[https://research.swtch.com/qr/draw](https://research.swtch.com/qr/draw)
![半色调二维码](https://img.lbjheiheihei.xyz/FuO7fwynW1AjrMTtf0SnUiFgvjM6 "半色调二维码")

##  2.2  彩色动态二维码
**Amazing QR Code**

把链接或者文字填入，上传图片或者 Gif，然后点击提交。等一会就会出现二维码了。（填入的内容不支持中文，支持 0~9,a~z, A~Z 以及常见的常用英文标点符号和空格）

建议是上传合适大小的图片或 Gif，请采用正方形或近似正方形的图片，不然会出现一点小偏差。

[http://www.amazing-qrcode.com/](http://www.amazing-qrcode.com/)
![amazing-qrcode](https://img.lbjheiheihei.xyz/FqDkBiIC0Iz_1F6G6CEiqy9u36eg "amazing-qrcode")
有人说生成的二维码是 AV 画质，我认真地想了想，这还真的是
![AV 画质的二维码](https://img.lbjheiheihei.xyz/FlxUhmtm2bGYwCtbuRWU_eKkbgxR "AV 画质的二维码")

##  2.3  带 logo 的彩色动态二维码
**Awesome-qr.js** 是英文，这个没办法，希望开发者能够尽快支持中文。

[https://www.bitcat.cc/webapp/awesome-qr/index.html](https://www.bitcat.cc/webapp/awesome-qr/index.html)

下面这图稍微解释了一下，大概就是这样。建议用谷歌浏览器，毕竟自带翻译。
![Awesome-qr.js](https://img.lbjheiheihei.xyz/FtiApAhsS2uy_6rh2N3aOOcVXJCc "Awesome-qr.js")

把该弄的都弄好后，点击右下角的小勾勾就开始生成了。

虽然不直接提供下载，但是，电脑可以选择鼠标右键，再**图片另存为**；手机微信也可以保存图片，大多数的浏览器都可以下载，过程曲折了点，但是也能用。


![生成的二维码](https://img.lbjheiheihei.xyz/FvbiBnmbBCjWWMG6jpxgoJdiB3nL "生成的二维码")

##  2.4  Android 
据我了解，**Awesome-QR** 的开发者只把软件上架到了谷歌 Play 商店，所以，没【翻越思维的墙】的朋友就看缘分了。

[https://play.google.com/store/apps/details?id=com.github.sumimakito.awesomeqrsample](https://play.google.com/store/apps/details?id=com.github.sumimakito.awesomeqrsample)

Awesome-QR 支持条码/QR 二维码解码，也就是说可以通过扫描二维码来解析二维码，不过不支持扫描相册里的二维码。

基本功能一看就懂，简单好用。
![Awesome-QR](https://img.lbjheiheihei.xyz/FlB4gmuJBfP8pPDYJpqcCp3_rzhp "Awesome-QR")

这个应用免费下载，可是有内购。购买专业版后可以不受广告的侵扰、使用 GIF 裁剪工具、不限制 GIF 帧数等。
![生成的二维码](https://img.lbjheiheihei.xyz/FpFTQd1Sn157oCBYqH1VgDlmkquC "生成的二维码")
##  2.5  iOS 
**EFQRCode** 是免费的，与 iPhone、iPad 和 iPod touch 兼容。

[https://itunes.apple.com/cn/app/EFQRCode/id1242337058?mt=8](https://itunes.apple.com/cn/app/EFQRCode/id1242337058?mt=8)

试过了之后，其实还不错的。
![EFQRCode](https://img.lbjheiheihei.xyz/FrqtTx6-bKVYjHmMX_GP_HeiGMih "EFQRCode")

#  3  相关说明


你所看到的乔巴二维码都是同一张图片在不同地方折腾出来的，哪一个更好就难说了，自行选择吧~

Amazing QR Code 的 GitHub 链接：https://github.com/sylnsfar/qrcode/blob/master/README-cn.md

Awesome-qr.js 的 GitHub 链接:https://github.com/SumiMakito/Awesome-qr.js

Awesome-QR 的 GitHub 链接:https://github.com/SumiMakito/AwesomeQRCode

EFQRCode 的 GitHub 链接：https://github.com/EyreFree/EFQRCode

最后，请允许我皮一下~~
![关注微信公众号，和我的聊天机器人聊聊天](https://img.lbjheiheihei.xyz/FpEEz40sM2wrU9ZSDSD5D5oneJG1 "关注微信公众号，和我的聊天机器人聊聊天")