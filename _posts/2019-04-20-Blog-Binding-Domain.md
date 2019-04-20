---
layout: post
title: 'GitHub Pages 搭建的博客绑定域名'
subtitle: '简单又轻松'
date: 2019-04-20
author: 伪君子
categories:
cover: ''
tags: GitHub 博客
---

* content
{:toc}


## 0 前言
用 GitHub Pages 搭建了个博客之后除了更新点文章之后就没怎么管过，一年前买的域名快过期了，花 69 续了一年，不想浪费钱，不想再忍受微信的提醒，于是把 Github Pages 搭建的博客绑定 lbjheiheihei.xyz 这个域名。（域名早已备案）
![](https://upload-images.jianshu.io/upload_images/2989110-37a973f90c5e5a13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这篇文章的前提是有域名、有 [Github Pages 搭建的博客](https://lbjheiheihei.xyz/2018/04/02/Use-github-Set-Up-The-Blog.html)。

## 1 具体过程
网上一堆不知所以的教程，看得我头昏脑胀，花了不少时间试出来了。
### 1.0 创建 CNAME
首先在你的库下面添加一个 CNAME （别名记录）文件，建议直接在 GitHub 那创建
![](https://upload-images.jianshu.io/upload_images/2989110-f05711291b3a68a7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
CNAME 记得要大写，然后内容是写你的域名，图中这样的格式，不要加上 http、https、www。
![](https://upload-images.jianshu.io/upload_images/2989110-d8d3ea5cf151965f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 1.1 添加 DNS 解析
然后是添加解析，我域名是在腾讯云买的，所以直接在腾讯云那添加解析了。阿里那买的域名可以在阿里那添加解析，当然，去 DNSPod 那也行。但是我发现我去 DNSPod 可以直接跳回腾讯云那添加解析。

>[https://www.dnspod.cn/](https://www.dnspod.cn/)

我添加的解析如下,供参考，记得把 username 改成你自己的。
>@    A    185.199.109.153
>@    A    185.199.110.153
>www    CNAME    username.github.io.

![](https://upload-images.jianshu.io/upload_images/2989110-ab81012e9f87f327.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

A 记录的 ip 地址可以在下面中选择
>185.199.108.153
>185.199.109.153
>185.199.110.153
>185.199.111.153

### 1.2 修改设置
添加完成后进入库的设置，找到 GitHub Pages ，如果能看到类似  **Your site is published at https://lbjheiheihei.xyz/** 这样的文字，说明就搞定了。

Enforce HTTPS 最好勾选上，GitHub 提供的这个可以直接让你的网站从 HTTP 升级到 HTTPS，非常赞。
![](https://upload-images.jianshu.io/upload_images/2989110-4584f568e75f714f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

过 10 分钟后访问一下你的域名，看看能不能访问到，如果是 HTTPS 的，而且能访问到，那就搞定了。

其实也不用等 10 分钟这么久，很快的。

## 2 相关说明

事实上,下面这样的两条 CNAME 也行，但是好像开启不了 HTTPS.
>@    CNAME    username.github.io.
>www    CNAM    username.github.io.

也就是说，目前你访问 [https://weijunzii.github.io](https://weijunzii.github.io) 会跳转到 [https://lbjheiheihei.xyz/](https://lbjheiheihei.xyz/)

我是参考了知乎上一篇文章写的教程后才成功绑定的，所以这里给出链接。
>[https://www.zhihu.com/question/31377141/answer/103056861](https://www.zhihu.com/question/31377141/answer/103056861)

GitHub 官方也有相关的说明，所以也给出链接：

[https://github.blog/2018-05-01-github-pages-custom-domains-https/](https://github.blog/2018-05-01-github-pages-custom-domains-https/)

[https://help.github.com/en/articles/setting-up-an-apex-domain](https://help.github.com/en/articles/setting-up-an-apex-domain)