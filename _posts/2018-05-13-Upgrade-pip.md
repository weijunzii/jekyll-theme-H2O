---
permalink: /2018/05/13/Upgrade-pip.html
title: pip 升级出错的解决办法
subtitle: pip 升级老是出错该怎么办？进来了解一下~
cover: ""
author: 伪君子
tags: 编程 Python pip
date: 2018-05-13T00:00:00.000Z
layout: post
categories: 技术，编程
---

* content
{:toc}


#  0 前言


这几天公众号后台有人问 pip 升级不了，试过了一些方法，还是不行，在 PyCharm 那升级不了， cmd 那升级也不行，会回退。

#  1 解决方法


###  1.0  思路
正常来说，输入下面两个命令的其中一个

<pre><code class="language-python">python -m pip install -U pip
python -m pip install --upgrade pip</code></pre>

就可以升级。

事实上，输入python -m pip install -U pip 和
python -m pip install --upgrade pip 后，说是成功升级了，可是查看 pip 版本，发现 pip 还是没有升级到 10.0.1 版本。

![pip 版本](https://img.lbjheiheihei.xyz/FlrqSFz-gyZmHu7IU2E277g4GDb- "pip 版本")
面对这种情况，可以尝试一下

<pre><code class="language-python">easy_install --upgrade pip</code></pre>

如下图所示，可以看到 pip 的版本已经升级到 10.0.1 了。

![pip 版本](https://img.lbjheiheihei.xyz/FhDPLzxxEEX5Ees8Z-JmNFvrWwG4 "pip 版本")

###  1.1  实践
先 Win 键加 R，在弹出框内输入 cmd ，然后回车

![cmd](https://img.lbjheiheihei.xyz/FrZLoBWp1BgQb1xDcxjDPo_w8fOf "cmd")
在下面两个命令都不起作用的情况下，

<pre><code class="language-python">python -m pip install -U pip
python -m pip install --upgrade pip</code></pre>

使用这个命令

<pre><code class="language-python">easy_install --upgrade pip</code></pre>

直接复制到 cmd 然后回车，很快就完成升级了。

![pip 升级](https://img.lbjheiheihei.xyz/Flo8gHM3MFDQK1btMns9jjylCtI- "pip 升级")

如果想确定升级成功没，输入下面这个命令

<pre><code class="language-python">pip --version</code></pre>

然后就可以看到版本信息了。
![查看 pip 版本](https://img.lbjheiheihei.xyz/Fjn3pfu2jEWjJKHAZ0hBMRpys1By "查看 pip 版本")

#  2  补充说明


已经在 Win10 64 位和 Win7 32 位的电脑上试验过了，都可以正常升级 pip ，可以说是完美地解决了问题。

如果在学习过程中遇到问题，可以截图 + 发代码询问。要是我会，会用最快的速度解决你的问题；要是我弄了好久都不行，那我们一起哭吧。（最好不要用手机拍照，看着就难受。）
