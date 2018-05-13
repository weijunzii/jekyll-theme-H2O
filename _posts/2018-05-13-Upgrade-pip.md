---
layout: post
title: 'pip 升级出错的解决办法'
subtitle: 'pip 升级老是出错该怎么办？进来了解一下~'
date: 2018-05-13
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程 python

---

* content
{:toc}


#  0 前言

***

这几天公众号后台有人问 pip 升级不了，试过了一些方法，还是不行，在 PyCharm 那升级不了， cmd 那升级也不行，会回退。

#  1 解决方法

***

###  1.0  思路
正常来说，输入下面两个命令的其中一个

<pre><code class="language-python">python -m pip install -U pip
python -m pip install --upgrade pip</code></pre>

就可以升级。

事实上，输入python -m pip install -U pip 和
python -m pip install --upgrade pip 后，说是成功升级了，可是查看 pip 版本，发现 pip 还是没有升级到 10.0.1 版本。

![cmd_2018-05-12_16-25-35.png](https://upload-images.jianshu.io/upload_images/2989110-049cda84a736477b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
面对这种情况，可以尝试一下

<pre><code class="language-python">easy_install --upgrade pip</code></pre>

如下图所示，可以看到 pip 的版本已经升级到 10.0.1 了。

![cmd_2018-05-12_16-36-09.png](https://upload-images.jianshu.io/upload_images/2989110-9c64eac04066023e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
###  1.1  实践
先 Win 键加 R，在弹出框内输入 cmd ，然后回车

![explorer_2018-05-13_11-36-14.png](https://upload-images.jianshu.io/upload_images/2989110-c627a6e720cce601.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在下面两个命令都不起作用的情况下，

<pre><code class="language-python">python -m pip install -U pip
python -m pip install --upgrade pip</code></pre>

使用这个命令

<pre><code class="language-python">easy_install --upgrade pip</code></pre>

直接复制到 cmd 然后回车，很快就完成升级了。

![66665.gif](https://upload-images.jianshu.io/upload_images/2989110-614794e37acd2b07.gif?imageMogr2/auto-orient/strip)

如果想确定升级成功没，输入下面这个命令

<pre><code class="language-python">pip --version</code></pre>

然后就可以看到版本信息了。
![cmd_2018-05-13_11-45-03.png](https://upload-images.jianshu.io/upload_images/2989110-73b30c8812632320.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  2  补充说明

***

已经在 Win10 64 位和 Win7 32 位的电脑上试验过了，都可以正常升级 pip ，可以说是完美地解决了问题。

如果在学习过程中遇到问题，可以截图 + 发代码询问。要是我会，会用最快的速度解决你的问题；要是我弄了好久都不行，那我们一起哭吧。（最好不要用手机拍照，看着就难受。）

去我微信公众号后台回复【Python实战】，有个小惊喜~

![](https://upload-images.jianshu.io/upload_images/2989110-5e96f3a9a9204f3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)