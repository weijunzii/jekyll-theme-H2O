---
permalink: /2018/09/03/Make-RegisteredJack-For-Cable.html
title: 给网线接水晶头
subtitle: 如果细心一点，其实也不难~
cover: ""
author: 君子
tags: null
date: 2018-09-03
layout: post
categories: 技术，编程
---

* content
{:toc}
##  0  准备
首先，我们要准备好工具和材料，测线器、网线钳，网线、水晶头、剥线器。如果找不到或者没有剥线器，可以选择用网线钳代替剥线器。
<img data-src="https://img.lbjheiheihei.xyz/FqqPp6TTiIqesJDhLTIqKCUN7BVJ" class="lazyload"  alt="工具和材料" title="工具和材料">

##  1 剥线

用网线钳或者剥线器把网线断口处 2-3cm 的电线外层剥掉，如下图所示。
<img data-src="https://img.lbjheiheihei.xyz/FiCTpGfOSC9mRLDQgzZpLHau2knF" class="lazyload"  alt="剥线" title="剥线">


##  2 理清网线

交叉线的做法是：一头采用568A标准，一头采用 568B 标准 ；平行线的做法是：两头同为 568A 标准或 568B 标准。

我这里用的是平行线法，两头同为 568B，一般都是用这个接法的,网线的顺序是：

>白橙-橙-白绿-蓝-白蓝-绿-白棕-棕

<img data-src="https://img.lbjheiheihei.xyz/FkVSWDt8OT0MmhSa-Dulhz9XgJ_1" class="lazyload"  alt="白橙-橙-白绿-蓝-白蓝-绿-白棕-棕" title="白橙-橙-白绿-蓝-白蓝-绿-白棕-棕">

##  3 将网线剪齐

用网线钳的剪线口将线剪齐，就是下图中圈住的地方。
<img data-src="https://img.lbjheiheihei.xyz/FnE6eDfKx3CogqM8EVjC_uJT5K-p" class="lazyload"  alt="将网线剪齐" title="将网线剪齐">

##  4 插线
把水晶头有活动卡口的那一面朝下，然后把网线并排插入水晶头线隙，注意顺序不能乱。
<img data-src="https://img.lbjheiheihei.xyz/Fj28KZKOxyy3gCdoCtnibVXhph57" class="lazyload"  alt="插线" title="插线">

##  5 压制
把水晶头放在压线钳里，将线钳与水晶头簧片对齐，用力把水晶头钳紧，这样就压制好了。
<img data-src="https://img.lbjheiheihei.xyz/FrjAC1iI9X4114sJooKu8dpLpp3w" class="lazyload"  alt="压制" title="压制">

##  6 测线
测线器要上场了，启动测线器，两端接上线。如果 1-8 号指示灯依次顺序闪烁，就说明网线接制成功；如果有一个不亮，说明有故障。得分别检查一下网线，水晶头，检测仪，看看哪里出问题了。如果是水晶头不行，剪断重来。

可以查看视频：[https://v.qq.com/x/page/w1347tbidl8.html](https://v.qq.com/x/page/w1347tbidl8.html)

如果另一端的线是不可以移动的，那就把可移动的那一端插到电脑上，然后按下 win+R，
<img data-src="https://img.lbjheiheihei.xyz/Ft7cJT9NF0Kk0AX9hjhaQnyM5rwe" class="lazyload"  alt="win+R" title="win+R">

输入 cmd，接着回车。输入 ping 192.168.1.1，然后回车查看情况。如果显示 **数据包: 已发送 = 4，已接收 = 4，丢失 = 0 (0% 丢失)**，那说明线是没问题的，搞定，收工。
<img data-src="https://img.lbjheiheihei.xyz/Fp4P8vjWRW-vepPY92IB19tt6j8z" class="lazyload"  alt="ping 192.168.1.1" title="ping 192.168.1.1">

192.168.1.1 属于保留 IP，专门用于路由器设置。我们也可以 ping www.baidu.com。

<img data-src="https://img.lbjheiheihei.xyz/FgrN_LnJJ3SS0wI7yDOq3W17eXa9" class="lazyload"  alt="ping www.baidu.com" title="ping www.baidu.com">

##  7 相关说明
其实也不难，就是过程要小心一点，顺序不要搞错，不要走神，基本上就能搞定了。

参考链接：[https://zhuanlan.zhihu.com/p/33718585](https://zhuanlan.zhihu.com/p/33718585)