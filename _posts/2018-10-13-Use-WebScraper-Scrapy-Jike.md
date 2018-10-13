---
layout: post
title: '用 WebScrapy 爬取即刻关注/被关注列表'
subtitle: '爬就完事了~'
date: 2018-10-13
author: 伪君子
categories: 技术，编程
cover: ''
tags: 扩展程序

---

* content
{:toc}
## 0 前言
在即刻看见即友说用 WebScrapy 爬取了关注列表和被关注列表，感觉很爽，我评论了一句我觉得我可以写一个教程，然后就有人问我怎么搞了。骚话不说，教程来了。

## 1 安装 WebScrapy

其实我之前已经介绍过怎么安装谷歌浏览器扩展程序，所以这里只给一个[链接](https://weijunzii.github.io/2018/10/07/Install-The-Chrome-Extension.html)，如果说想要打包好的 .crx 文件，可以去下面这个链接下载，不保证绝对安全。
>https://pan.baidu.com/s/1i6kIvGh 

>密码: i7e9

看到下图这样就说明是已经安装好了
![](https://upload-images.jianshu.io/upload_images/2989110-1136494d012af338.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2 准备爬取
打开想爬取内容的网站，然后按一下 F12 就能看见  WebScrapy 了。
![](https://upload-images.jianshu.io/upload_images/2989110-008bc9df01a25a36.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果看不见，按照图中的顺序修改一下就可以了。
![](https://upload-images.jianshu.io/upload_images/2989110-c906c7e3ca5858d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
下面我来介绍一下怎么用 WebScrapy 爬取即刻上关注我的人的信息

先进入 WebScrapy，然后选择 Create new sitemap，接着选择 Create sitemap
![](https://upload-images.jianshu.io/upload_images/2989110-f5d9426963bf7d36.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Sitemap name 只能是英文，不能是中文；Start URL 就是你想爬取的链接，填好后选择 Create Sitemap
![](https://upload-images.jianshu.io/upload_images/2989110-8d2c73f38fa5737e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入这个界面后选择 ADD new selector
![](https://upload-images.jianshu.io/upload_images/2989110-6d25ed7d7d609f40.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
id 也只能是英文，不能是中文；Type 选择 Element scroll down,这是因为即刻的页面是直接下拉就可以看到更多内容；

要勾选 Mulitple ，因为要爬取的不是一个；Delay (ms) 填写 5000
![](https://upload-images.jianshu.io/upload_images/2989110-079d0c094af320e6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着是重头戏，在 Selector 的右边选择 Select，然后去即刻的页面选择一个包含了人的信息的框，接着再选择一个， WebScrapy 会自动选择好相同的元素。
![](https://upload-images.jianshu.io/upload_images/2989110-6cfd0a2ee8a01ac7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择好之后点击 Done selecting! ，选择好之后会有下图中圈住的那样的元素。确认无误之后就选择 Save selector 
![](https://upload-images.jianshu.io/upload_images/2989110-a1e2428a5c565ad2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
完成后应该就是这样的，点击下面那一行，进入新的界面进行选择
![](https://upload-images.jianshu.io/upload_images/2989110-62d0cc2e19e9a3a3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
注意我这里是在 _root/jike 下面进行操作的， 选择 ADD new selector
![](https://upload-images.jianshu.io/upload_images/2989110-1a87c1a81bed21bf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
id 填写自己能辨别的，我这里填写的是 name ，因为我要爬取名字；Type 选择 Text；Delay (ms) 选择 100 或者 500；点击 Selector 右边的 Select，进去页面选择人的名字，选择好之后点击  Done selecting! 

我们可以点击 Data preview 查看一下选择对了没
![](https://upload-images.jianshu.io/upload_images/2989110-1bd60f29ae97bb51.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

确认无误之后就选择 Save selector。
![](https://upload-images.jianshu.io/upload_images/2989110-9521fd71f6c206a6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

再添加一个选择，点击 ADD new selector
![](https://upload-images.jianshu.io/upload_images/2989110-9feb4206185f1086.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
操作和上面的是一样的，id 我这里填写的是 sign ，因为我要爬取的是签名；Type 选择 Text；Delay (ms) 选择 100 或者 500；点击 Selector 右边的 Select，进去页面选择人的签名，选择好之后点击  Done selecting! 
![](https://upload-images.jianshu.io/upload_images/2989110-b16a9e4f49157ed0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
确认无误之后就选择 Save selector。

同理，再添加一个选择。

操作基本上是一样的，我想看一下我关注这个人没。
![](https://upload-images.jianshu.io/upload_images/2989110-5032476dd2fe3e0a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
完成后的样子
![](https://upload-images.jianshu.io/upload_images/2989110-291978c13037261d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击 Sitemap，选择 Selector graph 查看一下
![](https://upload-images.jianshu.io/upload_images/2989110-7df04b7fdfe40b46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这样的图，妥了。
![](https://upload-images.jianshu.io/upload_images/2989110-fbeb0a6d6cbafae6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 3 开始爬取和导出结果
点击 Sitemap，选择 Scrape 准备爬取
![](https://upload-images.jianshu.io/upload_images/2989110-32eed2fc02463c6e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击 Start scraping 就开始了，会开一个新的浏览器窗口进行爬取，速度有点慢，因为爬取的稍微有点多了。
![](https://upload-images.jianshu.io/upload_images/2989110-8ee772acf5348309.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
爬取完之后会自动关掉打开的窗口，接着显示爬取结果。
![](https://upload-images.jianshu.io/upload_images/2989110-a08bfa8cf83f7bc9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果想要导出爬取结果，按照下图来操作就好
![](https://upload-images.jianshu.io/upload_images/2989110-e2d43fee7b5e4442.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着点击 Download now
![](https://upload-images.jianshu.io/upload_images/2989110-ac6e8ac3f1d48c28.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
打开文件看一下，美滋滋
![](https://upload-images.jianshu.io/upload_images/2989110-42a8ae39425ac44a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  4 导入别人弄好的 Sitemap
拿我的做例子，复制下面的文字，也可以说是代码。
```
{"startUrl":"https://web.okjike.com/user/60e10ca7-f952-4642-9407-04717b80b5f4/follower","selectors":[{"parentSelectors":["_root"],"type":"SelectorElementScroll","multiple":true,"id":"jike","selector":"div.user-card-header","delay":"5000"},{"parentSelectors":["jike"],"type":"SelectorText","multiple":false,"id":"name","selector":"h1.user-card-title","regex":"","delay":"100"},{"parentSelectors":["jike"],"type":"SelectorText","multiple":false,"id":"sign","selector":"p.user-card-extra","regex":"","delay":"100"},{"parentSelectors":["jike"],"type":"SelectorText","multiple":false,"id":"follower","selector":"div:nth-of-type(3)","regex":"","delay":"100"}],"_id":"jike_follower"}
```
点击 Create new sitemap，接着选择 Import sitemap
![](https://upload-images.jianshu.io/upload_images/2989110-8c6d71e73f90060d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
把复制的代码黏贴到 Sitemap JSON 那个框里，Rename Sitemap (optional) 可以填写，也可以不填写，然后 Import sitemap 
![](https://upload-images.jianshu.io/upload_images/2989110-d7e136dc2060fa24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
但是这里是爬取关注我的人的信息，所以要用的话，得修改一下链接，
![](https://upload-images.jianshu.io/upload_images/2989110-12ecee5ddf861bf3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
把 Start URL 改成你的，保存后就可以愉快地玩耍了。
![](https://upload-images.jianshu.io/upload_images/2989110-610ca2b0f843d1cf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
提供一个不含关注信息的 Sitemap，以及，把链接改一下就能爬取自己关注的人的信息了。
```
{"selectors":[{"parentSelectors":["_root"],"type":"SelectorElementScroll","multiple":true,"id":"jike","selector":"div.user-card-header","delay":"5000"},{"parentSelectors":["jike"],"type":"SelectorText","multiple":false,"id":"name","selector":"h1.user-card-title","regex":"","delay":"100"},{"parentSelectors":["jike"],"type":"SelectorText","multiple":false,"id":"sign","selector":"p.user-card-extra","regex":"","delay":"100"}],"startUrl":"https://web.okjike.com/user/60e10ca7-f952-4642-9407-04717b80b5f4/following","_id":"weijunzi"}
```
## 5 说明
此处应该有一个视频，可是本肥宅不想动手录制，麻烦大家假装有视频，谢谢了。

提供一个参考链接，可以去看看：[https://www.zhihu.com/question/47883186/answer/155560145](https://www.zhihu.com/question/47883186/answer/155560145)