---
layout: post
title: '给网线接水晶头'
subtitle: '如果细心一点，其实也不难~'
date: 2018-09-03
author: 伪君子
categories: 技术，编程
cover: ''
tags: 

---

* content
{:toc}
##  0  准备
首先，我们要准备好工具和材料，测线器、网线钳，网线、水晶头、剥线器。如果找不到或者没有剥线器，可以选择用网线钳代替剥线器。
![](https://upload-images.jianshu.io/upload_images/2989110-d0c83e4831681703.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  1 剥线

用网线钳或者剥线器把网线断口处 2-3cm 的电线外层剥掉，如下图所示。
![](https://upload-images.jianshu.io/upload_images/2989110-7425e1661f9d68ae.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##  2 理清网线

交叉线的做法是：一头采用568A标准，一头采用 568B 标准 ；平行线的做法是：两头同为 568A 标准或 568B 标准。

我这里用的是平行线法，两头同为 568B，一般都是用这个接法的,网线的顺序是：

>白橙-橙-白绿-蓝-白蓝-绿-白棕-棕

![](https://upload-images.jianshu.io/upload_images/2989110-9dc88eebc7d1bb48.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  3 将网线剪齐

用网线钳的剪线口将线剪齐，就是下图中圈住的地方。
![](https://upload-images.jianshu.io/upload_images/2989110-37dacbdf726b7ee5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##  4 插线
把水晶头有活动卡口的那一面朝下，然后把网线并排插入水晶头线隙，注意顺序不能乱。
![](https://upload-images.jianshu.io/upload_images/2989110-48aa305d78a81ca4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  5 压制
把水晶头放在压线钳里，将线钳与水晶头簧片对齐，用力把水晶头钳紧，这样就压制好了。
![](https://upload-images.jianshu.io/upload_images/2989110-b2ad21d485e7063c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  6 测线
测线器要上场了，启动测线器，两端接上线。如果 1-8 号指示灯依次顺序闪烁，就说明网线接制成功；如果有一个不亮，说明有故障。得分别检查一下网线，水晶头，检测仪，看看哪里出问题了。如果是水晶头不行，剪断重来。

可以查看视频：[https://v.qq.com/x/page/w1347tbidl8.html](https://v.qq.com/x/page/w1347tbidl8.html)

如果另一端的线是不可以移动的，那就把可移动的那一端插到电脑上，然后按下 win+R，
![](https://upload-images.jianshu.io/upload_images/2989110-993820d1ac43d57b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输入 cmd，接着回车。输入 ping 192.168.1.1，然后回车查看情况。如果显示 **数据包: 已发送 = 4，已接收 = 4，丢失 = 0 (0% 丢失)**，那说明线是没问题的，搞定，收工。
![](https://upload-images.jianshu.io/upload_images/2989110-6905bb7b6d2c775c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
192.168.1.1 属于保留 IP，专门用于路由器设置。我们也可以 ping www.baidu.com。

![](https://upload-images.jianshu.io/upload_images/2989110-3bb00551c4459046.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  7 相关说明
其实也不难，就是过程要小心一点，顺序不要搞错，不要走神，基本上就能搞定了。

参考链接：[https://zhuanlan.zhihu.com/p/33718585](https://zhuanlan.zhihu.com/p/33718585)