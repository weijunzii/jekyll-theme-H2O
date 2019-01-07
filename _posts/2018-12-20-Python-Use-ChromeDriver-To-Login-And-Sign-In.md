---
layout: post
title: 'Python 用  ChromeDriver 实现登录和签到'
subtitle: '不只是登录，还可以签到~'
date: 2018-12-20
author: 伪君子
categories:
cover: ''
tags: 有趣的 Python

---

* content
{:toc}
# 0 前言
上个星期天，老师给我一堆账号，让我测试一下他们有没有去修改密码，我随手测试了几个之后发现有 500+ 个账户，想都没想就着手写代码了。

是用 Python 实现的，再加上一个 ChromeDriver 。不过这个代码不能公布出来，不然我就要喝茶了。

好在之前写过类似的代码，能把以前写过的代码拿出来做例子，还行，又不是不能用。
# 1 下载
Win10 系统下 Python3，编译器是 Pycharm 。需要安装 selenium ，安装失败的话可以看[这篇文章](https://weijunzii.github.io/2018/05/27/Install-Scrapy-In-Window.html)，里面有相关的教程。


>[https://sites.google.com/a/chromium.org/chromedriver/downloads](https://sites.google.com/a/chromium.org/chromedriver/downloads)

进入之后看一下谷歌浏览器的版本和 ChromeDriver 所支持的版本，如果是合适的，那就直接下载最新的 ChromeDriver。
![](https://upload-images.jianshu.io/upload_images/2989110-c44071315d3a0ed1.png)
如果想下载别的版本的 ChromeDriver，直接修改 path= 后面的数字就好。
![](https://upload-images.jianshu.io/upload_images/2989110-c42fb68c7ce6321d.png)
下载完成后解压，可以把解压后的文件放在别的地方，我是放在了谷歌浏览器的目录下，因为这样相对来说比较好找。
![](https://upload-images.jianshu.io/upload_images/2989110-d408065790950ab9.png)


别的浏览器也有对应的 Driver，可以自行前去下载。

>[https://selenium-python.readthedocs.io/installation.html](https://selenium-python.readthedocs.io/installation.html)

![](https://upload-images.jianshu.io/upload_images/2989110-465f493f9faf8c92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2 使用
先导入 webdriver 和 time，time 是用来防止操作过快的。
```Python
import time
from selenium import webdriver
```
对 webdriver 进行设置,我习惯了用隐身模式打开；driver_path 是 chromedriver.exe 的路径，
```Python
options = webdriver.ChromeOptions()
options.add_argument("--incognito")  # 隐身模式打开
driver_path = "C:\Program Files (x86)\Google\Chrome\Application\chromedriver.exe"  # chromedriver.exe 的路径
browser = webdriver.Chrome(executable_path=driver_path, options=options)
```
这里我用的是 css_selector，因为相对来说比较简单。

get() 方法是打开链接; send_keys() 方法是把内容填写上去；click() 方法是模拟点击。

time.sleep(3) 是推迟 3 秒再去执行，也就是暂停 3 秒。

```Python
browser.get("https://kejibear.xyz/auth/login")  # 网址
browser.find_element_by_css_selector(".card-inner input[name='Email']").send_keys("@qq.com")  # 账号
browser.find_element_by_css_selector(".card-inner input[name='Password']").send_keys("1")  # 密码
browser.find_element_by_css_selector(".row .col-md-10.col-md-push-1 button.waves-effect").click()
print("登录成功~")
time.sleep(3)
```
这里和上面是一样的，不过是已经登录进去之后再执行。close()方法是关闭浏览器。
```Python
browser.find_element_by_css_selector(".card-action-btn #checkin-btn button.waves-effect").click()
print("签到成功~")
time.sleep(5)
browser.close()
```

把上面的代码依次复制到运行环境中，然后修改网址，修改账户和密码就能实现自动登录和签到了。

这个代码适用于大部分的酸酸乳网站，只要是那一套模板改出来的都适用。

#  3 说明
可以使用PhantomJS(无头浏览器)，来达到目的，不过我懒得写了。
>[http://phantomjs.org/](http://phantomjs.org/)

在使用中可能会遇到要判断是否登录进去的情况，有一个思路是判断有没有登录成功后特有的元素，如果有则执行代码；如果没有，则执行别的代码。

例如：
```Python

try:  
    browser.find_element_by_css_selector(".confirm-content input[type='submit']")
    #  遇到异常则执行 except: 的代码，如果没有，正常执行。
    print(uid)
    browser.close()
except:
    browser.close()

```

当我写完这篇文字之后我发现原来我之前写过[类似的文章](https://weijunzii.github.io/2018/07/27/Simulate-Login-Zhihu.html),这个就有点尴尬了。