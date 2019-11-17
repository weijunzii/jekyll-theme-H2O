---
layout: post
title: '爬取朋友圈的内容'
subtitle: '简单实现'
date: 2019-11-17
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 前言
爬取朋友圈的办法还是有很多的，今天我来介绍一下我最近发现的一个办法。

需要的是一台安卓手机，一台 Windows 电脑（ios + Mac 也可以）。

AirtestIDE 是网易出的跨平台的 UI 自动化编辑器，可以用来做自动化测试和爬虫。

这里用来爬取朋友圈的信息，下面把 AirtestIDE 简称为 IDE。

官网链接：[http://airtest.netease.com](http://airtest.netease.com)
官方文档：[http://airtest.netease.com/docs/cn](http://airtest.netease.com/docs/cn)

##  1 前置准备
下载回来解压之后，找到 AirtestIDE.exe 双击打开，想注册登录可以注册登录，不想的话就 Skip 跳过。
![Skip](http://img.lbjheiheihei.xyz/FthHTysrDR5Lf9YPEm7QsHU8IBjU)

进来之后是这样的，
![界面](http://img.lbjheiheihei.xyz/FoOZTa3-TkxXsYhlVp5a1mThjJET)

左上角的文件里面可以新建脚本，一般用户创建个 Airtest 的就行，能力高的纯 Python 也没毛病。
![新建脚本](http://img.lbjheiheihei.xyz/Fh5sjBccDpfZdNafzEBsFeEdXY6y)

IDE 会自动创建好脚本
![创建好的脚本](http://img.lbjheiheihei.xyz/FnssyfYrjT_sS7pXLNJIQ6bL8p-o)

确保安卓手机已经打开开发者模式，且允许 USB 调试，而且已经用 USB 连接上电脑。

界面右上角的设备窗里面找到 移动设备连接，点击刷新 ADB ，设备出来之后点击 connect 进行连接。

![连接手机](http://img.lbjheiheihei.xyz/FtVePZtD2vfgCE06Y6AeUGvG_-iL)

如果能在 AirtestIDE 里面实时看到你的安卓手机，那就是可以了。

如果出现问题，请一步一步排查，看一下是不是少操作了一步，也可以看官方文档。

[http://airtest.netease.com/docs/cn/2_device_connection/1_android_phone_connection.html](http://airtest.netease.com/docs/cn/2_device_connection/1_android_phone_connection.html)
到这里，已经是连接上手机了，可以进行下一步了。

## 2 代码准备
找到 Poco 辅助窗，然后点击一下 Stop ，在下列框中选择 Android。
![Poco 辅助窗选择](http://img.lbjheiheihei.xyz/FuQoJLpd9oV_P7GVffQ1iYt_oQax)

接着在脚本里面有一个提示，点击 Yes 就行
![确认](http://img.lbjheiheihei.xyz/FkKifWKLy9U9HIwz_mZMVZadEZbA)
IDE 会自动导入需要的东西。

然后在 UI 渲染树 那里能看到手机当前页面的 UI 树。
![UI 渲染树](http://img.lbjheiheihei.xyz/FmAKkf-9PQe8Y9Rq_eBRKqTzuI4-)

**不同版本的微信可能会有所不同**，我使用的微信版本是 7.0.7。这里主要讲的是思路，代码是辅助。

前面 IDE 自动生成的代码就略过,只讲一下需要写的代码。

```Python
start_app('com.tencent.mm')  # 启动微信

poco(text="发现").click()  # 点击发现

# poco("com.tencent.mm:id/bu").offspring("com.tencent.mm:id/bv").child("android.widget.LinearLayout").child("android.widget.RelativeLayout")[2].offspring("com.tencent.mm:id/djv").click()
poco(text="朋友圈").click()  # 点击朋友圈
```

首先是启动微信，这里非常简单 start_app('com.tencent.mm') 就可以了，com.tencent.mm 是微信的包名，如果换一个应用就需要换包名。

poco(text="发现").click() 是找到 text 属性为 发现 的 UI，然后点击它，.click()就是点击，朋友圈那个同理。
![发现](http://img.lbjheiheihei.xyz/FvFuvxcQbEhKRudwWjZLVVxMyhGo)

我注释掉了一句代码，那句也是点击 发现 的，但是比较长，所以注释掉，然后使用短的那一句代码。

这里必须说一下这行代码是怎么出来的。

在 Poco 辅助窗那点击下图中圈中的那个图标，Poco Inspector，然后到手机界面中移动到想要点击的那个 UI ，然后 UI 树会自动展开。

去 UI 树那双击想要点击的 UI ，代码会自动添加，然后加上 .click()
![UI 树](http://img.lbjheiheihei.xyz/FpmWeUUXvauyiLFiIIGmXmvu7mC6)

我知道文字表述得不够清晰，所以有动图。
![动图](http://img.lbjheiheihei.xyz/FkiUAL9ai1KNV4IR863aj5Y_D-Ao)

当然，可以选择录制脚本
![录制脚本](http://img.lbjheiheihei.xyz/FpSA-GxnD5xPnimY4Pcy5vIo5LGF)

点击这个之后，去手机页面进行点击，IDE 会自动把语句生成。

![录制脚本自动生成语句](http://img.lbjheiheihei.xyz/FnBL9xmdhVgmOjmn3wG9iJsI6Lrf)

所以目前是已经打开微信，点击了发现，进入了朋友圈。

```Python
while True:
    result_obj = poco("com.tencent.mm:id/f3l")
    for result in result_obj:
        try:
            name = result.offspring("com.tencent.mm:id/bag").get_text()
            context =  result.offspring("com.tencent.mm:id/f3p").get_text()
            print(name,context)
            print()
        except:
            pass
    
    dev = device()  # 获取当前手机设备
    dev.minitouch.swipe_along([[817, 2170],[506, 32]])
    sleep(2.5)  # 暂停 2.5 秒
```

看下图就可以知道，一条朋友圈就是在一个 name 为 com.tencent.mm:id/f3l 的FrameLayout 里面的。

![一条朋友圈](http://img.lbjheiheihei.xyz/FpKOf4S453ZoWi5_xro_Ihrqqzz0)
poco("com.tencent.mm:id/f3l") 就是获取界面上能看到的朋友圈。

result_obj = poco("com.tencent.mm:id/f3l") 是把界面上能看到的朋友圈全部获取然后赋值到 result_obj ，待会对 result_obj 进行 for 循环，遍历出需要的内容来。


由下图可以看出，com.tencent.mm:id/bag 是 昵称/备注， com.tencent.mm:id/f3p 是文字内容。

name = result.offspring("com.tencent.mm:id/bag").get_text() 的意思就是把某一条朋友圈的昵称提取出来，赋值给 name，context 同理。
![内容](http://img.lbjheiheihei.xyz/Ft6wIkdKL9gc4DdPKZjy3O34k-iO)

因为很有可能会出现问题，所以我 try except 了一下。

dev = device() 是获取当前手机设备，因为遍历完了当前的这些就需要上滑加载更多。

dev.minitouch.swipe_along([[817, 2170],[506, 32]]) 就是上滑。[817, 2170] 和 [506, 32] 就是坐标，dev.minitouch.swipe_along([A,B])的意思就是从 A 坐标 滑动到 B 坐标。

左上角的选项那里有个设置，设置里面有个实时坐标显示，勾选了之后，鼠标移动到手机界面就能看到实时坐标。

相对坐标也可以使用勾选，按道理应该在适配上更好一点。
![实时坐标显示](http://img.lbjheiheihei.xyz/FmDabPTO-OVE4Ap8QKZGq10-9uMT)

效果就是这样
![实时坐标显示效果](http://img.lbjheiheihei.xyz/Fi8kfmp3S7lsgU79KZaWtOZD0Ml2)

把这些代码放在 while True: 里面，这样就能一直运行下去了。

## 3 完整代码
下面这个的代码只是使用 IDE 进行输出，不需要使用 Python 环境；
```Python
# -*- encoding=utf8 -*-
__author__ = "ASUS"

from airtest.core.api import *
from poco.drivers.android.uiautomation import AndroidUiautomationPoco
poco = AndroidUiautomationPoco(use_airtest_input=True, screenshot_each_action=False)

start_app('com.tencent.mm')  # 启动微信
sleep(6.6)
poco(text="发现").click()  # 点击发现
poco(text="朋友圈").click()  # 点击朋友圈

while True:
    result_obj = poco("com.tencent.mm:id/f3l")
    for result in result_obj:
        try:
            name = result.offspring("com.tencent.mm:id/bag").get_text()
            context =  result.offspring("com.tencent.mm:id/f3p").get_text()
            print(name,context)
            print()
        except:
            pass
    
    dev = device()  # 获取当前手机设备
    dev.minitouch.swipe_along([[817, 2170],[506, 32]])  # 向上滑动
    sleep(2.5)  # 暂停 2.5 秒
```
如果是要保存的话，那就得需要使用 Python 了。保存到 csv 文件的 python 代码就在下面。

建议是使用 IDE 来创建，这样会自动填写连接手机的代码。

"Android://127.0.0.1:5037/d918c48a" 这里 d918c48a 就是下图显示的这个，不同手机是不一样的。（如果知道 adb 的话，直接 cmd 里面 adb devices 查看）

![设备](http://img.lbjheiheihei.xyz/Fg4U_xmybM6S1OJNsiYR098rTWX2)
```Python
# -*- encoding=utf8 -*-
__author__ = "ASUS"
import csv
from airtest.core.api import *
from airtest.cli.parser import cli_setup
from poco.drivers.android.uiautomation import AndroidUiautomationPoco

poco = AndroidUiautomationPoco(use_airtest_input=True, screenshot_each_action=False)

if not cli_setup():
    auto_setup(__file__, logdir=True, devices=[
        "Android://127.0.0.1:5037/d918c48a",
    ])

# generate html report
# from airtest.report.report import simple_report
# simple_report(__file__, logpath=True)# script content

start_app('com.tencent.mm')  # 启动微信
sleep(6.6)
poco(text="发现").click()  # 点击发现
poco(text="朋友圈").click()  # 点击进入朋友圈

with open('pyq.csv', "w", newline="", encoding="utf-8-sig") as f:
    csv_write = csv.writer(f)
    csv_head = ["昵称", "文本内容"]
    csv_write.writerow(csv_head)

while True:
    result_obj = poco("com.tencent.mm:id/f3l")
    out = open("pyq.csv", "a+", newline="", encoding="utf-8-sig")
    csv_writer = csv.writer(out, dialect="excel")

    for result in result_obj:
        try:
            name = result.offspring("com.tencent.mm:id/bag").get_text()
            context = result.offspring("com.tencent.mm:id/f3p").get_text()
            print(name, context)
            row = [name, context]
            csv_writer.writerow(row)
            print()
        except:
            pass

    out.close()
    dev = device()  # 获取当前手机设备
    dev.minitouch.swipe_along([[817, 2170], [506, 32]])  # 向上滑动
    sleep(2.5)
```

## 4 相关说明
AirtestIDE 是可以只运行部分代码的
![只运行选中代码](http://img.lbjheiheihei.xyz/Fhs99SUTSCju7kxroUkJe6MfM2Ou)

稍微做一下修改的话，那么就不是爬取整个朋友圈了，而是可以单独爬取一个人的朋友圈。

这样爬取下来的只是昵称 + 文字，如果想爬取更多，可以试试 hook 或者 mitmproxy 抓包，如果有更好的方式，欢迎大佬留言![img](https://res.wx.qq.com/mpres/htmledition/images/icon/common/emotion_panel/emoji_wx/2_12.png)