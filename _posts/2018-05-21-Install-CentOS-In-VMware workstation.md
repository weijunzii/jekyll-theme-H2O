---
layout: post
title: '在 VMware workstation 安装 CentOS 虚拟机'
subtitle: '安装 CentOS 虚拟机，详细到我想哭'
date: 2018-05-21
author: 伪君子
categories: 技术，编程
cover: ''
tags: CentOS 虚拟机 VMware workstation

---

* content
{:toc}


#  0  前言
上一篇介绍了怎么[安装 VMware workstation Pro](https://weijunzii.github.io/2018/05/20/install-VMware-Workstation.html)，安装完肯定是要装虚拟机啊，下面就来介绍一下怎么安装 CentOS 7.

#  1  下载
去官网下载
>[https://www.centos.org/download/](https://www.centos.org/download/)

推荐下载 DVD ISO；Everything ISO 太大，要下载好久；Minimal ISO 太小，连用户界面都没有。
![](https://upload-images.jianshu.io/upload_images/2989110-d7ec3002f4d4180f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
因为要节约带宽，所以不能直接从官网下载，要选择镜像网站，随意选择一个就好。
![](https://upload-images.jianshu.io/upload_images/2989110-47dcab1363d9d6e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>阿里云的镜像：[https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
>清华大学的镜像：[https://mirrors.tuna.tsinghua.edu.cn/centos/](https://mirrors.tuna.tsinghua.edu.cn/centos/)

选择合适的进行下载，后面都标有具体大小的，不过看起来没那么舒适。
![](https://upload-images.jianshu.io/upload_images/2989110-6c7182f3b4f22ece.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
CentOS-7-x86_64-DVD-1708.iso 的大小是 4.21 GB，CentOS-7-x86_64-Minimal-1708.iso 的大小是 792 MB，看着下载吧，我还是推荐下载 DVD 的，因为我下面就是用这个安装的。

#  2  创建虚拟机
打开 VMware workstation Pro，选择创建新的虚拟机。
![](https://upload-images.jianshu.io/upload_images/2989110-eae50d7dff4c8401.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择默认的典型，然后选择下一步。
![](https://upload-images.jianshu.io/upload_images/2989110-a1406eee8bbfab93.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择安装光盘映像文件(iso），这里的 iso 就是之前下载的 iso 文件，
![](https://upload-images.jianshu.io/upload_images/2989110-9f2c50d8ae6caa61.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
找到之后就选中它，然后点击下一步。
![](https://upload-images.jianshu.io/upload_images/2989110-f06264a5d42b336c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
把虚拟机名称改成自己能够准确识别的名称，位置最好改一下，放在系统盘真的不好，然后点击下一步。
![](https://upload-images.jianshu.io/upload_images/2989110-a6f9e8628bf4ef14.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这里自行选择最大磁盘大小，是否拆分为多个文件，一般说来，选择默认的就好。我这里选择了 50G，主要是我真的需要这么大的空间。
![](https://upload-images.jianshu.io/upload_images/2989110-f4b176055791570e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
到这里后，点击完成，然后就创建完虚拟机了
![](https://upload-images.jianshu.io/upload_images/2989110-236896184309c4a2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  3 安装 
创建完虚拟机就需要安装，在这个界面选择 Install CentOS 7 ，然后回车
![](https://upload-images.jianshu.io/upload_images/2989110-97497de1688bc1cf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
一行一行的命令行就会出现，快速地闪过
![](https://upload-images.jianshu.io/upload_images/2989110-72d566b96602c3a8.gif?imageMogr2/auto-orient/strip)
在安装镜像加载到内存完成后，就可以看到这个欢迎界面

![](https://upload-images.jianshu.io/upload_images/2989110-e85172766305fba4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
下划，选择好语言，继续
![](https://upload-images.jianshu.io/upload_images/2989110-9e8e7e3f6bb41fec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后就会进入这个界面一般说来，日期和时间、键盘、语言支持、安装源都不用再看了，直接默认就好
![](https://upload-images.jianshu.io/upload_images/2989110-dc225f622b45b547.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果想让虚拟机连接到网络，请在*网络和主机名*那打开以太网
![](https://upload-images.jianshu.io/upload_images/2989110-810672dcd51ee0a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

软件选择这里非常重要，默认的是最小安装，安装完后是没有桌面的。所以要进去修改一下

**GNOME 桌面环境**可以这样选择，供你参考
![](https://upload-images.jianshu.io/upload_images/2989110-adf8f2facf3cbcdc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**KDE** 的话，可以这样选择。还是供你参考
![](https://upload-images.jianshu.io/upload_images/2989110-2f710e875b5d4450.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果是**带 GUI 的服务器**，你看着来吧，我没试过。
![](https://upload-images.jianshu.io/upload_images/2989110-6f4ad10939fda157.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这里我选择的是 GNOME 桌面环境，确保所需要的东西都搞定了之后，选择开始安装
![](https://upload-images.jianshu.io/upload_images/2989110-5fb95ab853b29199.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击开始安装后你会看到这个界面，需要去设置 ROOT 密码，还需要创建一个用户
![](https://upload-images.jianshu.io/upload_images/2989110-bf9c3df05ff70bc8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
先把 root 用户的密码搞定，这个一定要记下来，忘记了的话，之后都不用不了 root 权限。

root 账户是每个 Linux 系统的最高管理账户密码，它拥有所有的权限。（包括删库的权限，rm -rf/*)
![](https://upload-images.jianshu.io/upload_images/2989110-a04b8f5ad860bdd9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
再创建一个用户，这个的密码也要记住。用 root 账户运行系统是非常危险的，可能一个不小心就把系统搞废了，所以要创建一个用户。
![](https://upload-images.jianshu.io/upload_images/2989110-580bcf614ee4d2a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

到这里就搞定了，等系统安装完就可以了。要等多久？玄学，不知道，反正挺久的。
看到下面这个就说明安装完了，点击重启。
![](https://upload-images.jianshu.io/upload_images/2989110-c8a2d149201f0841.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  4  进入
如果重启后看到这个，不用慌，点击一下许可证那里，进去确认一下就好。
![](https://upload-images.jianshu.io/upload_images/2989110-a67d67928b0beb80.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后就变成这样，再点击完成配置。
![](https://upload-images.jianshu.io/upload_images/2989110-181b72a17f9d6d60.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
看到这个，说明已经搞定了，输入密码就可以进系统。
![](https://upload-images.jianshu.io/upload_images/2989110-921aa8b680297d5e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入之后，需要设置一下，自己会弹出来的，喜欢怎么来就怎么来。
![](https://upload-images.jianshu.io/upload_images/2989110-1f735ef36e37f66c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](https://upload-images.jianshu.io/upload_images/2989110-c7f57fe2901a1ae1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](https://upload-images.jianshu.io/upload_images/2989110-491cebb700e39dc0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
设置完后，你就会看到这个，开始愉快地使用吧~
![](https://upload-images.jianshu.io/upload_images/2989110-eda3b65a093f2e42.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

文章首发于本人公众号，欢迎关注~
![公众号.png](https://upload-images.jianshu.io/upload_images/2989110-53489b8fa40e90f6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)