---
permalink: /2018/07/04/Download-Jekyll-And-Use-It.html
title: 下载 Jekyll，并使用它在本地搭建一个博客
subtitle: 搭个博客可还行
cover: ""
author: 君子
tags: Jekyll 博客
date: 2018-07-04
layout: post
categories: null
---

* content
{:toc}
#  0 前言
之前搭建的博客是在线的，没有在本地搭建一个进行预览，导致修改样式或者添加功能的时候要频繁的 push ，然后再去查看改得好不好看，这样的体验可以说是非常糟糕了。

所以我下载了 Jekyll 到本地，然后生成本地的博客进行预览，觉得改得还行才 push，这样就比较省事了。

Jekyll 可以将纯文本转换为静态博客网站，简单好用，不需要自己开发大部分功能，甚至直接找模板修改一下就能够使用。

关心博客内容就足够了，别的就直接使用模板吧。

#  1  安装
###  1.1  下载和安装 Ruby
进入网站进行下载
>[http://www.ruby-lang.org/en/downloads/](http://www.ruby-lang.org/en/downloads/)

<img data-src="https://img.lbjheiheihei.xyz/FoM7wa1d4nCe7tAozMTcMQj9RE3w" class="lazyload"  alt="Ruby" title="Ruby">

如果是 Window 的话，直接到下面这个链接下载网站推荐的就好，下图中，网站推荐的就是 Ruby+Devkit 2.4.4-2 (x64) 
>[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)

<img data-src="https://img.lbjheiheihei.xyz/FnmyrxSEvx9VTn8SC1umPuWg3fDS" class="lazyload"  alt="Ruby+Devkit" title="Ruby+Devkit">


双击下载回来的 exe 文件，这里选择 accept 然后 Next。
<img data-src="https://img.lbjheiheihei.xyz/FtzbIKpCEBhRI0bTZhERH4Q2CxSV" class="lazyload"  alt="accept" title="accept">

把默认的文件夹位置修改一下，然后点击 Install
<img data-src="https://img.lbjheiheihei.xyz/FjSgOXYMPc4HgHSL6wNMlJQuCCih" class="lazyload"  alt="Install" title="Install">

这里我是直接 Next，没有勾选 744.4MB 的那个东西，然后点击 Next
<img data-src="https://img.lbjheiheihei.xyz/Fm7sZIRXiPUfgEPg444IcSkol-iY" class="lazyload"  alt="Next" title="Next">

安装也挺快的，安装完后点击一下 Finish
<img data-src="https://img.lbjheiheihei.xyz/FhiTn4hVqq1ylhwHxz8EV91wWHye" class="lazyload"  alt="安装完成" title="安装完成">


###  1.2  下载和安装 RubyGems
RubyGems 是 Ruby 的包管理器，可以类比为你电脑的下载中心。

去下面这个链接下载 zip 文件到本地，然后解压
>[https://rubygems.org/pages/download](https://rubygems.org/pages/download)

<img data-src="https://img.lbjheiheihei.xyz/FrbF_NnJXKWZRZmEqDA3EJ-teRoR" class="lazyload"  alt="RubyGems zip" title="RubyGems zip">

win 键 +R 键，然后输入 cmd ，接着回车。
<img data-src="https://img.lbjheiheihei.xyz/Fpc1bYh41i9abplg3-GF7AESv1z0" class="lazyload"  alt="cmd" title="cmd">

进入 cmd 后，cd 到解压目录，输入命令 ```ruby setup.rb```,安装过程可能有点长
<img data-src="https://img.lbjheiheihei.xyz/FooTkeZERBdASev_zn3s3U6bORfS" class="lazyload"  alt="ruby setup.rb" title="ruby setup.rb">

###  1.3  安装 Jekyll
同样的方法进入 cmd，输入命令 ```gem install jekyll```，搞定
<img data-src="https://img.lbjheiheihei.xyz/FsqY3sykcodbETroTcKpmrMoyyDY" class="lazyload"  alt="gem install jekyll" title="gem install jekyll">

#  2  搭建本地博客

我的博客是使用模板的，这里只说使用模板的

下载这个模板到本地，然后解压
>[https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O)

<img data-src="https://img.lbjheiheihei.xyz/FhT_J1LMwEqfCrCI243WFo1rkQw9" class="lazyload"  alt="jekyll-theme-H2O" title="jekyll-theme-H2O">

接着就是就入 cmd ，然后 cd 到博客模板解压出来的路径下，最后输入命令 ```jekyll server```

<img data-src="https://img.lbjheiheihei.xyz/Fqerc5tr6lx2ZPXGtKrD4WOjtZG-" class="lazyload"  alt="jekyll server" title="jekyll server">

如果发现报错，没有生成想要的本地博客，那就输入命令 ```bundle exec jekyll serve```，然后就发现可以了。（这里我也没搞懂，但是，又不是不能用）
<img data-src="https://img.lbjheiheihei.xyz/Fmm3GfUO-fMyR3WwmBb3Tvu6Q4b1" class="lazyload"  alt="bundle exec jekyll serve" title="bundle exec jekyll serve">

复制 http://127.0.0.1:4000/ 到浏览器打开，就能看见本地的博客了。这里因为我修改过，所以和模板有所不同。
<img data-src="https://img.lbjheiheihei.xyz/FjT2IdxxgZy76PCR-dpNuPCe2-jm" class="lazyload"  alt="本地的博客" title="本地的博客">

#  3  相关说明
如果想把本地的博客发布到网上，那就需要接着折腾了，域名、服务器，还有别的都得搞。推荐使用 GitHub Pages 搭建，原因很简单，方便简单又不花钱。

GitHub Pages：[https://pages.github.com/](https://pages.github.com/)

也可以看看[我搭建博客时的记录](https://weijunzii.github.io/2018/04/02/Use-github-Set-Up-The-Blog.html)，以及我给[博客添加评论系统的记录](https://weijunzii.github.io/2018/06/29/Add-Gitalk-In-Jekyll-Theme-H2O.html)

本文的参考链接[^1]：[http://jekyllcn.com/docs/installation/](http://jekyllcn.com/docs/installation/)

本文的参考链接[^2]：[http://jekyllcn.com/docs/windows/#installation](http://jekyllcn.com/docs/windows/#installation)