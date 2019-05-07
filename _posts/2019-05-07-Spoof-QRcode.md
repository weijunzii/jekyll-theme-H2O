---
layout: post
title: '我的小程序『恶搞二维码』开源了'
subtitle: '终于开源了，我没有咕咕咕'
date: 2019-05-07
author: 伪君子
categories:
cover: ''
tags: 小程序
---

* content
{:toc}


## 0 前言
之前说过要把『恶搞二维码』这个小程序开源，刚好五一假期有点时间，于是把代码完善了一下，然后前些天开源出来了。
![小程序二维码](https://upload-images.jianshu.io/upload_images/2989110-c52141e89ec8ad91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

许可协议: Apache2.0

>[https://github.com/weijunzii/Spoof-QRcode](https://github.com/weijunzii/Spoof-QRcode)

![页面截图](https://upload-images.jianshu.io/upload_images/2989110-3e896190752cf209.png?)

## 1 说明
下面是有意思的例子，扫描看一下

![有趣的例子](https://upload-images.jianshu.io/upload_images/2989110-d6cda82667ad4e07.png)

如果不填写群名和内容就点击『恶搞』 生成图片，那么群名会随机，内容被自动填写为我写好的内容。

因为小程序里面 if 不能嵌套 ，所以代码只能变成这样。

![部分代码](https://upload-images.jianshu.io/upload_images/2989110-f5113838df0a7d25.png)

如果输入的内容里包含敏感词，会提示 『包含敏感词，请重新编辑』。删掉输入的内容就能发现什么是敏感词，程序会自动把敏感词替换成 *，敏感词列表不太完善，请见谅。

没钱用 API ，微信提供的那个需要用服务器，我不太想用服务器，所以直接前端实现。

![敏感词](https://upload-images.jianshu.io/upload_images/2989110-09a407a40b604d60.png)

1.内容不能有 emoji，否则 ios 扫描二维码会乱码

2.部分手机生成的二维码和一般的二维码有区别，具体表现为有小白边。如下图所示：

   ![生成的图片](https://upload-images.jianshu.io/upload_images/2989110-54edf1449ff2f1b9.png)

3.引导层对不齐。模拟器上稳稳妥妥没毛病，真机上各种不齐。

   ![截图](https://upload-images.jianshu.io/upload_images/2989110-34997f3b23dd4284.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.iOS 上点击奖赏作者，图片加载不出来。

## 2 Thanks

这个小程序，绘图用的是 Painter ，没有这个库，这个小程序可能只是一个想法。

> [https://github.com/Kujiale-Mobile/Painter ](<https://github.com/Kujiale-Mobile/Painter> )

还要感谢帮我测试、给我提建议的各位小伙伴，一起完善了这个小程序。

## 3 TODO

- [ ] 修正引导层
- [ ] 完善敏感词
- [ ] 生成的图片加上带壳截图
- [ ] 随机群头像

## 4 相关说明
另一个小程序『颜值检测仪』早就开源了，点击[查看说明](https://mp.weixin.qq.com/s/r5F1xuIc7iC3DaOgZis9Nw)。

>[https://github.com/weijunzii/beauty](https://github.com/weijunzii/beauty)