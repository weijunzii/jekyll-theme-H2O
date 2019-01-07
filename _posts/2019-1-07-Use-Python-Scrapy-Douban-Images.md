---
layout: post
title: '用 Python 爬取豆瓣上的图片'
subtitle: '爬一下豆瓣还挺好'
date: 2019-1-07
author: 伪君子
categories:
cover: ''
tags: Python 豆瓣 爬虫

---

* content
{:toc}
#  0 前言
最近在极客时间上学习数据分析的内容，刚好老师在课程上讲了爬虫的内容，而且是爬取豆瓣上的图片，把老师给的代码稍微修改了一下，再加上了我的理解和说明。

#  1 环境说明
Win10 系统下 Python3，编译器是 PyCharm 。json、re 和 os 是不用辛苦安装；requests 可以直接用 pip install requests  安装。要是不知道该怎么安装，那还是用 Pycharm 安装吧。
![](http://upload-images.jianshu.io/upload_images/2989110-3b802df41aeff65b.png)

![](http://upload-images.jianshu.io/upload_images/2989110-08e77e3f15cadde7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2 实现
代码不算多，为了能解释清楚，所以是按顺序分开来，用的时候按顺序复制就好。

先导入要用的库

```Python
import json
import re
import os
import requests 
```
query 是查询，在代码里的意思是想要爬取的人的名字，随意修改。

path 这个是可以随意修改的，可以把 ```path = os.getcwd()``` 这一句取消注释，然后注释掉下面那一句。```path = os.getcwd()``` 的作用是获得当前文件的路径，然后把这个 .py 文件的路径赋值给 path。

```path = 'C:/Users/ASUS/Desktop/测试'``` 的意思是一样的，把后面这个路径赋给 path，如果用这个的话，记得修改成自己想要的路径。两个语句只能选择一个，另一个需要注释掉。

picpath 就是图片所在的目录，接下来就是要判断一下这个目录是否创建了，如果没有创建，那就创建。
```Python
query = '王祖贤'
path = os.getcwd()  # 当前路径，可以替换成别的路径
# path = 'C:/Users/ASUS/Desktop/测试'
picpath = path + '/' + query  # 设置的图片目录
print(picpath)  # 输出设置的图片目录
if not os.path.isdir(picpath):  # 如果图片目录未创建则创建一个
    os.mkdir(picpath)
```
这里是下载图片的 download 函数，传入的 src 是图片的链接，传入的 id 是图片的名称，图片的完整名就是图片对应的 id 再加上 .jpg。

dir 就是图片的路径，先是请求图片，如果遇到网络问题导致请求不到，那么就捕获 requests 的  ConnectionError  异常。如果能够请求到，那就打开以 wb 也就是二进制写模式打开图片，图片的路径就是上面说到的dir 。打开之后就把请求到的图片的内容写入，然后关闭。
```Python
def download(src, id):
    dir = picpath + '/' + str(id) + '.jpg'
    try:
        pic = requests.get(src, timeout=10)
    except requests.exceptions.ConnectionError:
        print(id + ' 图片无法下载')
    fp = open(dir, 'wb')
    fp.write(pic.content)
    fp.close()
```
下面这里就是进入循环，请求 url，找到这个 url 还是挺简单的。先进入下面给出的链接，然后  F12 打开开发者工具，点击 Newwork，然后再点击 XHR（XMLHttpRequest），接着 F5 刷新一下页面就能看到 search_photo?q= 那一串东西，点击它，接着去点击一下 Headers，最后就能看到 Request URL。

>[https://www.douban.com/search?cat=1025&q=王祖贤](https://www.douban.com/search?cat=1025&q=%E7%8E%8B%E7%A5%96%E8%B4%A4)

![](https://upload-images.jianshu.io/upload_images/2989110-7a145f7b14751460.png)

把 Request URL 的链接打开，就能看见 JSON 格式的数据了。当然，不出意外的话，你看到的是下图这种看得令人难受的样子。
![](https://upload-images.jianshu.io/upload_images/2989110-281e4d030a3d6f8a.png)
如果用谷歌浏览器的扩展程序 JSONView 的话，你看到的是下图这种清爽的样子，清晰明了又好看。
![](https://upload-images.jianshu.io/upload_images/2989110-6dd385291cd7223e.png)
多试几次就能发现 Request URL 的规律了，start=0，start=20，start=40.

拉到最底下你就能看到 total: 22598,limit: 20,more: true 这样的数据，意思是一共有 22598 张图片，一次只能请求 20，more 表示后面的还能请求。不过实际测试中我发现 start=2001 就显示 total: -1,limit: 20,more: false。

for i in range(0, 22471, 20) 的意思是从 0 开始循环到 22471，步长或者说间隔是 20，意思是 i 的值的变换规律是 0，20，40 ，60。

url 就是每一次请求的链接，得到的结果赋值给 html，接着把  JSON 对象的 html 转换成 Python 对象，接着是用一个 for 循环把每一个图片对应的链接和 id 拿到，然后交给前面说到的下载函数进行下载。

有一点需要注意，我把图片链接中的 thumb 全部替换成了 l，因为测试的时候发现替换之后的图片是大图，试试下面这个链接就知道了。

>[https://img3.doubanio.com/view/photo/thumb/public/p611792033.jpg](https://img3.doubanio.com/view/photo/thumb/public/p611792033.jpg)

这里实现替换可以用两种方法，一种是直接 replace，一种是用 re 模块的 sub 方法
```Python
''' for 循环 请求全部的 url '''
for i in range(0, 22471, 20):  #
    url = 'https://www.douban.com/j/search_photo?q=' + query + '&limit=20&start=' + str(i)
    html = requests.get(url).text  # 得到返回结果
    response = json.loads(html, encoding='utf-8')  # 将 JSON 格式转换成 Python 对象
    print('已下载 ' + str(i) + ' 张图片')
    for image in response['images']:
        image['src'] = image['src'].replace('thumb', 'l')
        # image['src'] = re.sub(r'thumb', r'l', image['src'])
        print(image['src'])  # 查看当前下载的图片网址
        download(image['src'], image['id'])  # 下载一张图片
```

# 3 运行结果和说明
在写好的路径下出现一个王祖贤的文件夹，文件夹里面有一堆图片。我这里的路径是 C:/Users/ASUS/Desktop/测试/王祖贤 ，搞定收工。
![](https://upload-images.jianshu.io/upload_images/2989110-f9d647f88d1bc9bc.png)