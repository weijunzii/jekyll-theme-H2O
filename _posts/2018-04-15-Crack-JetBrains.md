---
layout: post
title: '破解 Pycharm 专业版'
subtitle: '最好还是不要这样'
date: 2018-04-15
author: 伪君子
categories: 技术
cover: ''
tags: 破解

---

* content
{:toc}


#  0  前言

***

Pycharm 社区版没有专业版的部分功能，有人喜欢使用教育部，有人不喜欢[教育版](http://mp.weixin.qq.com/s/VLA6_dnnyOzJUuXKgf_Umg)，那就破解专业版吧。

说是破解 Pycharm ，其实是 JetBrains 系列的都能破解 ，只是我这里只说 Pycharm 的破解而已，有空的话，可以去试试破解 JetBrains 系列软件。

如果是学生，可以去**[申请学生授权](https://sales.jetbrains.com/hc/zh-cn/articles/207154369-%E5%AD%A6%E7%94%9F%E6%8E%88%E6%9D%83%E7%94%B3%E8%AF%B7%E6%96%B9%E5%BC%8F)**, 不用这么麻烦；如果可以，请支持正版。

#   1  下载

***



首先你得下载了专业版的 [Pycharm](http://mp.weixin.qq.com/s/ygVuD0UOFGxtwWfbQHXDAg)，至于 [Python](http://mp.weixin.qq.com/s/cubyNsqX4Hg1Zo7CChY8Aw)，我想不用多说了。

好了，现在该有的东西都有了，安装都安装完了，那就开始破解。



#   2  破解

***



这里简单介绍两种方法

##  2.1 注册码激活

[http://idea.lanyus.com](http://idea.lanyus.com) 打开这个网站,点击获取注册码就好.

这里省略内容,因为我也没试过这个.

![999556.gif](https://upload-images.jianshu.io/upload_images/2989110-8bf551264c365e87.gif?imageMogr2/auto-orient/strip)

##  2.2  使用破解补丁激活

我们先进入 Pycharm 的目录下，找到 *bin* 文件夹，打开这个文件夹。

例如我这里的路径是：  D:\Program Files\JetBrains\PyCharm 2018.1\bin（不难找，一般是安装的盘不一样）

然后去 [http://idea.lanyus.com](http://idea.lanyus.com/) 那下载破解补丁,

![image.png](https://upload-images.jianshu.io/upload_images/2989110-7a2267ef4c8f969e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

把下载来的补丁放再这个目录下

> D:\Program Files\JetBrains\PyCharm 2018.1\bin



![poji](https://upload-images.jianshu.io/upload_images/2989110-73bc93c05efab8cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后找到 pycharm.exe.vmoptions 和 pycharm64.exe.vmoptions 这两个文件，以文本格式打开 ( 记事本、EditPlus 都行)

![image.png](https://upload-images.jianshu.io/upload_images/2989110-3212239ce4af20b2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后添加一行内容，格式是

>-javaagent:文件目录\补丁名

就如

> -javaagent:D:\Program Files\JetBrains\PyCharm 2018.1\bin\JetbrainsCrack-2.7-release-str.jar

![image.png](https://upload-images.jianshu.io/upload_images/2989110-4541257ad0377698.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

两个文件都要添加这一行内容.

然后保存，打开 Pycharm，选择使用激活码激活。

![image.png](https://upload-images.jianshu.io/upload_images/2989110-5a27fe91d62039ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输入如下激活码

>```
>ThisCrackLicenseId-{
>"licenseId":"ThisCrackLicenseId",
>"licenseeName":"Boss",
>"assigneeName":"",
>"assigneeEmail":"6666666@163.com",
>"licenseRestriction":"For Rover12421 Crack, Only Test! Please support genuine!!!",
>"checkConcurrentUse":false,
>"products":[
>{"code":"II","paidUpTo":"2099-12-31"},
>{"code":"DM","paidUpTo":"2099-12-31"},
>{"code":"AC","paidUpTo":"2099-12-31"},
>{"code":"RS0","paidUpTo":"2099-12-31"},
>{"code":"WS","paidUpTo":"2099-12-31"},
>{"code":"DPN","paidUpTo":"2099-12-31"},
>{"code":"RC","paidUpTo":"2099-12-31"},
>{"code":"PS","paidUpTo":"2099-12-31"},
>{"code":"DC","paidUpTo":"2099-12-31"},
>{"code":"RM","paidUpTo":"2099-12-31"},
>{"code":"CL","paidUpTo":"2099-12-31"},
>{"code":"PC","paidUpTo":"2099-12-31"}
>],
>"hash":"2911276/0",
>"gracePeriodDays":7,
>"autoProlongated":false}
>```

点击 OK 就激活成功了.

![image.png](https://upload-images.jianshu.io/upload_images/2989110-ca91a31da029f5fe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



如果想再次确认一下激活成功了,进入 Pycharm 的菜单栏,选择 Help,再选择 About 查看许可信息

![poji](https://upload-images.jianshu.io/upload_images/2989110-03144c33b0a13886.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



##  2.3  修改试用时间

安装前将系统时间需要改为一个比较远的时间，如2050年，修改后安装IntelliJ IDEA，安装后选择试用，全部步骤完毕并关闭IntelliJ IDEA后，将系统时间修改回来。

这个方法我没试过,能不能成功就看缘分了.

#   3  相关链接

***

感谢  [http://idea.lanyus.com](http://idea.lanyus.com/)  的破解补丁

感谢 [http://idea.lanyus.com/help/help.html](http://idea.lanyus.com/help/help.html) 的说明