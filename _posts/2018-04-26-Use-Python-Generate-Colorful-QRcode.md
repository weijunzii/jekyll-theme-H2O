---
layout: post
title: '用 Python 生成彩色动态二维码'
subtitle: '彩色动态二维码了解一下~'
date: 2018-04-26
author: 伪君子
categories: 技术，编程
cover: ''
tags: Python 有趣的 二维码

---

* content
{:toc}
#  0  前言

***



最近在忙别的事情，也没有怎么更新，我的错。
下面来介绍一下怎么通过一个有趣的库生成二维码，生成彩色的，动态的二维码都不是事。
#  1  环境说明

***



Win10 系统下 Python3，编译器是 Pycharm，需要安装 MyQR 这个库。

 Pycharm 安装第三方库的方法。
![](http://upload-images.jianshu.io/upload_images/2989110-eba62bb3986f0d64.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/2989110-c5f3b215895c51cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Pip 安装第三方库的方法
```python
pip install myqr
```

myqr 可以替换成你想安装的第三方库
#  2  相关代码

***



###  2.1 跑代码
先导入 MyQR 这个库

<pre><code class="language-python">from MyQR import myqr</code></pre>

再加上需要的代码

<pre><code class="language-python">version, level, qr_name = myqr.run(
    words='dhb cdfb64%vjk',  # 不支持中文，支持 0~9,a~z, A~Z 以及常见的常用英文标点符号和空格
    version=2,  # 版本，从 1至 40
    level='H',  # 纠错等级，范围是L、M、Q、H，从左到右依次升高
    picture='4e.jpg',  # 文件要放在目录下
    colorized=True,   # True 为彩色，False 为黑白
    contrast=1.0,  # 对比度
    brightness=1.0,  # 亮度
    save_name='1d6.bmp',  # 命名随便都行，格式可以是 jpg,png,bmp,gif
    save_dir="F:\二维码"  # 路径要存在
)</code></pre>

words 那里就是你想让二维码被识别出来后的文字（好气哦，居然不支持中文）

picture 那里说文件要放在目录下的意思就是，代码在哪个目录，图片就要在哪个目录。

就如我代码文件在 **F:\PycharmProjects\untitled** 这，那我的图片也要在这个目录。
![](https://upload-images.jianshu.io/upload_images/2989110-ca5cb08443f8a13a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
colorized 那可以选择 True 或者 False，True 为彩色，False 为黑白。

save_name 那可以命名，也可以不命名。

如果命名，格式可以是 .jpg .png .bmp .gif；如果不命名，会在文件名后面加上 _qrcode ,生成如 1d_qrcode.gif、4e_qrcode.png 这样的文件。（文件如果是 .gif的, 那生成的文件名也要是 .gif 的）

save_dir 是保存文件的目录，如果想保存在当前文件的目录下，可以删掉或者注释掉这一句；如果想保存在别的地方，请确认目录存在，不然会报错。

看看我生成的二维码
![GavinThomas](https://upload-images.jianshu.io/upload_images/2989110-991a2b4e4336c27c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.2  命令行
先 cd 到图片的目录下

<pre><code class="language-python">C:\Users\ASUS> cd F:\二维码
C:\Users\ASUS>F:
F:\二维码></code></pre>

然后输入 **myqr 666 -p 下载.png -c**

myqr 就是库的名字；666 是你想让别人扫描二维码看见的文字；-p 是参数；下载.png 是图片的名字；-c 也是参数，生成彩色的二维码。

具体过程如下图
![](https://upload-images.jianshu.io/upload_images/2989110-42e61e3dba7d4fac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

效果就是在 **F:\二维码** 这生成了 **下载_qrcode.png** 这个二维码图片，扫描该二维码，识别出来的是 **666** 这 3 个字符。
![下载_qrcode.png](https://upload-images.jianshu.io/upload_images/2989110-16380c692c77b80e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#  3  相关说明

***



MyQR 的 GitHub 链接：[https://github.com/sylnsfar/qrcode/blob/master/README-cn.md](https://github.com/sylnsfar/qrcode/blob/master/README-cn.md)

其实有 Windows可以用的 exe 版：[https://github.com/sylnsfar/qrcode_win](https://github.com/sylnsfar/qrcode_win)  （不过我没试）

也有封装好的网页版：[http://www.amazing-qrcode.com/](http://www.amazing-qrcode.com/)