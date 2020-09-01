---
permalink: /2018/07/21/Use-Python-Draw-a-Heart.html
title: 用 Python 给你比个心
subtitle: 还有音乐
cover: ""
author: 君子
tags: 编程 Python
date: 2018-07-21
layout: post
categories: 技术，编程
---

* content
{:toc}
#  0 前言
之前写了一篇[用 Python 画一个小猪佩奇和哆啦 A 梦](https://weijunzii.github.io/2018/05/08/Use-Python-write-PeppaPig-And-Doraemon.html)，然后最近看到有人用 turtle 画了一个心，觉得挺有意思的，于是把代码复制到本地，再加了个播放音乐。
#  1 环境说明
Win10 系统下 Python3，编译器是 Pycharm 。turtle 和 time 是，不用辛苦安装；pygame 可以直接用 `pip install  pygame` 安装，要是不知道该怎么安装，那还是用  Pycharm 安装吧。

<img data-src="https://img.lbjheiheihei.xyz/FiWX1br6ELwKwLQIfQfmFO5je-oT" class="lazyload"  alt="Pycharm 安装第三方包" title="Pycharm 安装第三方包">
<img data-src="https://img.lbjheiheihei.xyz/FqXVEBEtAStmMAD29k5x4NHvFV9M" class="lazyload"  alt="Pycharm 安装第三方包" title="Pycharm 安装第三方包">



#  2 实现
代码有点多，所以是分开来，用的时候按顺序复制就好。

先导入要用的库
```python
import pygame
import time
import turtle as t
```
然后是播放音乐的功能，这里记得要把文件的路径修改一下
```python
file = 'G:\years.mp3'  # mp3 的路径
pygame.mixer.init()  # 初始化音频
track = pygame.mixer.music.load(file)  # 载入音乐文件
pygame.mixer.music.play()  # 开始播放
```
turtle 的设置，背景色和颜色可以使用 #bf360c 或者 red 来替换颜色，具体的颜色喜欢哪个就用哪个，看着舒服和好看就行。
```python
t.title('dalao 带带我')  # 设置标题栏文字
t.hideturtle()  # 隐藏箭头
t.getscreen().bgcolor('#f0f0f0')  # 背景色
t.color('#c1e6c6', 'red')  # 设置画线颜色、填充颜色，可以直接写 green，也可以用 #c1e6c6
t.pensize(2)  # 笔的大小
t.speed(2)  # 图形绘制的速度,1~10
t.up()  # 移动，不画线
t.goto(0, -150)
```
下面这里开始画爱心
```python
t.down()  # 移动，画线
t.begin_fill()  # 开始填充
t.goto(0, -150)
t.goto(-175.12, -8.59)
t.left(140)
pos = []
for i in range(19):
    t.right(10)
    t.forward(20)
    pos.append((-t.pos()[0], t.pos()[1]))
for item in pos[::-1]:
    t.goto(item)
t.goto(175.12, -8.59)
t.goto(0, -150)
t.left(50)
t.end_fill()  # 结束填充，显示填充效果
```
这里开始写字，t.goto(0, 220) 的意思是箭头前往到这个位置，(0, 0) 是中心。

(x, y)，x 是左右，正数为右，负数为左；y 是上下，正数为上，负数为下。

字体可以修改，黑体、方正舒体、华文琥珀等等，找一个合适的就好。
```python
t.color("black")  # 设置颜色
t.up()
t.goto(0, 220)
t.write("大佬，带带我~", font=(u"方正舒体", 36, "normal"), align="center")
t.goto(200, -250)
t.write('by 伪君子', font=(u"方正舒体", 10, "bold"))
```
结束,如果下面的代码注释掉 t.done() 的话，那么结束播放音乐后就会自动退出；如果不注释的话，运行完代码会停留在画图的界面，音乐播放到结束设置好的时间就结束。

这里看你喜欢，我个人是喜欢播放到一定时间就自动退出，所以我注释掉了。
```python
time.sleep(10)  # 画完后再播放 10 秒音乐，可以修改时间
pygame.mixer.music.fadeout(100)  # 停止播放
#t.done()
```
录制了一个 gif 做示范
<img data-src="https://img.lbjheiheihei.xyz/Fvf6tJM0a24-p8DX5IgvDBFwcaPM" class="lazyload"  alt="gif" title="gif">
#  3 相关说明
源代码是在知乎专栏那看见的，这里复制下来进行了修改和添加。

链接：[https://zhuanlan.zhihu.com/p/38448462](https://zhuanlan.zhihu.com/p/38448462)（点击阅读原文）