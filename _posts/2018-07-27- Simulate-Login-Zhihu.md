---
layout: post
title: '用 selenium 和 scrapy 模拟知乎登录'
subtitle: ''
date: 2018-07-27
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程 Python 模拟

---

* content
{:toc}
##  0 前言
这个是看一个视频学来的，视频给出的教程部分失效，因为知乎的登录页面改了。我进行一点修改就可以登录了，本文主要是记录

##  1 环境说明

Win10 系统下 Python3，编译器是 Pycharm 。需要安装 selenium 和 scrapy，安装的话可以考虑看[这篇文章](https://weijunzii.github.io/2018/05/27/Install-Scrapy-In-Window.html)，这里不赘述。

这里还需要下载一个 Drivers，比如我用的是 Chrome 浏览器就下载 chromedriver，别的浏览器下载对应的 driver 就好

链接：[http://selenium-python.readthedocs.io/installation.html](http://selenium-python.readthedocs.io/installation.html)
![](https://upload-images.jianshu.io/upload_images/2989110-465f493f9faf8c92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果你因为无法【翻越思维的墙】而下载不了chromedriver.exe，而且巧好是 Windows 的话，可以去下面这下载
>链接: https://pan.baidu.com/s/1Xz3ezvBVF4BwMYhV4pjaKg 
>密码: fpqc

下载回来后需要把路径记住，比如我就把 chromedriver.exe 放在了 C:/Program Files (x86)/Google/Chrome/Application/ 下。

##  2 实现
代码有点多，所以是分开来的，用的时候按顺序复制就好。

先导入要用的库
```
from selenium import webdriver
from scrapy.selector import Selector
```

接着就是对浏览器进行设置，chromedriver 的路径记得要修改一下
```
options = webdriver.ChromeOptions()
options.add_argument("--incognito")  # 隐身模式打开，可以注释掉
driver_path = "C:/Program Files (x86)/Google/Chrome/Application/chromedriver.exe"  # chromedriver 的路径
browser = webdriver.Chrome(executable_path=driver_path, chrome_options=options)
browser.get("https://www.zhihu.com/")  # 知乎网址
```
最后就是模拟点击和输入，记得把账号和密码修改一下
```
t_selector = Selector(text=browser.page_source)
browser.find_element_by_css_selector(".HomeSidebar-signBannerActions button.HomeSidebar-signBannerButton").click()  # 点击右侧登录
browser.find_element_by_css_selector(".SignFlow-accountInput.Input-wrapper input[name='username']").send_keys("你的账号")  # 账号
browser.find_element_by_css_selector(".SignFlowInput .Input-wrapper input[name='password']").send_keys("你的账号密码")  # 密码
browser.find_element_by_css_selector(".Login-content button.SignFlow-submitButton").click()  # 点击登录
```

实际效果可以看下面这个gif

![](https://upload-images.jianshu.io/upload_images/2989110-66edc505bf1f00a0.gif?imageMogr2/auto-orient/strip)

##  3 说明

登录完之后就可以开搞了

安装说明：http://selenium-python.readthedocs.io/installation.html

官方文档：https://seleniumhq.github.io/selenium/docs/api/py/