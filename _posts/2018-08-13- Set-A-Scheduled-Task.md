---
permalink: /2018/08/13/Set-A-Scheduled-Task.html
title: 设置一个计划任务，到了时间就运行代码
subtitle: 大佬带带我
cover: ""
author: 君子
tags: 编程 Python
date: 2018-08-13
layout: post
categories: 技术，编程
---

* content
{:toc}
##  前言
其实这篇文章的内容很简单，说白了就是设置一个计划任务，当触发到设定的条件后就运行。

下面的演示是 Win10 系统下 Python3，需要 Python 环境，因为代码就是 Python 的。
##  开始
找到**计划任务**，然后打开

<img data-src="https://img.lbjheiheihei.xyz/FrNnAOqh1JgXfgW7JdqbP3WrRhVt" class="lazyload"  alt="计划任务" title="计划任务">

右键**任务计划程序（本地）**，然后选择**创建基本任务**

<img data-src="https://img.lbjheiheihei.xyz/FjwgVNHJ3JlJGZdvBzgCTlceolfi" class="lazyload"  alt="创建基本任务" title="创建基本任务">

名称和描述写自己能记住的，然后选择下一步
<img data-src="https://img.lbjheiheihei.xyz/Fu6ZiWkKF6pybQK92O4qKqYT8zyY" class="lazyload"  alt="名称和描述" title="名称和描述">

触发器看个人情况，下面的演示触发器是一次的
<img data-src="https://img.lbjheiheihei.xyz/FmWlDHTdG5gjmooIdtQ9ssrkVsAj" class="lazyload"  alt="触发器" title="触发器">

设置好时间就选择下一步
<img data-src="https://img.lbjheiheihei.xyz/Fv2WMIqx8P8Uwu6ttFgsRmJi34x6" class="lazyload"  alt="设置好时间" title="设置好时间">

操作这里也就只有启动程序了
<img data-src="https://img.lbjheiheihei.xyz/FhF7Ozx_c64EcY1G-NqXnuljk6Cq" class="lazyload"  alt="启动程序" title="启动程序">

按照下图的格式来填写就好，也可以选择 pythonw.exe ，区别在于没有 python.exe 这个黑窗口。个人是喜欢加上的 python.exe ，而不是 pythonw.exe 。

因为 pythonw.exe 弹出的窗口可能会被遮挡住，python.exe 的则不会在弹出时就被遮挡住。
<img data-src="https://img.lbjheiheihei.xyz/FiJxUBDNM5qt1CUA9J5uj-hCbA05" class="lazyload"  alt="python.exe" title="python.exe">

接着会看到一个完整的展示，点击完成就好
<img data-src="https://img.lbjheiheihei.xyz/FsOTxTwsgiWwz-dLejidHpJbBlqg" class="lazyload"  alt="完成" title="完成">
到了设置好的时间就会运行代码。

<img data-src="https://img.lbjheiheihei.xyz/FnWXoXWNiLwlxid16CUDhsJ_JJtH" class="lazyload"  alt="到点运行" title="到点运行">

##  补充
如果需要修改，需要点击任务计划程序库，然后找到你设置好的任务，双击，然后就可以修改了
<img data-src="https://img.lbjheiheihei.xyz/FvpXUHKODCh9TA9t1jLbJqZuHU55" class="lazyload"  alt="修改任务计划" title="修改任务计划">

需要注意一下条件那里，默认好像是勾选只有在计算机使用交流电源才启动此任务，说白了就是接上了电源才能启动任务，不接电源就不启动。取消勾选，什么时候都能运行。
<img data-src="https://img.lbjheiheihei.xyz/FoI7fX4SY82hfv05Dzek9zvaoIvj" class="lazyload"  alt="勾选" title="勾选">

##  相关说明

演示的代码[这篇文章](https://weijunzii.github.io/2018/07/21/Use-Python-Draw-a-Heart.html)里面有