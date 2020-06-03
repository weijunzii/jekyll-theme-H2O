---
permalink: /2018/05/27/Install-Scrapy-In-Window.html
title: 在 Windows 下安装 Scrapy
subtitle: Scrapy 了解一下~
cover: ""
author: 君子
tags: 编程 爬虫 pip Python
date: 2018-05-27T00:00:00.000Z
layout: post
categories: 技术，编程
---

* content
{:toc}
#  0  前言


因为要学一点爬虫，我要安装 Scrapy 这个库，直接用 Pycharm 安装就报错， pip 也不行，所以要把 Scrapy 依赖的库安装好，然后再安装 Scrapy 。也就是说，lxml、pyOpenSSL、Twisted、pywin32 这些基本库都要安装好。

![直接安装 Scrapy 报错](https://img.lbjheiheihei.xyz/Fq88Xu9tw0VomgBOYM4Owe9LQOwU "直接安装 Scrapy 报错")

这次的安装环境是python3.6， 电脑是 32 位，主要用 Pycharm 安装。

#  1  安装

###  安装 lxml
用 pycharm 安装比较简单一点
![安装 lxml](https://img.lbjheiheihei.xyz/FpldVEB4JA7dVTu7Af6u5WnKn19w "安装 lxml")
也可以 cmd 内输入

 <pre><code class="language-python">pip install lxml</code></pre> 

先 Win键+R，再输入 cmd ，回车
![cmd](https://img.lbjheiheihei.xyz/Fgp2rwS-n3bWvdnireFGRUH45AE0 "")
进来后输入 

<pre><code class="language-python">pip install lxml</code></pre>

![pip install lxml](https://img.lbjheiheihei.xyz/Fkqs95eykqhJy799GdDmEpfGVCJx "pip install lxml")

如果不行，则去下面的网站下载。
>https://pypi.org/project/lxml/#files
>https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml

比如我这台电脑是 Python3.6，32位的就下载 **lxml-4.2.1-cp36-cp36m-win32.whl**
![lxml](https://img.lbjheiheihei.xyz/Fr7LVqTe3CuZ0IT4Xcx53wgMFSWE "lxml")
进入 cmd，然后 cd 到文件的路径下，接着就是 

<pre><code class="language-python">pip install lxml-4.2.1-cp36-cp36m-win32.whl</code></pre>

命令后面那一部分要和文件名保持一致，也就是 pip install 文件名.whl回车，等一会就安装好了
![](https://upload-images.jianshu.io/upload_images/2989110-0afcf74fd9798752.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  安装 pyOpenSSL
用 pycharm 安装或者 

<pre><code class="language-python">pip install pyOpenSSL</code></pre>

![pip install pyOpenSSL](https://img.lbjheiheihei.xyz/FtIDHzMNos14LWu5FbolAKsnJiHI "pip install pyOpenSSL")
>https://pypi.org/project/pyOpenSSL/#files

如果还不行，就下载图中的这个，然后进入 cmd 用 pip 安装 whl文件
![](https://upload-images.jianshu.io/upload_images/2989110-9b350150935e0032.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  安装 Twisted
我这里用 Pycharm 安装不了，pip install Twisted 也不行，直接去下载 whl 文件回来安装
>https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted
>https://pypi.org/project/Twisted/#files

![安装 Twisted,报错](https://img.lbjheiheihei.xyz/FpeCLvtb2s23syu3BoEGwZvsR3hv "安装 Twisted,报错")
电脑是 python3.6 ,32 位的电脑，所以下载的是 Twisted-18.4.0-cp36-cp36m-win32.whl
![Twisted-18.4.0-cp36-cp36m-win32.whl](https://img.lbjheiheihei.xyz/FjY6gOE5Dwk60-sLd5V1k5v0D1cK "Twisted-18.4.0-cp36-cp36m-win32.whl")
进入 cmd ，cd 到文件目录下，输入命令 

<pre><code class="language-python">pip install Twisted-18.4.0-cp36-cp36m-win32.whl</code></pre>

命令后面那一部分要和文件名保持一致，也就是 pip install 文件名.whl,回车，等一会就安装好了。
![pip install](https://img.lbjheiheihei.xyz/FskxYSGLd-7Ja6aGK51XZ6TtANs3 "pip install")

###  安装 pywin32
pycharm 安装或者 pip install pywin32
>https://sourceforge.net/projects/pywin32/files/pywin32/Build%20220/

![pycharm 安装 pywin32](https://img.lbjheiheihei.xyz/FoO8xr6wPjlX6oDGzVOZbKNDd2J2 "pycharm 安装 pywin32")
如果不行，下载 exe 文件，下载回来直接运行一下就好。
![下载 exe 文件](https://img.lbjheiheihei.xyz/FrLtQxr1CgUMYir9FxEIHnN78eUo "下载 exe 文件")
最后就是安装 Scrapy 了，在 pycharm 里面安装
![安装 Scrapy](https://img.lbjheiheihei.xyz/Fq5H1_uITjTRSa0c-2-Iy8loi8P1 "安装 Scrapy")
直接用 pip 安装

<pre><code class="language-python">pip install Scrapy</code></pre>

![pip install Scrapy](https://img.lbjheiheihei.xyz/FotQ9BVgY360_44OYbFpGMz8-JGx "pip install Scrapy")

# 2 说明


听说用 Anaconda 安装可简单了，一个命令就搞定了，可惜我懒得试了。

<pre><code class="language-python">conda install Scrapy</code></pre>

Anaconda下载链接：https://www.anaconda.com/download/
