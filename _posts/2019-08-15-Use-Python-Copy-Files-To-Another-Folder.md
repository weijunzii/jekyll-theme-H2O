---
layout: post
title: '用 Python 批量把文件复制到另一个文件夹'
subtitle: '不看就亏'
date: 2019-08-15
author: 伪君子
categories:
cover: ''
tags: Python
---

* content
{:toc}
## 0 前言
大概是三个月前，有个人找我说要我帮忙写几行代码，功能是把一个文件夹里面的所有文件拆分成 200 个文件一个文件夹，很简单的。

我理解了之后，觉得还是挺简单的，花了半个小时写出来了，代码也不多，代码和思路都可以分享一下。
## 1 环境说明
Win10 系统下 Python3，编译器是 Pycharm。

需要安装 shutil 这个第三方库，直接 pip install shutil 就可以了。

## 2 代码
先导入需要用到的库，os 是用来切换路径和创建文件夹的。

shutil 是用来复制黏贴文件的
```Python
import os
from shutil import copy
```
i 用来计算文件数量，当 i 是 200 的倍数时，k 会 +1；k 用来计算新建文件夹的数量，方便创建文件夹。

save_dir 是想把复制出来的文件存放在的路径
```Python
# i 用来计算文件数量，k 用来计算新建文件夹的数量
i = 0
k = 0

#  想保存到的根路径
save_dir = r'F:\666'
#  如果目录不存在，则创建
if not os.path.isdir(save_dir):
    os.makedirs(save_dir)
```
dir_name 是新的文件夹的命名；file_path 是想拆分的文件夹所在路径，也就是一大堆文件所在的路径。

os.listdir(file_path) 是获取指定路径下包含的文件或文件夹列表，在 Unix, Windows 下使用。
```Python
#  想保存的名字
dir_name = "junzi"

#  想拆分的文件夹所在路径
file_path = r'F:\ALL'

#  获取 file_path 下的文件和文件夹列表
#  因为 file_path 里面没有文件夹，所以不处理有文件夹的情况
pathDir = os.listdir(file_path)
```

获取到了列表，那就一个一个进行遍历。0 是 200 的倍数，所以一开始 k 的值会 +1 。

allDir 是文件的名字+后缀名。from_path 就是当前这个被遍历出来的文件的完整路径，to_path是这个文件要复制到的路径。

接着 copy(from_path, to_path) 完成复制黏贴，最后 i 自增1.
```python
for allDir in pathDir:
    if( (i%200) == 0):
        print("200 的倍数，新建一个文件夹")
        k += 1

    print(allDir)
    from_path = os.path.join(file_path, allDir)
    to_path = save_dir + "\\" + dir_name + str(k)

    #  如果 to_path 目录不存在，则创建
    if not os.path.isdir(to_path):
        os.makedirs(to_path)
    copy(from_path, to_path)
    i += 1
```

## 3 相关说明
shutil 的 copy() 是复制到一个新的地方，创建时间、修改时间、访问时间都是新的，copy2() 则是会创建时间、修改时间、访问时间这些也复制过去。

就这个简单的程序，喜提 88.88 。可能是这个让我有点飘了，过了没几天，有人找我做外包，整一个简单的小程序，我理解了一下需求，觉得还是简单的，一周就能完事。

一开始还真的挺简单的，后来改了点需求，然后我因为学校的事情耽误了不少实际，甲方因为准备资料花了点时间。

也就是说，这个外包到现在还没结项😂😂
