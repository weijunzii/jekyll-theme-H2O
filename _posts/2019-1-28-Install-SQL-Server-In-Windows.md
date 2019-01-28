---
layout: post
title: 'Windows 环境下安装 Microsoft SQL Server'
subtitle: '别说难...'
date: 2019-1-28
author: 伪君子
categories:
cover: ''
tags: 安装 SQL
---

* content
{:toc}
#  0 前言
 SQL(Structured Query Language) ，结构化查询语言，是用于访问和处理数据库的标准的计算机语言，简单易学还好用。

常用的数据库包括：MySQL、SQL Server、Access、Oracle 等，其中，Microsoft SQL Server 是微软公司推出的关系型数据库管理系统（DBMS）。

今天的文章主要是来说一下安装 Microsoft SQL Server 的过程，Windows 环境下安装 Microsoft SQL Server。

#  1 下载和安装 SQL Server 2017
因为目前最新的稳定版本是 2017 的，所以我下载的是 2017 的，不是说只能下载这个，有兴趣可以去下载别的版本，这个随意。
>[https://www.microsoft.com/zh-cn/sql-server/sql-server-downloads](https://www.microsoft.com/zh-cn/sql-server/sql-server-downloads)

免费版有两个，SQL Server 2017 Developer 是一个全功能免费版本，可以在非生产环境下用作开发和测试数据库；SQL Server 2017 Express 是 SQL Server 的一个免费版本，适用于桌面、Web 和小型服务器应用程序的开发和生产。

所以我下载的是 SQL Server 2017 Express 版。
![](https://upload-images.jianshu.io/upload_images/2989110-345d13e85cfe82aa.png)
下载完成后开始安装，直接点击基本开始安装。
![](https://upload-images.jianshu.io/upload_images/2989110-5010346a28a160fc.png)
许可条款当然是接受啦
![](https://upload-images.jianshu.io/upload_images/2989110-ebc1773e457d0c3f.png)
安装位置建议是修改成别的盘，不要安装到系统盘，然后点击安装。
![](https://upload-images.jianshu.io/upload_images/2989110-fd159d97ba699023.png)
然后就会开始安装，等就是了，需要的时间有点长。
![](https://upload-images.jianshu.io/upload_images/2989110-606d2686ef13e3fa.png)
安装完成后会显示类似的界面，最好把这个界面截图保存，文字也复制下来保存。


先不急着重启计算机，别关闭这个界面，还需要安装 SSMS 呢
![](https://upload-images.jianshu.io/upload_images/2989110-f0cea5fe336bfac3.png)
#  2 下载和安装 SSMS
SSMS(Microsoft SQL Server Management Studio) 是 SQL Server 的管理工具，这个也是需要安装的，刚刚说了先不急着关掉完成安装 Microsoft SQL Server 后的界面就是因为要安装 SSMS。
![](https://upload-images.jianshu.io/upload_images/2989110-a96904d34119cb64.png)
如果不小心关了也没关系，反正都是进入下面这个链接下载 SSMS 的🌚🌚。
>[https://docs.microsoft.com/zh-cn/sql/ssms](https://docs.microsoft.com/zh-cn/sql/ssms/)

建议下载正式版本，如果喜欢折腾，随意。
![](https://upload-images.jianshu.io/upload_images/2989110-4f926bfad30aca9f.png)

安装其实很简单，双击安装包
![](https://upload-images.jianshu.io/upload_images/2989110-6eb2b7d038f16d4a.png)
进入后点击安装
![](https://upload-images.jianshu.io/upload_images/2989110-4210b6b390c251e0.png)
然后搞定
![](https://upload-images.jianshu.io/upload_images/2989110-f1651b5a7963d046.png)
然后打开 SSMS 就能使用了，直接点击连接就好，默认的服务器名称和身份验证（Windows 身份验证）都不要去动。
![](https://upload-images.jianshu.io/upload_images/2989110-86d249b1395bbc2b.png)

如果无法进入 SQL Server Management Studio，可能是因为安装 SQL Server 和 SSMS 的间隔中你关机了，直接一路安装的话应该是不会出现这样的问题。解决的方法应该是在 SQL Server Management Studio 内注册一个服务器，这里我就不展开讲讲了，自行搜索。

#  3  说明
还记得要你保存的东西吗，安装资源文件夹： C:\Program Files\Microsoft SQL Server\140\SSEI\Resources ，不同版本路径可能不一样，打开后你能看见下面几个文件。
![](https://upload-images.jianshu.io/upload_images/2989110-cc22fbbf9983001b.png)

微软还提供了使用教程，觉得有用的话可以去看看。
>[https://www.microsoft.com/en-us/sql-server/developer-get-started/](https://www.microsoft.com/en-us/sql-server/developer-get-started/)

![](https://upload-images.jianshu.io/upload_images/2989110-44ce0ee32f4c3c6d.png)