---
layout: post
title: '用 Python 爬微信公众号'
subtitle: '基于搜狗微信搜索的微信公众号爬虫'
date: 2018-04-13
author: 伪君子
categories: 技术
cover: ''
tags: Python 爬虫 微信

---

* content
{:toc}
#  0  前言

***

最近想搞一点秘密的小东西，然后就发现了一个非常有用的库 *wechatsogou*，听个名字你就大概能猜出是什么来的了，基于搜狗微信搜索的微信公众号爬虫接口，有了这个就可以玩起来了。

#  1  环境说明

***

Win10 系统下 [Python3](http://mp.weixin.qq.com/s/cubyNsqX4Hg1Zo7CChY8Aw)，编译器是 [Pycharm](http://mp.weixin.qq.com/s/ygVuD0UOFGxtwWfbQHXDAg)，需要安装 [wechatsogou](https://github.com/Chyroc/WechatSogou) 这个库



这里只介绍 [Pycharm](http://mp.weixin.qq.com/s/a06B-wLMyRWT1uY7uTP7lA) 安装第三方包的方法。
<p><img src="http://image.135editor.com/files/users/404/4043688/201802/FHGW8HvR_rrTj.png" alt="一" style="box-shadow: rgb(102, 102, 101) 3.53553px 3.53553px 8px; margin: 0px 8px 8px 0px; border-radius: 4px;" _src="http://image.135editor.com/files/users/404/4043688/201802/FHGW8HvR_rrTj.png"></p><p><img src="http://image.135editor.com/files/users/404/4043688/201802/tIAVkLmj_DYYr.png" alt="二" style="box-shadow: rgb(102, 102, 101) 3.53553px 3.53553px 8px; margin: 0px 8px 8px 0px; border-radius: 4px;" _src="http://image.135editor.com/files/users/404/4043688/201802/tIAVkLmj_DYYr.png"></p>

# 2  相关代码

***

## 2.1  搜索公众号信息

 ```python
	import wechatsogou  # 导入库
        ws_api = wechatsogou.WechatSogouAPI()  # 初始化
        print(ws_api.search_gzh('萧北月'))  #  搜索公众号
 ```
代码运行后会显示一个验证码，自己人工识别一下，再把验证码输入到```please input code:```那就好（6个字符的是搜狗的验证码，4个字符的是微信的验证码）

![运行结果](https://upload-images.jianshu.io/upload_images/2989110-f513b1771f24824f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
*运行结果:*

<pre><code class="language-css">[{'open_id': 'oIWsFt_dPYnbltzh3qPwi3J7XqJQ',
 'profile_url': 'http://mp.weixin.qq.com/profile?src=3&timestamp=1523616541&ver=1&signature=9yFqnyyzkqK3sQAV6KIW9OTb4BXx0lLrKzpdUHK6A5XaTmAtB8TeoKTM7vdE89u5adoYWw2OcQleRlMtOF7rw==', 
'headimage': 'http://img01.sogoucdn.com/app/a/100520090/oIWsFt_dPYnbltzh3qPwi3J7XqJQ', 
'wechat_name': '萧北月', 'wechat_id': 'beiyue_lbj', 
'qrcode': 'http://mp.weixin.qq.com/rr?src=3×tamp=1523616541&ver=1&signature=WVOGii0G4xYwtQWrMW5Ha2ufILN0pB992K5zAIhSiWXOh8Nd0HOoliGVjm5eIla0sPZ5YW7QvzMAwrVsB2UjPnNGFk4UwDB6kDGNbP4k=', 
'introduction': '分享我的所思所想,也分享实用又有趣的东西', 
'authentication': '\n', 'post_perm': -1, 'view_perm': -1}]</code></pre>

把 profile_url 是最近10条群发页链接，把后链接复制到浏览器打开，可以看见下面这样的东西。
![](https://upload-images.jianshu.io/upload_images/2989110-f7bdde45620a0091.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

是的，就是历史消息，仔细一看就能发现只有 10 条历史消息。链接是临时链接，也就是说，这个链接会失效，具体时间我没仔细测试一下。

headimage 就是我公众号的头像；wechat_id 是我公众号的微信 id；qrcode 是公众号二维码的链接；introduction 是公众号简介，或者说是功能介绍；authentication 是认证，个人认证就是这样；post_perm 是最近一月群发数；view_perm 是最近一月阅读量。

>'introduction': '党委中心组时政、理论学习、管理、交流平台', 'authentication': '中国共产党四川省委员会讲师团', 'post_perm': 121, 'view_perm': 48}

抱歉了，某公众号的运营团队，用你们的数据说说话。

## 2.2  微信公众号文章

代码如下

<pre><code class="language-python">
import wechatsogou
ws_api = wechatsogou.WechatSogouAPI()
print(ws_api.search_article('萧北月'))  # 关键词是萧北月，不是说爬我公众号的文章
</code></pre>

运行结果是一大堆的东西，，这里只能爬取一部分的文章
![](https://upload-images.jianshu.io/upload_images/2989110-ab4b45b6e9cf3941.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<pre><code class="language-css">
{'article': {'title': '用Python 制作微信好友个性签名词云图', 
'url': 'http://mp.weixin.qq.com/s?src=11&timestamp=1523618973&ver=814&signature=vBZrfexBBbHDqRnEJyMsdimKvg8fJoyg8ca1iZKYUdw63s6kNtkI1H-0hz0glHvQhGKKYMntSPsm8YbqIrpnC4F3-cKLbjBZxtlFTdLEiP7NlQLpX8ZntMWOpXoWJ&new=1', 
             
'imgs': ['http://img01.sogoucdn.com/net/a/04/link?appid=100520033&url=https://mmbiz.qlogo.cn/mmbiz_jpg/Wz5hZDg47G3skibMYwMeVYxTl3vSNbdBXAib3FqhUMKtq8VUF5T0Rlib4iaHww8eLc7Xib0XtJrfVxbqPYzFuwKxttQ/0?wx_fmt=jpeg'], 
             
'abstract': '4.相关说明参考链接:http://blog.csdn.net/Lee20093905/article/details/79052795萧北月beiyue_lbj', 
'time': 1521553773}, 

'gzh': {'profile_url': 'http://mp.weixin.qq.com/profile?src=3×tamp=1523618973&ver=1&signature=9yFqnyyzkqK3sQAV6KIW9OTb4BXx0lLrKzpdUHK6A5XaTmAtB8TeoKTM7vdE89uWk1krt44mHni8OuheHFg==', 
        
'headimage': 'http://wx.qlogo.cn/mmhead/Q3auHgzwzM5RZypia1GRRNpCEFqFdc50eDT4ADqDbbtibAm3embortYA/0', 
'wechat_name': '萧北月', 'isv': 0}} 
</code></pre>

 isv  ：是否加 v，只能是 1 或 0。1 就是加 v，0 就是没有。

## 2.3  首页热门页

<pre><code class="language-python">
from pprint import pprint
from wechatsogou import WechatSogouAPI, WechatSogouConst

ws_api = WechatSogouAPI()
gzh_articles = ws_api.get_gzh_article_by_hot(WechatSogouConst.hot_index.food)
for i in gzh_articles:
    pprint(i)
</code></pre>

*运行结果：*
![](https://upload-images.jianshu.io/upload_images/2989110-9b590eaf4e5da10e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```python
 'main_img': 'http://img01.sogoucdn.com/net/a/04/link?appid=100520033&url=http%3A%2F%2Fmmbiz.qpic.cn%2Fmmbiz_jpg%2F0oVicD6cYHuGN2NpoWgNed6AzUsP0kukbx7zy57F8EWoATvhwvNp0e060sGACINVliaQtKZWDFhTQWbIAAV4iaibfA%2F0%3Fwx_fmt%3Djpeg',

             'open_id': 'oIWsFt_2q1cK2d6Yvp44XKZ-tnIQ',
             'time': 1523616378,
             'title': '史上最短下学期,考试接二连三!快被考糊的学生该怎么办?',
             'url': 'http://mp.weixin.qq.com/s?src=11&timestamp=1523619725&ver=814&signature=pP52bN2UflHFFApeiYSOwi-ytTCETF*jdMKnykZM76QTUDylYKtAQlq1rzyVr2VdiIf7oQQSxbZ9cXc45mmrtmSAbwegWucocQBr9T0WfoSTNxpYPBZ2SZ8diiQOOJUG&new=1'},

 'gzh': {'headimage': 'http://img04.sogoucdn.com/app/a/100520090/oIWsFt_2q1cK2d6Yvp44XKZ-tnIQ',

         'wechat_name': '中华资源库'}}
```

​            

## 2.4  公众号最近文章

<pre><code class="language-css">
import wechatsogou

ws_api = wechatsogou.WechatSogouAPI()
print(ws_api.get_gzh_article_by_history('萧北月'))  #这次是真的爬我公众号的文章
</code></pre>



这里只能爬最近 10 篇的文章，不过也足够了。

<pre><code class="language-css">
{'gzh': {'wechat_name': '萧北月', 'wechat_id': 'beiyue_lbj', 'introduction': '分享我的所思所想，也分享实用又有趣的东西', 'authentication': '分享我的所思所想，也分享实用又有趣的东西', 'headimage': 'http://wx.qlogo.cn/mmhead/Q3auHgzwzM5RZypia1GRRNpCEFqFdc50eDT4ADqDbbtibAm3embortYA/0'},

'article': [{'send_id': 1000000020, 'datetime': 1523019431, 'type': '49', 'main': 1, 

'title': '使用 Python 伪造数据', 'abstract': '真真假假，假假真真', 'fileid': 100000203, 

'content_url': 'http://mp.weixin.qq.com/s?timestamp=1523621534&src=3&ver=1&signature=opv39vxOL922oluCYH8yziQFqKCpCpXToynePDglJpOXIBfFy8GHUzmr6g9zZhxcdImimyts8JgLsSWJ0z5TnQpeHkpt9pfSDvtM5e3ak9ZVyEnq356ORsDA8p3-fsF67-TNZcoAi178tyVVauFctqphpsn7igxPcQbponoi4=', 

'source_url': 'https://github.com/joke2k/faker', 'cover': 

'https://mmbiz.qlogo.cn/mmbiz_jpg/Wz5hZDg47G3LckVXsS41ibb19AoOShI8S4DJOocPHbKpDSN3Btt0KUFoPmacdIpibLUWlxw9Omm9XVeEJsiaWrOCA/0?wx_fmt=jpeg', 

'author': '伪君子', 'copyright_stat': 11},
</code></pre>

如果没猜错，send_id 就是发的第几篇文章；datetime 我没看透，不知道 10 位时间戳是什么意思； type 是消息类型，网页端最近10条消息页只有49，表示图文消息；main 是群发的第几条消息，1 是第一条；content_url 是文章链接；source_url 是原文链接；copyright_stat 表示是否原创，11是原创。

##2.5  关键词联想

<pre><code class="language-python">
import wechatsogou

ws_api = wechatsogou.WechatSogouAPI()
print(ws_api.get_sugg('美女'))  # 获取关键字联想词
</code></pre>


分别试试美女，谷歌，腾讯，结果还行。
![](https://upload-images.jianshu.io/upload_images/2989110-7d10c58fd6499367.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  3  相关说明

***

WechatSogou 的说明文档：[https://github.com/Chyroc/WechatSogou](https://github.com/Chyroc/WechatSogou)

