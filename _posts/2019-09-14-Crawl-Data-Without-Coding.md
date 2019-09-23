---
layout: post
title: '不写代码爬数据-0'
subtitle: '这是开始，也可能只有开始'
date: 2019-09-14
author: 伪君子
categories:
cover: ''
tags: 不写代码爬数据 WebScraper
---

* content
{:toc}
## 0 课前准备

1.谷歌浏览器，这个[去这里下载](https://www.google.cn/chrome/index.html)
2.Web Scraper , 能科学上网的直接[去这里下载安装](https://chrome.google.com/webstore/detail/jnhgnonknehpejjnehehllkliplmbmhn)，不能科学上网的就到百度网盘
> 链接: [https://pan.baidu.com/s/1sh7s-PZdkk-ppUFGouyzEg](https://pan.baidu.com/s/1sh7s-PZdkk-ppUFGouyzEg)
> 提取码: 3d9h

安装的时候如果出现问题，可以[查看这个](http://www.iwebscraper.com/webscraper-install/)

安装完成之后，能在谷歌浏览器上看到 Web Scraper
![Web Scraper](http://img.lbjheiheihei.xyz/FgjqWpzT_r0ucyzi1Itw3oePb2jU)
## 1 打开 web scraper

打开 Web Scraper 其实很简单, 按 F12 或者点击鼠标右键，然后点击检查
![点击鼠标右键，然后点击检查](http://img.lbjheiheihei.xyz/FvLFSZB4fYbNFYJHgnEWaTuzM2xf)
如果你的界面是下图这样，左右分开的，那么需要调整一下
![左右分开](http://img.lbjheiheihei.xyz/FuoQruikSjIqVzAj5ld7nIS1AgKk)
先点击右上角那三个点，然后点击 Dock side 里面的 Dock to bottom
![Dock to bottom](http://img.lbjheiheihei.xyz/FhwHZ9jxB9bUc7c27_e_isaRzDx-)
当你能看到 Web Scraper 这个的时候，点击一下就能打开了。
![Web Scraper](http://img.lbjheiheihei.xyz/Fi_VESQ43k_G0BL7zF3gg0zrYZJD)

## 2 爬取某乎上的数据

[https://www.zhihu.com/people/excited-vczh/answers](https://www.zhihu.com/people/excited-vczh/answers)

进入上面这个链接，打开web scraper

先点击 Create new sitemap，然后点击 Create Sitemap，然后会跳转到一个新的界面
![Create Sitemap](http://img.lbjheiheihei.xyz/Fh225qjq-LTmoQU1fCQiMYlK2-3L)
跳转到这个新的界面之后，网页的链接，也就是我刚刚给出的链接填到 Start URL 里面

Sitemap name 填自己能记住的词，英文+数字都可以，只能用英文开头。

然后点击 Create Sitemap
![Create Sitemap](http://img.lbjheiheihei.xyz/Fl3K62SXppjQzBEHeaz8Mk6arpWE)
点击 Create Sitemap之后会跳转到一个新的界面，然后点击 Add new selector
![Add new selector](http://img.lbjheiheihei.xyz/FhRpZYqeAuNlGJKOyXEGfdlPjCaO)
然后会跳转到一个新的界面，
![Select](http://img.lbjheiheihei.xyz/FpgiVud4DQ_GIcaT74VuUyorSdg8)
这里先选择标题这个数据，先点击 Seletor 这一行里面的 Select 
然后会出现下图这一个东西，需要的就是它。
![Select](http://img.lbjheiheihei.xyz/FnAEkRM4cxkAB2V-7PkK59ej1qJ9)
在页面上用鼠标点击两个标题，然后就能选中所有的标题，接着点击一下 Done selecting
![Done selecting](http://img.lbjheiheihei.xyz/FoAYYX6XzCOO7eotO1HI1wxs6Ow_)

![Select](http://img.lbjheiheihei.xyz/Fi6yOcO0NCbIKsGrseSWYCYbBahm)

接下来的就是在 id 那填个名字，勾选一下 Multiple ，接着点击 Save selector。
![Save selector](http://img.lbjheiheihei.xyz/FmTkSeIfBgYH2KT3NqfyalJBMDev)
Save selector 之后会跳转到一个新的界面，点击一下 sitemap 。。。，然后再点击 Scrape
![Scrape](http://img.lbjheiheihei.xyz/FvgSZkqo9_L7Zt45bl-GXxERg0io)
点击 Start scraping，然后等它自己运行
![Start scraping](http://img.lbjheiheihei.xyz/FuKvJ9Nxbm2fQq2fUopl_KPavCGW)
运行完成之后，就能看到一个 refresh，点击一下，
![refresh](http://img.lbjheiheihei.xyz/FhwZM2IAvYM_7O5W64Y5ecOlg9AN)
就能看到数据
![数据](http://img.lbjheiheihei.xyz/FszhPdwkbwcLqlSGaut5KKFOaqkO)
点击 sitemap 。。。，然后再点击 Export data as CSV，
![Export data as CSV](http://img.lbjheiheihei.xyz/FoUaFkXqlHB34FEwVbZfYrjvFGEs)
然后点击 Download now 就能下载到爬取的数据了。
![Download](http://img.lbjheiheihei.xyz/FqAuTXdcEjz_kv9LsHPitffjV6XL)
打开看一下下载回来的文件
![查看数据](http://img.lbjheiheihei.xyz/FvPKeT8mdCMDMHMXYxYXoCwIhooY)


## 3 爬取更多页
上面的只有一页，对不对，可以有更多页

先来看一下页面链接的规则，
>answers?page=1
>answers?page=2
>answers?page=3
>answers?page=4

这个是有顺序的

![页面链接](http://img.lbjheiheihei.xyz/FqYVjjG4jPe_hrgzom-WXfdZBKJF)
我们点击一下 sitemap 。。。 ，然后点击 Edit metadata
![Edit metadata](http://img.lbjheiheihei.xyz/FlX3UQmiE4lkopU0Ln7I8O2Yc4Ui)
进来之后，我们可以添加多个 Start URL，点击那个 【+】就可以了

Save sitemap ，然后去 Scrape
![Scrape](http://img.lbjheiheihei.xyz/Fp0vnl-0_vdqJSxVBjLIf08-rfNF)
数据是多了，没错，但是一个一个填写链接，直接就能填写到自闭，对不对。
![数据](http://img.lbjheiheihei.xyz/FoA4_BWnPhENnkGiIyHKBIeNWX6R)

Edit metadata，进入去修改一下，把链接改成 https://www.zhihu.com/people/excited-vczh/answers?page=[1-3]

然后保存，运行一下看看。
![Edit metadata](http://img.lbjheiheihei.xyz/FvXNFf6cHW279FhtJrNHzxYn9pe3)

##  4 爬取更多的数据
显然，上面的数据只有一个 title，没有回答的内容，也没有点赞/评论数

所以得加上，再创建一个 sitemap，或者直接把刚刚的 title 删掉，回到最初的起点,Add new selector
![Add new selector](http://img.lbjheiheihei.xyz/FhRpZYqeAuNlGJKOyXEGfdlPjCaO)
进来之后点击 Type 那一行，选择 Element
![Element](http://img.lbjheiheihei.xyz/FvBlGN_6kb_-_4pfckgIZYEiskOo)
然后点击 select，去选中整个回复的 div，先点击一个，然后在点击一个，web scraper 会自动把同类型的选中，然后 Done selecting
![Done selecting](http://img.lbjheiheihei.xyz/FrSuSQIwwm3XeeIIPadwH887B6WT)
随便命个名，勾选 Multiple，然后 Save。
![Save](http://img.lbjheiheihei.xyz/FgSpcPXK6W6cJ8ltvmjYxrvs6PrG)
![过程](http://img.lbjheiheihei.xyz/FomfY2Us6ra7KuvnLFKclNGu9sZb)

接着就是点击刚刚创建的 selector，进入里面
![进入刚刚创建的 selector](http://img.lbjheiheihei.xyz/FhoBkkxlZWtXSpcrB3B8R7JCtwTS)
进来之后还是 Add new selector
![Add new selector](http://img.lbjheiheihei.xyz/FucvDZl4pT0ebUxUp0ftFg42LzLJ)
这一个不用勾选 Multiple
![问题](http://img.lbjheiheihei.xyz/Fr1FsXJtTsviUkZewcSr81tFKpcY)
![](http://img.lbjheiheihei.xyz/FpGEiyg5qPsXrxNayHhxKRVRRzZn)
阅读全文是需要点击的，那么 Type 就选择 Popup Link，一样不用勾选 Multiple，然后 Save。
![点击阅读全文](http://img.lbjheiheihei.xyz/FmDSHK24OeSej8HqFyzdLqOrLLzx)
然后是回复
![回复](http://img.lbjheiheihei.xyz/Fi92sR-VNuCsWZR9CG31Vm8hnmrd)
接着是发布时间
![发布时间](http://img.lbjheiheihei.xyz/FoLiblG3xcFkrZS2WsWXjkDmwkA-)
赞同数，这里需要在 Regex 里面填写 [1-9]\d*，这里是个正则。
![点赞数](http://img.lbjheiheihei.xyz/FpLF-4csKJGf0-c-9W4hfawqsMR3)
评论数据，同样用正则提取数字。
![评论数](http://img.lbjheiheihei.xyz/FmnHPuCq49j9_ABQPZ-lML-vjkMy)
整体的样子
![整体](http://img.lbjheiheihei.xyz/FmfP9LEHI0WNiCxD_5VHbzwsLqVH)
我们可以看一下整体的结构，点击 Sitemap 。。。 然后点击 Selector graph
![Selector graph](http://img.lbjheiheihei.xyz/FnDOGofKU3oST76O3vjV-1N9J2pc)
一个一个点开之后是这样样子的
![Selector graph](http://img.lbjheiheihei.xyz/Fgos5DV7uWOYEyyvixsB9vl06G_W)

## 5 相关说明
显然，你们爬取下来的数据都是乱序的，有解，安装个东西就可以了。

[电脑上安装 CouchDB](http://www.iwebscraper.com/install-couchdb/)，按照这个教程来就可以了。

有作业的，爬 100 条数据，[http://kj.idcby.com/Gradingrel.aspx?mid=5&ID=190103030001](http://kj.idcby.com/Gradingrel.aspx?mid=5&ID=190103030001)，爬完之后，截图发微信群里打卡。