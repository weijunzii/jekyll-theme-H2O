---
permalink: /2018/07/10/Crawl-JianShu-Users-Timeline.html
title: 爬取简书用户的动态
subtitle: 有点意思
cover: ""
author: 君子
tags: 编程 Python 简书
date: 2018-07-10
layout: post
categories: null
---

* content
{:toc}
#  0  前言
我在简书关注的一位大佬发了一篇文章，文章大意是一个简书用户假意约稿，其实是想让别人关注微信公众号，大佬写代码去爬取该用户的动态，发现该用户真的是在骗人。

具体细节请看[文章：https://www.jianshu.com/p/35a85ee14f7b](https://www.jianshu.com/p/35a85ee14f7b)

我把大佬的代码复制到本地运行，发现没有把第一页的动态保存下来，于是添加了一点点代码把代码完善了一下。

#  1  环境说明
Win10 系统下 [Python3](https://mp.weixin.qq.com/s/cubyNsqX4Hg1Zo7CChY8Aw)，编译器是 [Pycharm](https://mp.weixin.qq.com/s/ygVuD0UOFGxtwWfbQHXDAg)，需要安装 requests、lxml这两个包。

这里只介绍 [Pycharm 安装第三方包](https://mp.weixin.qq.com/s/a06B-wLMyRWT1uY7uTP7lA)的方法。

<img data-src="https://img.lbjheiheihei.xyz/FiWX1br6ELwKwLQIfQfmFO5je-oT" class="lazyload"  alt="Pycharm 安装第三方包" title="Pycharm 安装第三方包">

<img data-src="https://img.lbjheiheihei.xyz/FqXVEBEtAStmMAD29k5x4NHvFV9M" class="lazyload"  alt="Pycharm 安装第三方包" title="Pycharm 安装第三方包">
#  2  相关代码
```python
import requests
from lxml import etree

my_header = "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36"

res = requests.get(url='https://www.jianshu.com/users/93022c8a49c5/timeline', headers={'user-agent': my_header})

if '大神带我来搬砖' in res.text:
    print('找到了')
page = etree.HTML(res.text)
last_li = page.xpath('''//ul[@class="note-list"]/li[last()]''')[0]
max_id = int(last_li.get('id').split('-')[1]) - 1

file = open("activity.txt",'w',encoding='utf-8')
file.write(res.text)
file.write("\n")

page = 2
while True:
    res = requests.get(url='https://www.jianshu.com/users/93022c8a49c5/timeline?max_id=%s&page=%s' %(max_id,page),
        headers={'user-agent': my_header, 'X-INFINITESCROLL':'true'})

    last_li = etree.HTML(res.text).xpath('''/html/body/li[last()]''')[0]
    max_id = int(last_li.get('id').split('-')[1]) - 1
    page = page + 1
    file.write(res.text)
    file.write("\n")
    if '加入了简书' in res.text:
        print('end')
        break

file.close()
```
这里我爬的是我简书账号的动态，如果想爬取别人的动态需要去拿到动态链接，进去他的主页，在动态那点击一下鼠标右键，然后复制链接地址或者在新标签页打开链接。

<img data-src="https://img.lbjheiheihei.xyz/FvSy0OdKtuuLGLydRtXMx41yT-Mp" class="lazyload"  alt="动态链接" title="动态链接">

替换一下图中圈住的链接
<img data-src="https://img.lbjheiheihei.xyz/FqME2ugpkGvPJsehqwVukzmiq_pG" class="lazyload"  alt="替换链接" title="替换链接">

如果想搜索的不是『大神带我来搬砖』可以自行替换

实际运行结果如图
<img data-src="https://img.lbjheiheihei.xyz/FuUjfx_0FjB0eCoq1kkpjFaFV-tj" class="lazyload"  alt="实际运行结果" title="实际运行结果">

还有一个名字是 activity.txt 的文件在和代码同一级的文件目录下，打开进行搜索就是了。
<img data-src="https://img.lbjheiheihei.xyz/Fti4oz767Aw7RoPmekUesAWsGPCp" class="lazyload"  alt="activity.txt" title="activity.txt">

#  3 相关说明
大佬的[文章链接：https://www.jianshu.com/p/35a85ee14f7b](https://www.jianshu.com/p/35a85ee14f7b)

感谢大佬『大神带我来搬砖』写的代码，感谢大佬同意我水一篇文章

在我写完这篇文章的时候才知道大佬又写了一篇，不过实现方式和代码有所不同，这里也给出[链接：https://www.jianshu.com/p/fdb3cf39f295](https://www.jianshu.com/p/fdb3cf39f295)
