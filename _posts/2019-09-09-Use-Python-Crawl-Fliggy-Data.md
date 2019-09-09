---
layout: post
title: 'Python 爬取飞猪上全国景点的数据'
subtitle: '咋搞哟，现在才更新'
date: 2019-09-09
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 前言
前段时间有人找我写代码爬点东西，就是爬飞猪上全国景点的当月销量、优惠价、城市这些数据，等我写好了之后，他说不要了...

没辙，只能完善一下之后写出来了。
## 1 环境说明
Win10 系统下 Python3，编译器是 Pycharm。

需要安装 requests，bs4，selenium 这个第三方库，直接 pip install 就可以了。还需要配置一下 
 driver，我用的是谷歌浏览器，所以直接用 chromedriver，配置的方法具体看这里。
## 2 代码
万恶之首先导包
```Python
import csv
import time
import requests
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
```

先建一个 csv 文件来保存数据，我不想存储到数据库，只能这样了。
```Python
# 新建一个 fliggy.csv 文件,w 表示是新创建一个文件, encoding 为 utf-8-sig，中文能正常显示,
# newline="" 不能省略，省略了之后，会换行
with open("fliggy.csv", "w", encoding='utf-8-sig', newline="") as f:
    csv_write = csv.writer(f)
    csv_head = ["景点", "城市", "当月销量", "优惠价", "价格"]
    csv_write.writerow(csv_head)
```


newline="" 不能省略，一省略就会导致换行多换了一行，如下图所示
![错误示范](http://pwqtqal1m.bkt.clouddn.com/FmqsMmPkp1DSLsx4x2jIXWL3L_5R)

接着就是配置 chromedriver
```Python
options = Options()
# options.add_argument('--headless')  # headless, 无头浏览器, 不显示用户界面
options.add_argument('--disable-gpu')  # 不使用 gpu
# options.add_argument("--incognito")  # 以隐身模式打开
prefs = {"profile.managed_default_content_settings.images": 2}  # 不显示图片
options.add_experimental_option("prefs", prefs)
# chromedriver.exe 的路径
driver_path = "C:\Program Files (x86)\Google\Chrome\Application\chromedriver.exe"
driver = webdriver.Chrome(executable_path=driver_path, options=options)
```
配置好之后就是开始爬，这里先用广州进行测试，所以 url 是广州的

driver.get(url) 的意思是 chromedriver 去访问这个 url。

```Python
url = 'http://s.fliggy.com/scenic/list.htm?q=广州'
driver.get(url)
print(url)
try:
    # 获取页数
    next_num = driver.find_element_by_xpath("//a[@class='pi-pagination-num'][3]").text
    print(next_num)
except Exception as e:
    # 处理只有一页的情况
    next_num = 1
    print(e)
```

next_num 是 一共有多少页，这个是用 xpath 来定位的，```//a[@class='pi-pagination-num'][3]```, class 名为 pi-pagination-num 的 第 3 个 a 标签就是页数所在的地方。

```next_num = driver.find_element_by_xpath("//a[@class='pi-pagination-num'][3]").text``` 就是把页数对应的文字获取到。
![获取页数](http://pwqtqal1m.bkt.clouddn.com/Fse7KXXeZsoVEyEYaP9ZJ6r8uFBq)

还记得 next_num 吗，它是总页数，所以我们需要一个 for 循环，一页一页去获取数据。

range(0, int(next_num))，从 0 开始到 总页数。Python 中，range(0, 10)的意思是从0 到 9 开始计数，计到 10 结束，但不包括 10。

```Python
for i in range(0, int(next_num)):
    links = driver.find_elements_by_xpath("//a[@class='pi-btn pi-btn-primary']")

    for link in links:
        try:
            print(link.get_attribute("href"))
            res = requests.get(link.get_attribute("href"), timeout=10)
            # print(res.text)
            soup = BeautifulSoup(res.text, 'lxml')
            name = soup.find('h3', {'class': 'scenic-tit'}).get_text().strip()
            city = soup.find('span', {'class': 'scenic-subtit'}).get_text().strip()
            sell_count = soup.find('dl', {'class': 'sell-count'}).find('dd').find('em').get_text().strip()
            scenic_price = soup.find('span', {'class': 'pi-price-lgt'}).get_text().strip()
            price = soup.find('div', {'class': 'right-area'}).find('span', {'class': 'pi-price'}).get_text().strip()

            row = [name, city, sell_count, scenic_price, price]
            # encoding 为 utf-8-sig, 中文能正常显示, 不信的话, 换成 utf-8试试
            out = open("fliggy.csv", "a+", encoding='utf-8-sig', newline="")
            csv_writer = csv.writer(out, dialect="excel")
            csv_writer.writerow(row)
            out.close()
        except Exception as e:
            print(e)
    try:
        # 点击下一页
        driver.find_element_by_class_name('pi-pagination-next').click()
    except Exception as e:
        print(e)
    # 休息 3 秒接着干
    time.sleep(3)

# 搞定收工，退出浏览器
driver.quit()
```
```links = driver.find_elements_by_xpath("//a[@class='pi-btn pi-btn-primary']")``` 是找到网页上所有的 class 属性为 pi-btn pi-btn-primary 的 a 标签。

![找到需要的标签](http://pwqtqal1m.bkt.clouddn.com/FpysWJLVXUVcp4FbqfNt8GOeRm3s)

driver.find_element_by_xpath是找一个，driver.find_elements_by_xpath找所有的，区别就在于 element 后面加没加一个 s。

得到的 links 是一个列表，需要一个一个获取需要的 href 属性，因为这个属性里面的就是景点的链接。

```res = requests.get(link.get_attribute("href"), timeout=10)```的意思就是用 requests 去请求获取到的链接。

```soup = BeautifulSoup(res.text, 'lxml')``` ，res.text 就是获取到的网页源码。用 BeautifulSoup 使用 lxml 解析器解析一下网页源码。（可以把 soup 打印出来看一下）

name 是景点名，city 是景点所在的城市，sell_count 是当月销量，scenic_price 是优惠价，price 是价格。
![对应的位置](http://pwqtqal1m.bkt.clouddn.com/FrYyicnsfE6-8BTQQ2wY0bKkNitg)

这里以 sell_count 来讲解一下代码，```sell_count = soup.find('dl', {'class': 'sell-count'}).find('dd').find('em').get_text().strip()```， 在解析过的网页源码中，也就是 soup 中找到 class 属性为 sell-count 的 dl 标签，然后在 dl 标签里面找到 dd 标签，接着找到 em 标签。

.get_text() 是获取到里面的文字，.strip() 是去掉空格（以防万一）

别的字段都类似 sell_count 这样获取。
![找到需要的文字](http://pwqtqal1m.bkt.clouddn.com/FtmDvCoVp2uBr7-RnWKWVrk1b0Yv)

把数据获取到之后肯定就是保存下来，row 里面就是需要保存的数据。

以追加的形式打开 fliggy.csv，写入数据，然后 ```out.close()``` 关闭 fliggy.csv。
```Python
row = [name, city, sell_count, scenic_price, price]
# encoding 为 utf-8-sig, 中文能正常显示, 不信的话, 换成 utf-8试试
out = open("fliggy.csv", "a+", encoding='utf-8-sig', newline="")
csv_writer = csv.writer(out, dialect="excel")
csv_writer.writerow(row)
out.close()
```
```driver.find_element_by_class_name('pi-pagination-next').click()```, 这个就是点击下一页，前面那一堆是定位到下一页，.click() 就是点击。

最终爬下来的就是下面这样，
![爬下来的数据](http://pwqtqal1m.bkt.clouddn.com/Fl1a6-T804W2Y8OMCrHi8sq4hqWN)

##  3 相关说明
链接是 http://s.fliggy.com/scenic/list.htm?q=广州 就是爬飞猪上广州的景点；把广州改成广东就是爬广东的；改成中国，那就是爬飞猪上全国的景点。

文章还是得多写，好久没写了，居然没感觉了。

本来是懒得写的，但是学 SEO，老师布置了个作业，要露出个外链（[lbjheiheihei.xyz](lbjheiheihei.xyz)），只能不要脸的来写篇文章了。

题图：Photo by Pierre Gillier on Unsplash