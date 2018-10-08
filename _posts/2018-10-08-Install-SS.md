---
layout: post
title: '安装 SS 服务端'
subtitle: '嘿嘿嘿~'
date: 2018-10-08
author: 伪君子
categories: 技术，编程
cover: ''
tags: 安装

---

* content
{:toc}


## 0 安装 ss 服务端
把下面的代码复制到你的服务器，然后回车
```markup
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```
接着会出现这个，现在要输入一个密码，这个密码就是你以后用 ss 的密码了
![](https://upload-images.jianshu.io/upload_images/2989110-be723bb0235c25a8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
输入密码后会显示密码给你看的，一定要记住
![](https://upload-images.jianshu.io/upload_images/2989110-ab7c768a1e762fed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后是端口，选择自己喜欢的就好，大佬给我的建议是选择 5 位数的端口
![](https://upload-images.jianshu.io/upload_images/2989110-b52148fcd737b255.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
加密方式我选择的是 14
![](https://upload-images.jianshu.io/upload_images/2989110-634c6ca54267e2a2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
回车之后再随便按一下才能开始安装，花的时间不算多，喝口水，出点零食就可以了，大概也就两三分钟的事情，安装完后就能看见这个。

![](https://upload-images.jianshu.io/upload_images/2989110-f5291091bef1ea73.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 1 安装锐速

复制过去，回车，显示一堆东西出来后再随便按一下键盘

```markup
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
```

搞定之后显示要重启，输入y，再回车就好
![](https://upload-images.jianshu.io/upload_images/2989110-e0e2bf4488716843.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


```markup
systemctl status shadowsocks -l 
```
查看 SS 服务是否启用成功，出现下图说明就成功启用了
![](https://upload-images.jianshu.io/upload_images/2989110-8791010ca4c55218.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2 说明

剩下的事情可以看这里，毕竟[翻越思维的墙](https://weijunzii.github.io/2018/07/31/To-Climb-Over-The-Wall.html#3ss-或-ssr-翻越)这部分我还是写过的。

参考链接：[https://www.jianshu.com/p/f9854e8a708e](https://www.jianshu.com/p/f9854e8a708e)