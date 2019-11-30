---
layout: post
title: 'python 爬取 instagram 用户的关注列表'
subtitle: '我也不想写代码的'
date: 2019-11-30
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 前言
这是很久之前我的房东找我帮忙爬 instagram 上面某个用户的关注列表，一开始我想着减低难度好给他使用，于是尝试了 webscraper，后羿采集器去爬取，结果吭哧吭哧花了两个多小时都没搞定。

于是我就直接写代码来爬取了，用 python 写个代码，半小时就好了🤣
## 1 分析过程
先访问用户主页，然后 F12 打开控制台，接着点击 Network，然后在下面选中 XHR。
![用户主页](http://img.lbjheiheihei.xyz/FnGpRpk5k7Cr4AbOVNs2PIVM-qFL)

在页面中点击 正在关注，会出现下图中圈出的网络请求
![XHR（XML Http Request）](http://img.lbjheiheihei.xyz/FuSKz-EOv5gaMEqU7PCuNOWJ_Mm7)

点击第一个加载出来的请求，然后点击 Preview 查看一下加载的数据是否一致，是否一一对应。

username、followed_by_viewer、profile_pic_url 那些如果一一对应，那就是这个请求了，没找错。
![数据](http://img.lbjheiheihei.xyz/FuK5cmSXNFnraYBYe086E1IwN4zv)

那么点击 Headers ，然后找到 Request Headers。

这里非常重要，Request Headers也就是请求头里面携带了重要的信息 cookie，要是没有 cooike 的话，那就爬取不了了。

代码中需要把请求头里面的信息加上才能爬取内容。
![Request Headers](http://img.lbjheiheihei.xyz/FsVxvzHAvw6I20khWqOTTYETU0N1)

拉到最下面就是 Query String Parameters，请求的参数，query_hash 照着来就好，一般不会变。

variable 里面有个 id ，每个用户的 id 是不同的，所以要爬另一个用户关注的用户列表的话，需要进行替换。
![Query String Parameters](http://img.lbjheiheihei.xyz/FlWY2UUS8Ty2_DqaXjI-FvRIZOnY)
双击这个请求，浏览器会新开一个标签页来访问这个链接。
![链接](http://img.lbjheiheihei.xyz/FmeOgnmGVcwQDI8z0VKqMOl6lsor)
在谷歌扩展程序【JSONVIEW】的加持下，看到是内容是下图这样的；如果不加持的话，所有的文字都是挤在一起的。

简单分析一下， count 应该就是该用户关注了多少个人， has_next_page 就是有没有下一页，end_cursor 是查看下一页的关键，用来构造请求。

每一个 node 里面就是一个用户的信息。
![数据](http://img.lbjheiheihei.xyz/FvxDdQYaZTwq_8CzKevpBUGFU90o)

id 是用户的 id；username 是用户名，是 instagram.com/eltaautomotive 后面的那一个用来标识用户的字符串；full_name 应该类似微信昵称。
![用户界面](http://img.lbjheiheihei.xyz/FqQ4PLtY-rhACquqYLhfjW4u9sKG)

##  2 代码思路
使用 requests 去构造请求，把请求头和参数加上，提取获取到的内容，has_next_page用来判断有没有下一页，end_cursor 用来构造下一个请求，id，username，full_name 是需要的内容，保存到 csv 里面。

## 3 代码 + 解释
首先是导入需要用到的包，这里只有 requests 是需要 pip install requests 进行安装的，别的都是 python 自带的包。

requests 是用来请求网站，获得数据的；json 是把获取到的 json 数据转化为 python 对象；csv 是用来把数据保存到 csv 里面；time 是用来 sleep 的，两个请求之间加上一点时间间隔。
```python
import csv
import json
import requests
from time import sleep
```
先构造一个请求头，把需要的东西进行替换
```python
# cookie 是需要替换的，referer 最好是替换一下
headers = {
    'sec-ch-ua': 'Google Chrome 77',
    'sec-fetch-mode': 'cors',
    'dnt': '1',
    'x-ig-www-claim': 'hmac.AR1P1exDcpFRvpFAYKNm_Wnajygy1QK5l3HC7cN5943dNlY-',
    'accept-language': 'zh-CN,zh;q=0.9,en;q=0.8',
    'sec-fetch-dest': 'empty',
    'x-requested-with': 'XMLHttpRequest',
    'cookie': r'这里是cookie，需要自行替换',
    'x-csrftoken': '1vBpb3wLDDDbC63ckwu06IzIy351nB12',
    'x-ig-app-id': '936619743392459',
    'accept-encoding': 'gzip, deflate, br',
    'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/77.0.3865.75 Safari/537.36',
    'accept': '*/*',
    'referer': 'https://www.instagram.com/linda_ledo_carlights/following/',
    'authority': 'www.instagram.com',
    'sec-fetch-site': 'same-origin',
}
```
然后是 end_cursor ，这个是用来构造下一页的请求链接，一开始为空；has_next 是有没有下一页，用来循环获取列表。
```python
end_cursor = ''
has_next = True
```
下面这个就是一个循环，只有 has_next 不为 True 的时候才退出循环。

params 是请求所带的参数，每一页的参数都是不同的，通过不同的 end_cursor 来访问不同的页数。

然后用 requests 去获取到数据，获取到的数据用 json.loads() 把数据从 json 对象转为 python 对象。

接着从转化之后的数据中获取 has_next、end_cursor 并且赋值。

edges 是用户列表，获取之后遍历一下就能把每一个用户的id, username, full_name 的信息。

打开一个 csv 把爬取到的信息保存进去，关闭 csv，接着程序 sleep 23.3 秒之后判断是否进入 while 循环。（sleep的数值可以修改，但是建议不要低于 5）
```python

while has_next:
    # id是需要替换的，每一个用户的 id 不一样
    params = (
        ('query_hash', 'd04b0a864b4b54837c0d870b0e77e076'),
        ('variables',
         '{"id":"5848320586","include_reel":true,"fetch_mutual":false,"first":12,"after":"' + end_cursor + '"}'),
    )

    response = requests.get('https://www.instagram.com/graphql/query/', headers=headers, params=params).text

    res = json.loads(response)
    has_next = res['data']['user']['edge_follow']['page_info']['has_next_page']
    print(has_next)
    end_cursor = res['data']['user']['edge_follow']['page_info']['end_cursor']
    edges = res['data']['user']['edge_follow']['edges']

    out = open("ig.csv", "a+", newline="", encoding="utf-8-sig")
    csv_writer = csv.writer(out, dialect="excel")

    for i in edges:
        row = [i['node']['id'], i['node']['username'], i['node']['full_name']]
        csv_writer.writerow(row)
        
    out.close()
    sleep(23.3)

print("=============搞定收工==============")
```
把代码从头到尾复制下来，替换一下需要替换的部分，运行之后就能在代码的同级目录下看到一个 ig.csv 的文件，打开之后就能看到数据了。

##  4 相关说明
最近文章：
题图：Photo by Yiran Ding on Unsplash
催更热线