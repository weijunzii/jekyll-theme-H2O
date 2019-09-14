---
layout: post
title: 'Python 基础 - 0'
subtitle: '来了'
date: 2019-09-14
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 课前准备
1.[安装并配置好 python 环境](https://mp.weixin.qq.com/s/cubyNsqX4Hg1Zo7CChY8Aw)，建议是 python3 的
2.安装并配置好编译器，[PyCharm](https://mp.weixin.qq.com/s/cubyNsqX4Hg1Zo7CChY8Aw)、Anaconda、VS code 实在不行，记事本也可以。

实在安装不了 python 环境，那就只能用[在线工具](https://tool.lu/coderunner/)的顶替一下了。

## 1 python 基础

先说一下赋值, ```i = 0```,这个的意思不是说【i 等于 0】，而是说把 【0 这个值赋给了 i】
```Python
i = 0
print(i)
```
上面的代码，输出的是 0，print(i) 的意思就是把 i 输出。

猜一下下面这个的代码输出的是什么

```Python
i = a = s = d = f = 0
print(i, a, s, d, f)
```
接下来讲一下数据类型，看下面的代码。
```Python
i = 0
print(i)
print(type(i))

i = 0.0
print(i)
print(type(i))

i = '000000'
print(i)
print(type(i))

i = True
print(i)
print(type(i))

```
上面的代码运行的结果是
```Python
0
<class 'int'>
0.0
<class 'float'>
000000
<class 'str'>
True
<class 'bool'>
```
也就是说 i 的类型从整型(int)变成了浮点型(float),再变成字符串(str),最后变成了布尔型(bool)。

这就是 Python 的特点，换成 C 语言，C++，Java 那些，只要敢写成这样，被人笑死都是有可能的。

Python还不止有这些数据类型，List（列表）、Tuple（元组）、Set（集合）、Dictionary（字典）这些都有的。


## 2 类和函数
下面的代码就包含了类和函数，class 的意思就是类，class people的意思就是有一个类，名字叫 people。

run（）是一个函数，fly（）也是一个函数，函数的作用就是实现一些东西。
```Python
class people:
    age = 0

    def run(self):
        return 'run run run'

    def fly(self):
        return '飞得更高'


i = people()
i.age = 28
print(i.age)
print(i.fly())
```

##  3 安装库
pip install requests
![pip install requests](http://pwqtqal1m.bkt.clouddn.com/FswDqUTnxKBb2VPbAQYXJzWVezsB)
## 4 导入库
```Python
import requests
from lxml import etree
```
一般的用法就是上面那两个，直接 import 和 from ... import ...

可以这样理解，直接 import 就是直接把一个群聊里面的人都叫出来，用不用的上到时候再说。

from ... import ... 意思就是从一个群中找某个人出来帮忙。

下面这个的用法也是对的，就相当于起别名。

import 亚洲舞王·尼古拉丁·赵四 as 赵四
```Python
import requests as res
from lxml import etree as es
```

## 5 循环
下面这一句的代码就是依次输出 0 到 4 
```Python
for i in range(0, 5):
    print(i)
```
下面这个和上面那个是一样的，0是开始值，5是结束的值，1是步长，也就是间隔。
意思就是说从 0 开始，每隔 1 就输出一次，到 5 就结束，不输出了。
```Python
for i in range(0, 5, 1):
    print(i)
```
猜一下下面这个代码是在干什么
```Python
for i in range(4, -1, -1):
    print(i)
```


## 6 判断
如果为真，输出是的，如果为假，输出不是。
```Python
if True:
    print("是的")
else:
    print("不是")
```
一般的编程语言中，if... else... 是一对的，if... else if...是一对的

python 比较简洁，if... elif...是一对的。
```Python
if False:
    print("假的")
elif True:
    print("是")
else:
    print("非常假")
```
## 7 课后作业
题目：
![题目](http://pwqtqal1m.bkt.clouddn.com/Fr0PpRE7NYWf2fzHSCWbJoip0rB3)
提示：
![题目的提示](http://pwqtqal1m.bkt.clouddn.com/FtN0VHsKU2ckAbs-YkXeJ9kED328)
菜鸟教程的链接，去看一下
[https://www.runoob.com/python3/python3-tutorial.html](https://www.runoob.com/python3/python3-tutorial.html)