---
layout: post
title: '爬取 2019 年数学建模国赛中， C 题的数据'
subtitle: '提供了我写的示例代码，不提供思路'
date: 2019-09-27
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 前言
数学建模国赛那会，一堆人找我，问我能不能爬机场 / 出租车的数据。

一开始我只是以为是学校老师闲得无聊布置的任务，后来来的人多了，我就感觉不太对路了。没理由好几十号人都是同一个老师 / 导师，要求是这么奇葩的。

我稍微搜索了一下，被我发现了。要不是我机灵，我可能就被搞翻车了，一个都不回复，不给数据不给代码，只给了一个链接。
![C 题的题目](http://img.lbjheiheihei.xyz/FvLvwjP2KjAUhgqdIXfwdHMpKT1d)
我找到的网页： http://www.whalebj.com/xzjc/default.aspx

到了现在，公布一下代码也是可以的。
![页面内容](http://img.lbjheiheihei.xyz/FpZ85VNkM-NSRBMvhJAvsolZd6nX)

## 1 环境说明
Win10 系统下 Python3，编译器是 Pycharm。

需要安装 requests，lxml 这两个第三方库，直接 pip install 就可以了

## 2 相关代码
先导包, csv 是用来操作 csv 文件的，time 这里是用来控制时间间隔的，requests 用来请求网页，lxml 用来解析网页数据。
```Python
import csv
import time
import requests
from lxml import etree
```
然后创建一个 csv 文件来保存数据，Airport_Taxi-10s.csv 是文件的名字，以 w 模式打开，也就是说是新建一个文件，文件编码是 utf-8-sig，这个是为了解决中文乱码才使用的。

csv_head 就是标题，就是下图圈出来的这个玩意。

![csv_head](http://img.lbjheiheihei.xyz/FqDsWxO0V8kuFRfW34gZmpF8EGW2)

```Python
with open("Airport_Taxi-10s.csv", "w", encoding='utf-8-sig', newline="") as f:
    csv_write = csv.writer(f)
    csv_head = ["时间", "场内待运车辆数", "前半小时进场车辆数", "前半小时离场车辆数"]
    csv_write.writerow(csv_head)
```

接下来的是一个 get_info() 函数，目的是获取数据，然后保存到 csv 文件里 。

先是用 requests 去请求网页，获得网页的源代码，也就是 res.text。

接着把 res.text 扔进 etree.HTML() 来解析一下，然后把解析之后的结果赋给 htmlparser。

接着是用 Xpath 去定位需要的内容。如下图所示，//*[@id="Label_Msg"]/text()[3] 这个 Xpath 对应的文字就是当前的时间。

别的数据也是有规律的，直接改改就能获取到了。

![Xpath](http://img.lbjheiheihei.xyz/Fl-gAKduk2sIuuBG56MOdVgS_WXz)

接着是进行一下替换，把不需要的文字替换成空。

```now_time = now_time[0].replace("截止目前为止（", "").replace("）", "")```

最后打开该 csv 文件，把爬下来的数据以 a+ 也就是追加的模式加到文件里面，然后关闭文件。
```Python
def get_info():
    try:
        res = requests.get("http://www.whalebj.com/xzjc/default.aspx")
        htmlparser = etree.HTML(res.text)

        now_time = htmlparser.xpath('//*[@id="Label_Msg"]/text()[3]')
        car = htmlparser.xpath('//*[@id="Label_Msg"]/text()[5]')
        in_car = htmlparser.xpath('//*[@id="Label_Msg"]/text()[7]')
        out_car = htmlparser.xpath('//*[@id="Label_Msg"]/text()[9]')

        now_time = now_time[0].replace("截止目前为止（", "").replace("）", "")
        car = car[0].replace("场内待运车辆数为：", "").replace("；", "")
        in_car = in_car[0].replace("前半小时进场车辆数为：", "").replace("；", "")
        out_car = out_car[0].replace("前半小时离场车辆数为：", "").replace("；", "")

        print(now_time, car, in_car, out_car)

        row = [now_time, car, in_car, out_car]
        out = open("Airport_Taxi-10s.csv", "a+", encoding='utf-8-sig', newline="")
        csv_writer = csv.writer(out, dialect="excel")
        csv_writer.writerow(row)

        out.close()
        print()

    except Exception as e:
        print(e)
```

接下来的就是简单的了， 写一个死循环去调用 get_info() 这个函数

时间间隔是 10 秒，time.sleep(10)，这里可以把时间间隔调整，时间间隔改成 10 分钟也行。
```Python
while True:
    get_info()
    time.sleep(10)
```

## 3 相关说明

其实数据多得是，多想想。

我这里是往简单了写，如果需要长时间稳定运行的话，可能还是得改改代码。

但是，我懒😂