---
layout: post
title: '用 Python 把网页转换成 PDF'
subtitle: '还行，比较省事'
date: 2019-05-19
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}


## 0 前言

前段时间有个需求是要把本地的 html 转换成 pdf，一个两个还好说，上千上万的话，只能写代码解决问题。

试了几个，发现 python 实现起来也挺简单的，那就去掉复杂的逻辑，简单说一下怎么实现。

## 1 安装

### 1.1 安装 wkhtmltopdf

> <https://wkhtmltopdf.org/downloads.html>

![下载 wkhtmltopdf](https://upload-images.jianshu.io/upload_images/2989110-2519c7a240938990.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

圈起来的那两个，上面写着 Installer 的是安装包，直接安装就行；下面写着 7z archive 的是压缩包，如果没记错的话，需要下载 7-Zip 才能解压使用。

> <https://www.7-zip.org/>

如果需要，可以把 wkhtmltopdf 加到系统变量 Path 中；如果不需要，把路径记住就好。

### 1.2 安装 pdfkit

先说一下环境，Win10 系统下 Python3，编译器是 PyCharm 。

pdfkit 可以直接用 pip install pdfkit 安装，要是不知道该怎么安装，那还是用 PyCharm 安装吧。

![PyCharm 安装第三方库](http://upload-images.jianshu.io/upload_images/2989110-3b802df41aeff65b.png)

![PyCharm 安装第三方库](http://upload-images.jianshu.io/upload_images/2989110-08e77e3f15cadde7.png)

## 2 代码

代码挺少的，为了能解释清楚，所以是按顺序分开来，用的时候按顺序复制就好。

先导入要用的库 pdfkit，这里加上 time 只是为了计时。

```python
import time
import pdfkit
```

下面这个 wk_path 是 wkhtmltopdf 的路径，config 是配置。

```python
#  wkhtmltopdf 的路径
wk_path = r'E:\Program Files\wkhtmltox\bin\wkhtmltopdf.exe'
config = pdfkit.configuration(wkhtmltopdf=wk_path)
```

url 是需要把 html 转换成 pdf 的那个网页；name 是文件名，文件名这里一定要有后缀名 .pdf，不然得自己手动添加后缀名。

pdfkit.from_url(url, name, configuration=config) 就是开始把 html 转换成 pdf 。

time1 和 time2 是我用来计时的，跑完代码之后会输出用时。

```python
url = "https://lbjheiheihei.xyz/2019/05/07/Spoof-QRcode.html"
name = "lbj.pdf"
time1 = time.time()
pdfkit.from_url(url, name, configuration=config)
time2 = time.time()
print(str(time2 - time1)+" s")
```

![代码截图 + 运行结果](https://upload-images.jianshu.io/upload_images/2989110-226a6039b0caeecb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)代码截图 + 运行结果

我用这个把一个博客的部分文章导成了 PDF，结果如下，用 SumatraPDF 查看能看到目录。

![PDF](https://upload-images.jianshu.io/upload_images/2989110-05cb3ea7ea052391.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

PDF和网页对比如下图，左边是 PDF，右边是 网页。（网页背景颜色原来是白色的，我的浏览器会自动把背景颜色进行替换）

![PDF和网页对比](https://upload-images.jianshu.io/upload_images/2989110-ff4c9fea4dbc466a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 3 相关说明

这样把 html 转换成的 pdf 肯定和网页原来的样子是有差别的，但是把本地的 html 转换成 pdf 还是挺合适我心意的，毕竟解决了我的问题。

如果想把多个 PDF 合并成一个的话，可以使用 PyPDF2，挺好用的。