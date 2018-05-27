---
layout: post
title: '在 Windows 下安装 Scrapy'
subtitle: 'Scrapy 了解一下~'
date: 2018-05-27
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程 有趣的 网站 孩子

---

* content
{:toc}
#  0  前言

***

因为要学一点爬虫，我要安装 Scrapy 这个库，直接用 Pycharm 安装就报错， pip 也不行，所以要把 Scrapy 依赖的库安装好，然后再安装 Scrapy 。也就是说，lxml、pyOpenSSL、Twisted、pywin32 这些基本库都要安装好。
![](https://upload-images.jianshu.io/upload_images/2989110-da7da32849320884.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这次的安装环境是python3.6， 电脑是 32 位，主要用 Pycharm 安装。
#  1  安装

***

###  安装 lxml
用 pycharm 安装比较简单一点
![](https://upload-images.jianshu.io/upload_images/2989110-a5b7cc59bf45f1a2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
也可以 cmd 内输入  
```
pip install lxml
```

先 Win键+R，再输入 cmd ，回车
![](https://upload-images.jianshu.io/upload_images/2989110-f1a6ed1b8e6eb323.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进来后输入 
```
pip install lxml
```

![](https://upload-images.jianshu.io/upload_images/2989110-dc4fd9fde090f009.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果不行，则去下面的网站下载。
>https://pypi.org/project/lxml/#files
>https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml

比如我这台电脑是 Python3.6，32位的就下载 **lxml-4.2.1-cp36-cp36m-win32.whl**
![](https://upload-images.jianshu.io/upload_images/2989110-0af9db77e53dea2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入 cmd，然后 cd 到文件的路径下，接着就是 
```
pip install lxml-4.2.1-cp36-cp36m-win32.whl
```
命令后面那一部分要和文件名保持一致，也就是 pip install 文件名.whl回车，等一会就安装好了
![](https://upload-images.jianshu.io/upload_images/2989110-0afcf74fd9798752.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  安装 pyOpenSSL
用 pycharm 安装或者 
```
pip install pyOpenSSL
```
![](https://upload-images.jianshu.io/upload_images/2989110-615ca94a9c4fa06e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
>https://pypi.org/project/pyOpenSSL/#files

如果还不行，就下载图中的这个，然后进入 cmd 用 pip 安装 whl文件
![](https://upload-images.jianshu.io/upload_images/2989110-9b350150935e0032.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  安装 Twisted
我这里用 Pycharm 安装不了，pip install Twisted 也不行，直接去下载 whl 文件回来安装
>https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted
>https://pypi.org/project/Twisted/#files

![](https://upload-images.jianshu.io/upload_images/2989110-62b238a836ff2052.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
电脑是 python3.6 ,32 位的电脑，所以下载的是 Twisted-18.4.0-cp36-cp36m-win32.whl
![](https://upload-images.jianshu.io/upload_images/2989110-0a59b9bf72afc001.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入 cmd ，cd 到文件目录下，输入命令 
```
pip install Twisted-18.4.0-cp36-cp36m-win32.whl
```
命令后面那一部分要和文件名保持一致，也就是 pip install 文件名.whl,回车，等一会就安装好了。
![](https://upload-images.jianshu.io/upload_images/2989110-9fc893f112f44535.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  安装 pywin32
pycharm 安装或者 pip install pywin32
>https://sourceforge.net/projects/pywin32/files/pywin32/Build%20220/

![](https://upload-images.jianshu.io/upload_images/2989110-f4c3162206975039.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果不行，下载 exe 文件，下载回来直接运行一下就好。
![](https://upload-images.jianshu.io/upload_images/2989110-6675c34333c3b25f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
最后就是安装 Scrapy 了，在 pycharm 里面安装
![](https://upload-images.jianshu.io/upload_images/2989110-03fdd539a024746f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
直接用 pip 安装

```
pip install Scrapy
```

![](https://upload-images.jianshu.io/upload_images/2989110-0302b021563b4ce5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 2 说明

***

听说用 Anaconda 安装可简单了，一个命令就搞定了，可惜我懒得试了。

```
conda install Scrapy
```

Anaconda下载链接：https://www.anaconda.com/download/

本次的参考资料是小怪大佬的知识星球【scrapy 爬虫课程】里的资料，这里就不放出来了。
