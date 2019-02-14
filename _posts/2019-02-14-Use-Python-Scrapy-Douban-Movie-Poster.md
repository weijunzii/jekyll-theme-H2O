---
layout: post
title: '用 Python 爬取豆瓣电影海报'
subtitle: '本文的例子是下载王祖贤相关的电影海报'
date: 2019-02-14
author: 伪君子
categories:
cover: ''
tags: Python 豆瓣 爬虫
---

* content
{:toc}
#  0 前言
之前写过一篇[用 Python 爬取豆瓣上的图片](https://weijunzii.github.io/2019/01/07/Use-Python-Scrapy-Douban-Images.html)，那今天就来写一下爬取豆瓣上的电影海报，算是姐妹篇。

#  1 环境说明
Win10 系统下 Python3，编译器是 PyCharm 。requests 可以直接用 pip install requests 安装，lxml、selenium 也一样，要是不知道该怎么安装，那还是用 PyCharm 安装吧。
![PyCharm 安装第三方库](http://upload-images.jianshu.io/upload_images/2989110-3b802df41aeff65b.png)

![PyCharm 安装第三方库](http://upload-images.jianshu.io/upload_images/2989110-08e77e3f15cadde7.png)
还需要下载和配置 ChromeDriver，可以看看[这篇文章](https://weijunzii.github.io/2018/12/20/Python-Use-ChromeDriver-To-Login-And-Sign-In.html)里面的内容。

#  2 代码
代码不算多，为了能解释清楚，所以也是按顺序分开来，用的时候按顺序复制就好。

先导入要用的库

```Python
import os
import requests
from lxml import etree
from selenium import webdriver
```
query 是查询，在代码里的意思是想要爬取的人的名字，随意修改。

path 这个是可以随意修改的，可以把 path = os.getcwd() 这一句注释，然后下面那一句注释掉。path = os.getcwd() 的作用是获得当前文件的路径，然后把这个 .py 文件的路径赋值给 path。

path = 'C:/Users/ASUS/Desktop/测试' 的意思是一样的，把后面这个路径赋给 path，如果用这个的话，记得修改成自己想要的路径。两个语句只能选择一个，另一个需要注释掉，不然程序会把最后一个赋值语句的值赋给 path。

picpath 就是图片所在的目录，接下来就是要判断一下这个目录是否创建了，如果没有创建，那就创建。

```Python
query = '王祖贤'  # 名字可以随便换
path = os.getcwd()  # 当前路径，可以替换成别的路径
# path = 'C:/Users/ASUS/Desktop/测试'
picpath = path + '/' + query  # 设置的图片目录
print(picpath)  # 输出设置的图片目录
if not os.path.isdir(picpath):  # 如果图片目录未创建则创建一个
    os.mkdir(picpath)
```
这里是下载图片的 download 函数，传入的 src 是图片的链接，传入的 id 是图片的名称，图片的完整名就是图片对应的 id 再加上 .jpg。

dir 就是图片的路径，先是请求图片，如果遇到网络问题导致请求不到，那么就捕获 requests 的 ConnectionError 异常。如果能够请求到，那就打开以 wb 也就是二进制写模式打开图片，图片的路径就是上面说到的dir 。打开之后就把请求到的图片的内容写入，然后关闭。

```Python
def download(src, id):
    dir = picpath + '/' + str(id) + '.jpg'
    try:
        pic = requests.get(src, timeout=10)
    except requests.exceptions.ConnectionError:
        # print 'error, %d 当前图片无法下载', %id
        print('图片无法下载')
    fp = open(dir, 'wb')
    fp.write(pic.content)
    fp.close()
```
这里是关于 ChromeDriver 的部分，需要下载和配置 ChromeDriver，可以看看[这篇文章](https://weijunzii.github.io/2018/12/20/Python-Use-ChromeDriver-To-Login-And-Sign-In.html)里面的内容,里面有提及到。
```Python
driver_path = "C:/Program Files (x86)/Google/Chrome/Application/chromedriver.exe"  # chromedriver 的路径
browser = webdriver.Chrome(executable_path=driver_path)
```
```for i in range(0, 6*15, 15):``` ，意思是从 0 开始到 75，每一个间隔是 15，例如，0、15、30、45、60、75，这里要说明的是，90 是不算在内的。

6*15 是因为王祖贤的电影海报只有 6 页，6 可以改成 10，最多就是程序运行多一会，不会有太多的影响。

对提取出来的 src 进行替换链接，s_ratio_celebrity 和 s_ratio_poster 都是小图，替换成 l 之后就是大图。webp 替换成 jpg，方便下载之后查看图片。
```Python
for i in range(0, 10*15, 15):
    url = 'https://movie.douban.com/subject_search?search_text=' + query + '&cat=1002' + '&start=' + str(i)
    browser.get(url)  # 打开浏览器
    html = etree.HTML(browser.page_source)
    # print(browser.page_source)
    src_xpath = "//div[@class='item-root']/a[@class='cover-link']/img[@class='cover']/@src"  # 所有图片的 XPath
    title_xpath = "//div[@class='item-root']/div[@class='detail']/div[@class='title']/a[@class='title-text']"  # 所有电影名称的 XPath
    srcs = html.xpath(src_xpath)  # 获取页面中所有的 src_xpath，把值传给 srcs
    titles = html.xpath(title_xpath)  # 获取页面中所有的 title_xpath，把值传给 titles

    for src, title in zip(srcs, titles):
        src = src.replace('s_ratio_celebrity', 'l')
        src = src.replace('s_ratio_poster', 'l')
        src = src.replace('webp', 'jpg')
        title.text = title.text.replace('?', '')
        print('\t'.join([str(src), str(title.text)]))  # 把链接和标题输出，方便查看。
        download(src, title.text)  # 传到下载函数那进行下载
```
下载完成后输出一个『下载完成』，然后关闭浏览器。
```Python
print("下载完成")
browser.close()  # 下载完成后关闭浏览器
```

#  3 补充说明
## 3.1  url 为什么是这个?
```
url = 'https://movie.douban.com/subject_search?search_text=' + query + '&cat=1002' + '&start=' + str(i)
```
先去豆瓣电影那搜索一下王祖贤，把每一页的链接都看一遍。
>[https://movie.douban.com/](https://movie.douban.com/)

![](https://upload-images.jianshu.io/upload_images/2989110-a59a7cdb4a480dd9.png)
看完后应该就理解了。


## 3.2  src_xpath 、title_xpath 哪来的
首先，先下载一个谷歌浏览器扩展程序，名字叫『XPath Helper』，不会下载可以看[我之前写的教程](https://weijunzii.github.io/2018/10/07/Install-The-Chrome-Extension.html)。

安装完成后点击 XPath Helper 的图标就能显示和隐藏  XPath Helper 的界面，也可以使用快捷键  Ctrl+Shift+X 显示和隐藏  XPath Helper 的界面。
![](https://upload-images.jianshu.io/upload_images/2989110-2aec03e0987305eb.gif)

把 XPath 黏贴到 QUERY 框内就能看到这个 XPath 对应的内容。
![](https://upload-images.jianshu.io/upload_images/2989110-0ec0535bdf4df3a6.gif)

当然，也可以按住  Ctrl+Shift,然后移动鼠标来查看 XPath.

浏览器复制出来的 XPath 和 XPath Helper 找到的 XPath 是有区别的，建议是使用 XPath Helper 找到的 XPath.
![](https://upload-images.jianshu.io/upload_images/2989110-23bdac5fdaefa675.gif)
src_xpath 和 title_xpath 都是一步步试出来的。（这里是极客时间里《数据分析实战45讲》课程的作者陈旸试出来的）
```Python
src_xpath = "//div[@class='item-root']/a[@class='cover-link']/img[@class='cover']/@src"  # 所有图片的 XPath
title_xpath = "//div[@class='item-root']/div[@class='detail']/div[@class='title']/a[@class='title-text']"  # 所有电影名称的 XPath
```

##  3.3 结果

下载后去查看图片，如果看到下图中圈出来的图片，这不说明程序出问题，这只是豆瓣没有这个电影的海报。
![](https://upload-images.jianshu.io/upload_images/2989110-1c5af5e618a20cc2.png)
#  4 说明
本文和本文的姐妹篇都是根据极客时间里《数据分析实战45讲》的其中一讲的内容展开写写的，需要说明的是，通过下面这个二维码购买课程，我有 6 元返利。
![](https://upload-images.jianshu.io/upload_images/2989110-454e691819d5fe77.png)
