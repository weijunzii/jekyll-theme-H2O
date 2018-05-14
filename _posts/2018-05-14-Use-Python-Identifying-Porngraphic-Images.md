---
layout: post
title: '用 Python 鉴别色色的图片'
subtitle: '玄学鉴黄了解一下~'
date: 2018-05-14
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程 有趣的 python

---

* content
{:toc}
#  0  前言

***

实话实说啊，这个标题起得就有点标题党，识别是识别，准确率就有点玄学了。

#  1  环境说明

***

Win10 系统下 Python3，编译器是 Pycharm，需要安装 nonude 这个库。

Pycharm 安装第三方库的方法。
![](http://upload-images.jianshu.io/upload_images/2989110-3b802df41aeff65b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/2989110-08e77e3f15cadde7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  2  代码

***

### 2.1 识别少量图片
先导入 nonude 这个库（我也很奇怪为什么 import 的是 nude）
```
import nude
```
再写出代码
```
print(nude.is_nude("godfather.jpg"))
print(nude.is_nude("leisheng.jpg"))
print(nude.is_nude("qiaoba.png"))
```
代码运行的结果居然是 False、True、True
让我们来看一下图片。

![godfather.jpg](https://upload-images.jianshu.io/upload_images/2989110-114fb6fdc10a260e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![lei.jpg](https://upload-images.jianshu.io/upload_images/2989110-d622cf31f7967a16.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![qiaoba.png](https://upload-images.jianshu.io/upload_images/2989110-f4197fb0f3f271c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


对了，我这里是直接把图片放在了项目的路径里的
![](https://upload-images.jianshu.io/upload_images/2989110-6929dfd175d7b049.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果不喜欢这样，可以换一个写法
```
import nude
print(nude.is_nude("E:/Images/OOXX/00mitai.jpg"))
print(nude.is_nude("E:\Images\OOXX/00zkted.jpg"))
print(nude.is_nude("E:/Images\OOXX/011idk8.jpg"))
```
代码运行的结果是 False、True、False

![00mitai.jpg](https://upload-images.jianshu.io/upload_images/2989110-f3d0e5e77006a8e4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![00zkted.jpg](https://upload-images.jianshu.io/upload_images/2989110-0ecf05a7767beeac.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![011idk8.jpg](https://upload-images.jianshu.io/upload_images/2989110-21c9e92130da2635.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

说一下，路径里面的斜杠 / 可以是反斜杠 \，如果后面有数字的话，请使用斜杠 /，不要用反斜杠 \。

### 2.2 识别文件夹中的图片
先导入要用的库
```
import glob
import itertools
from nude import Nude
```
这里用 glob 返回匹配指定模式的文件名
```
images_format = ['jpg', 'png', 'gif']  # 图片格式
images_jpg = glob.glob("E:/Images/OOXX/*.jpg")  # 返回匹配指定模式的文件名
images_png = glob.glob("E:/Images/OOXX/*.png")
images_gif = glob.glob("E:/Images/OOXX/*.gif")
```
itertools.chain 把迭代对象串联起来，形成一个更大的迭代器，说白了就是把 images_jpg、images_png、images_gif 弄在一起，变成了images_list。

然后进行循环，在 images_list 里面一个一个对图片进行识别。
```
images_list = itertools.chain(images_jpg, images_png, images_gif)

for i in images_list:
    print(i)  # 输出照片的路径
    n = Nude(i)  # 对图片进行识别
    n.parse()
    print(n.result)  # 输出结果
    print(n.message)  # 输出判断信息
    print(n.inspect())  # 输出更加详细的判断信息
```
运行结果如下图

![TeamViewer_2018-05-14_19-45-57.png](https://upload-images.jianshu.io/upload_images/2989110-60098e91275689c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们来看一下下图片，准确率嘛，有点玄学。

![图片还可以吧](https://upload-images.jianshu.io/upload_images/2989110-dbfe84f07acdc926.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





#  3  说明

***

识别是不是色色的图片的有依据的，根据给出的信息来看，是皮肤暴露的百分比来判断的，暴露的比例大于 15% 就判断为色色的图片。这里只是很粗浅的说明，还有一些我没有看懂。

nonude 的 GitHub 链接：[https://github.com/gearsystems/nonude/](https://github.com/gearsystems/nonude)

nonude 的最近一次更新是两年前了，感觉有点可惜，希望作者能继续维护。