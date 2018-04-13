---
layout: post
title: '使用 Python 伪造数据'
subtitle: '真真假假，假假真真'
date: 2018-04-06
author: 伪君子
categories: 技术
cover: ''
tags: Python 伪造

---

* content
{:toc}
# 0  前言

 某些时刻，因为个人数据不想泄露出去，所以需要伪造一下数据；也有使用爬虫的时候需要换一下 `user agent` ，一个用到旧会被发现的。

运行环境是 Python3， Win10，编译器是 Pycharm。

# 1  个人数据

***

使用的是 [faker](https://github.com/joke2k/faker) 这个包，安装的过程直接省去。下面这段代码是生成简单的个人信息。

语言那可以自己选择，注释那只给出了常用的语言。

## 自己选择

```Python
from faker import Faker

fake = Faker('zh_CN')  # en_US,zh_CN,zh_TW
for _ in range(4):  # 输出4个，方便选择
    print("姓名：" + fake.name() + "    工作：" + fake.job())
    print("公司：" + fake.company())
    print("住址：" + fake.address())
    print("===========")
```

下面是运行结果，职位的本地化还稍微有所欠缺，哪怕选择了中文，职位还是英文的

![运行结果](https://upload-images.jianshu.io/upload_images/2989110-f00fd3c75828afa7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 生成简单信息

如果不喜欢，或者闲麻烦，可以直接调用给出的方法生成简单的个人信息

```Python
from faker import Faker

fake = Faker('zh_CN')  # en_US,zh_CN,zh_TW
print(fake.simple_profile(sex=None))
```

代码运行后的结果就是这样

![简单个人信息](https://upload-images.jianshu.io/upload_images/2989110-ee5a39756a457299.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 生成复杂信息

如果觉得不够详细，可以想下面这样做。

```python
from faker import Faker

fake = Faker('zh_CN')  # en_US,zh_CN,zh_TW
print(fake.profile(fields=None, sex=None))
```

![复杂个人信息](https://upload-images.jianshu.io/upload_images/2989110-7e18138ba90616b1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

还有很多的东西没有写出来，建议去阅读[官方文档](https://faker.readthedocs.io/en/master/)（官方文档是英文的。。）

# 2  爬虫 user_agent 

***

运行爬虫的时候总会加上 user_agent，每一次都是找一堆 user_agent，然后堆在一起，最后用 random 随机选择一个。

```python
user_agent = ["Mozilla/5.0 (Windows NT 10.0; WOW64)", 'Mozilla/5.0 (Windows NT 6.3; WOW64)',
              'Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.64 Safari/537.11',
              'Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) like Gecko',
              'Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/28.0.1500.95 Safari/537.36',
              'Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; .NET4.0C; rv:11.0) like Gecko)',
              'Mozilla/5.0 (Windows; U; Windows NT 5.2) Gecko/2008070208 Firefox/3.0.1',
              'Mozilla/5.0 (Windows; U; Windows NT 5.1) Gecko/20070309 Firefox/2.0.0.3',
              'Mozilla/5.0 (Windows; U; Windows NT 5.1) Gecko/20070803 Firefox/1.5.0.12',
              'Opera/9.27 (Windows NT 5.2; U; zh-cn)',
              'Mozilla/5.0 (Macintosh; PPC Mac OS X; U; en) Opera 8.0',
              'Opera/8.0 (Macintosh; PPC Mac OS X; U; en)',
              'Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.12) Gecko/20080219 Firefox/2.0.0.12 Navigator/9.0.0.6',
              'Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0)',
              'Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Trident/4.0)',
              'Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; WOW64; Trident/6.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; InfoPath.2; .NET4.0C; .NET4.0E)',
              'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.1 (KHTML, like Gecko) Maxthon/4.0.6.2000 Chrome/26.0.1410.43 Safari/537.1 ',
              'Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; WOW64; Trident/6.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; InfoPath.2; .NET4.0C; .NET4.0E; QQBrowser/7.3.9825.400)',
              'Mozilla/5.0 (Windows NT 6.1; WOW64; rv:21.0) Gecko/20100101 Firefox/21.0 ',
              'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.1 (KHTML, like Gecko) Chrome/21.0.1180.92 Safari/537.1 LBBROWSER',
              'Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; WOW64; Trident/6.0; BIDUBrowser 2.x)',
              'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/536.11 (KHTML, like Gecko) Chrome/20.0.1132.11 TaoBrowser/3.0 Safari/536.11']
```

不得不说，麻烦到爆炸，还让代码多出了一堆，既不美观，又显多余。

现在只需用一下 faker 这个包，简简单单就可以弄出一堆的 user_agent 了

![fake](https://upload-images.jianshu.io/upload_images/2989110-b8db0c70c3396fd0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

多种样式，能满足大部分需求。

```python
from faker import Faker

fake = Faker('zh_CN')  # en_US,zh_CN,zh_TW

print(fake.safari())
print(fake.opera())
print(fake.chrome(version_from=13, version_to=63, build_from=800, build_to=899))
print(fake.firefox())
print(fake.user_agent())
```

[官方文档](https://faker.readthedocs.io/en/master/locales/zh_CN.html#faker-providers-user-agent) 那的介绍更加详细，建议多看看

# 3  相关说明

***



faker 的 GitHub：

[https://github.com/joke2k/faker](https://github.com/joke2k/faker)

faker 的说明文档：

[https://faker.readthedocs.io/](https://faker.readthedocs.io/)

