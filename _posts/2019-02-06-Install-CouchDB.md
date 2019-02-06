---
layout: post
title: '安装并配置 CouchDB'
subtitle: '真的不会写摘要'
date: 2019-02-06
author: 伪君子
categories:
cover: ''
tags: 安装 CouchDB WebScraper
---

* content
{:toc}
#  0 前言
之前写过[用 Web Scraper 爬取即刻关注/被关注列表](https://weijunzii.github.io/2018/10/13/Use-WebScraper-Scrapy-Jike.html)，爬取下来的数没按照顺序排序。有解决的办法，去安装 CouchDB，然后设置一下从此 Web Scraper 爬取下来的数据都是有序的。

#  1 下载和安装
>[http://couchdb.apache.org/#download](http://couchdb.apache.org/#download)

进入后下载合适你电脑系统的 CouchDB。
![](https://upload-images.jianshu.io/upload_images/2989110-009cb58472d346c9.png)

这里演示一下 Windows 下安装，打开后直接点击 Next
![](https://upload-images.jianshu.io/upload_images/2989110-724ce576eaaa3cbb.png)
接受条款，然后点击 Next
![](https://upload-images.jianshu.io/upload_images/2989110-8b855d6103304157.png)
还是点击 Next
![](https://upload-images.jianshu.io/upload_images/2989110-475a7a316f1fb56b.png)
改一下路径，不要直接安装到 C 盘，然后点击 Next
![](https://upload-images.jianshu.io/upload_images/2989110-2c647bbc9abe1be1.png)
安装，冷静等待几分钟，很快安装完的。
![](https://upload-images.jianshu.io/upload_images/2989110-38b7dbe5c107735b.png)
#  2 设置
浏览器打开 [http://127.0.0.1:5984/_utils/](http://127.0.0.1:5984/_utils/)，别打开错了。
![](https://upload-images.jianshu.io/upload_images/2989110-33483037a3106560.png)

然后创建一个数据库，命名为 scraper-sitemaps
![](https://upload-images.jianshu.io/upload_images/2989110-e0dc472bf74ccf7d.png)
右键 Web Scraper，然后点击选项，进入设置界面
![](https://upload-images.jianshu.io/upload_images/2989110-d83fdc74c4519816.png)

Storage type 改成 CouchDB

Sitemap db 填写 http://localhost:5984/scraper-sitemaps

Data db 填 http://localhost:5984/
![](https://upload-images.jianshu.io/upload_images/2989110-494063fe02df29ef.png)
保存之后重启浏览器，然后  Web Scraper 爬取下来的数据就是有序的。

![](https://upload-images.jianshu.io/upload_images/2989110-daf50f45bb009a38.png)
进入 http://127.0.0.1:5984/_utils/ 能看到创建的数据库，点击进去能看到 Sitemap。
![](https://upload-images.jianshu.io/upload_images/2989110-a591533ca9765d2c.png)
而且是非常易于阅读的形式
![](https://upload-images.jianshu.io/upload_images/2989110-5475daee4b3c45ca.png)
如果重启浏览器不行就重启电脑，如果还不行，建议重买电脑。

#  3  说明
如果之前 Web Scraper 有 Sitemap，那先保存一份再去安装 CouchDB；如果已经安装且设置了，也可以去设置那里把 Storage type 改回 local storage (本地存储)，然后保存备份 Sitemap 后再改回去。