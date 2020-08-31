---
permalink: 2018/06/29/Add-Gitalk-In-Jekyll-Theme-H2O.html
title: jekyll-theme-H2O 配置 gitalk
subtitle: 感谢
cover: ""
author: 伪君子
tags: 网站 博客
date: 2018-06-29
layout: post
categories: 技术，编程
---

* content
{:toc}
#  0  前言

前提是 [搭建了博客](ttps://weijunzii.github.io/2018/04/02/Use-github-Set-Up-The-Blog.html)，使用的主题是 [jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O/) 这个主题。其余的可以借鉴，但不一定完全适用。

Gitalk 是一个评论系统，在个人博客里添加了之后就可以很简便的进行评论和回复了。



#  1  注册 GitHub Application

首先要注册一下 GitHub Application，
>[https://github.com/settings/applications/new](https://github.com/settings/applications/new)

<img data-src="https://img.lbjheiheihei.xyz/FgVglVfmjNuqI0ivrTS_Ap3_dTWR" class="lazyload"  alt="注册 GitHub Application" title="注册 GitHub Application">

注册完就会有 Client ID 和 Client Secret

<img data-src="https://img.lbjheiheihei.xyz/FtOV3fKR_1TLDD_SBT5rcyNT2gl0" class="lazyload"  alt="Client ID 和 Client Secret" title="Client ID 和 Client Secret">

#  2  配置 ``_config.yml``

在 comments 那添加
```html
  gitalk: true
  gitalk_clientID: 'Client ID'
  gitalk_Secret: 'Client Secret'
  gitalk_repo: '用户名.github.io'
  gitalk_owner: '用户名'
  gitalk_admin: '用户名'
  distractionFreeMode: true
```
是在 comments 下面那添加，不要搞错地方。
<img data-src="https://img.lbjheiheihei.xyz/FpoEEI2fr-GmBdwt-qpmPGQHJfKx" class="lazyload"  alt="_config.yml" title="_config.yml">

#  3  配置 ``post.html``
文件的位置在 ``_layouts\post.html``
##  3.0  在 ``<html>`` 这个标签下添加
在 ```<html>``` 这个标签下加上这两行
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>
```

就像这样
<img data-src="https://img.lbjheiheihei.xyz/FqbcvctPsnjKgWr3US7e0XyJ8reC" class="lazyload"  alt="post.html 添加 css 和 js" title="post.html 添加 css 和 js">

##   3.1  在`` footer.html``里添加
```html
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>
```
如图所示，位置不要搞错

<img data-src="https://img.lbjheiheihei.xyz/Fo-EP9Ul3dGiBLNke2DupD6A-RLg" class="lazyload"  alt="footer.html 里添加 js" title="footer.html 里添加 js">

##  3.2  在``disqus``后面添加
如下图所示
<img data-src="https://img.lbjheiheihei.xyz/Fhk7XNUJtgR-loPTRlYh8QbI06Et" class="lazyload"  alt="添加 Gitalk" title="添加 Gitalk">

关于 ``post.html`` 这部分的修改可以看一下我的[修改](https://github.com/weijunzii/weijunzii.github.io/commit/0ba47d4b3b437d73f7079bb9efba181f172520d7)

最近发现页面 title 的长度超过 50 个字符之后就会出错，表现为 Gitalk 报错，评论出不来。

<img data-src="https://img.lbjheiheihei.xyz/Fn9KSHMy7MRR5LIpcBQajhqPtXSy" class="lazyload"  alt="报错" title="报错">

这部分的修改看[这里](https://github.com/weijunzii/weijunzii.github.io/commit/5af2e4af7390b9d3d4b6d70966a860db42dc095b)，主要就是加了 md5.min.js 个文件，接着引用 md5.min.js  文件，然后把 id: location.pathname, 修改为 id: md5(window.location.pathname)，感谢[@LouNlay ](https://github.com/lounlay) 的提醒和帮助。

#  4  开 issues
进入博客，点击设置
<img data-src="https://img.lbjheiheihei.xyz/FjmD6kXSG2AkAl1kNwFKosk0Wu_g" class="lazyload"  alt="设置" title="设置">

进去后勾选一下 issues 就搞定了。
<img data-src="https://img.lbjheiheihei.xyz/Fm2XumTfuGSYj6g2VRKvcMBUU5Y-" class="lazyload"  alt="issues" title="issues">

再去看一下你博客里面的文章，如果说出现了评论框，那就是成功了。
<img data-src="https://img.lbjheiheihei.xyz/FtrCowC4nwzxAhcPWodhzLrqxmU7" class="lazyload"  alt="gitalk 评论框" title="gitalk 评论框">

#  5 相关说明

参考了这篇文章才实现的：[https://tea9.github.io/2018/06/24/gitali_config.html](https://tea9.github.io/2018/06/24/gitali_config.html)

文章作者写的说明：[http://note.youdao.com/publicshare/?id=6ea132ba501b49b2928125a694cc9ad9#/](http://note.youdao.com/publicshare/?id=6ea132ba501b49b2928125a694cc9ad9#/)

使用的主题是：[jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O/) 

感谢两位作者~~

因为某种原因，小标题那里不能详细地写出在哪添加代码，一写出就编译不了这篇文章，所以把文章复制到[微信公众号了](https://mp.weixin.qq.com/s/e_ABP7TLAw5AmXDgPOLkkg)