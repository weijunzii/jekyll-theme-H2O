---
layout: post
title: '安装 SSR 服务端'
subtitle: '嘿嘿嘿~'
date: 2018-10-08
author: 伪君子
categories: 技术，编程
cover: ''
tags: 安装

---

* content
{:toc}
## 0 安装 SSR 服务端

```markup
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

复制过去后就能看见下图这样的提示，我这里是安装ssr，所以选择2，接着就是要输入密码，回车，密码一定要记住！
![](https://upload-images.jianshu.io/upload_images/2989110-f24f631d1e3c922b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输入密码后会显示给你看的
![](https://upload-images.jianshu.io/upload_images/2989110-114551a5d839437a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着是端口，选择一个合适的端口（推荐五位数），然后回车，回车后能看见下图，需要选择加密方法。

我选择的是 ```11) chacha20-ietf```
![](https://upload-images.jianshu.io/upload_images/2989110-7694a113f0e5ab3c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着是协议，我选择的是```5) auth_aes128_md5```
![](https://upload-images.jianshu.io/upload_images/2989110-bcc7ff7a7eef824e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
obfs 是混稀方式，我选择的是```6) tls1.2_ticket_auth```
![](https://upload-images.jianshu.io/upload_images/2989110-b49365ed64365d50.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
回车之后再随便按一下才能开始安装，花的时间不算多，喝口水，出点零食就可以了，大概也就两三分钟的事情。

接着就能看见类似这样的显示了，IP、端口、密码、协议等都显示出来，ssr 链接都有，二维码也保存到特定的目录下，接下来的事情，嘿嘿嘿，不多说了。

记住 IP 和密码，不然就重装吧
![](https://upload-images.jianshu.io/upload_images/2989110-43c89f1148eb9d66.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

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

参考链接：[https://tingtalk.me/fq/](https://tingtalk.me/fq/)