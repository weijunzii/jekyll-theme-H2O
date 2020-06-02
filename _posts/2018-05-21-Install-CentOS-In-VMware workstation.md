---
permalink: /2018/05/21/Install-CentOS-In-VMware-workstation.html
title: 在 VMware workstation 安装 CentOS 虚拟机
subtitle: 安装 CentOS 虚拟机，详细到我想哭
cover: ""
author: 君子
tags: CentOS 虚拟机 VMware workstation
date: 2018-05-21T00:00:00.000Z
layout: post
categories: 技术，编程
---

* content
{:toc}


#  0  前言
上一篇介绍了怎么[安装 VMware workstation Pro](https://weijunzii.github.io/2018/05/20/install-VMware-Workstation.html)，安装完肯定是要装虚拟机啊，下面就来介绍一下怎么安装 CentOS 7.

#  1  下载
去官网下载
>[https://www.centos.org/download/](https://www.centos.org/download/)

推荐下载 DVD ISO；Everything ISO 太大，要下载好久；Minimal ISO 太小，连用户界面都没有。
![centos 官网](https://img.lbjheiheihei.xyz/FjHoCl9Esk1LSvzO2dezu_I2sLb_ ""centos 官网)
因为要节约带宽，所以不能直接从官网下载，要选择镜像网站，随意选择一个就好。
![镜像站](https://img.lbjheiheihei.xyz/FlW2g9mGkpBH53u0UXr30H5nHIEF "镜像站")

>阿里云的镜像：[https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
>清华大学的镜像：[https://mirrors.tuna.tsinghua.edu.cn/centos/](https://mirrors.tuna.tsinghua.edu.cn/centos/)

选择合适的进行下载，后面都标有具体大小的，不过看起来没那么舒适。
![下载 iso](https://img.lbjheiheihei.xyz/FiDpD4nadzizwNQuLo6jI_RfsgpZ "下载 iso")
CentOS-7-x86_64-DVD-1708.iso 的大小是 4.21 GB，CentOS-7-x86_64-Minimal-1708.iso 的大小是 792 MB，看着下载吧，我还是推荐下载 DVD 的，因为我下面就是用这个安装的。

#  2  创建虚拟机
打开 VMware workstation Pro，选择创建新的虚拟机。
![创建新的虚拟机](https://img.lbjheiheihei.xyz/Fgu8nJ2aFZDlC8A44cOikWzs6x_9 "创建新的虚拟机")
选择默认的典型，然后选择下一步。
![典型](https://img.lbjheiheihei.xyz/Fr7BN7yX9cRlOayPc7-XeEJ_lpNe "典型")

选择安装光盘映像文件(iso），这里的 iso 就是之前下载的 iso 文件，
![选择安装光盘映像文件(iso）](https://img.lbjheiheihei.xyz/Fo17TTE8IOl40kSuaYdAmerDBUff "选择安装光盘映像文件(iso）")

找到之后就选中它，然后点击下一步。
![下一步](https://img.lbjheiheihei.xyz/FrCI1wuQyzw8nPCV9Vs4oRAWIAam "下一步")

把虚拟机名称改成自己能够准确识别的名称，位置最好改一下，放在系统盘真的不好，然后点击下一步。

![虚拟机名称](https://img.lbjheiheihei.xyz/Ftk5bttNldq40dmplhMgY015SBpr "")
这里自行选择最大磁盘大小，是否拆分为多个文件，一般说来，选择默认的就好。我这里选择了 50G，主要是我真的需要这么大的空间。

![最大磁盘大小](https://img.lbjheiheihei.xyz/Fj4vBM8IuhzkBMAkVC5U3z5jPqhr "最大磁盘大小")
到这里后，点击完成，然后就创建完虚拟机了。

![创建完成](https://img.lbjheiheihei.xyz/Fq6cLXiHg3OUyx7GiZj0AlalBtOA "创建完成")

#  3 安装 
创建完虚拟机就需要安装，在这个界面选择 Install CentOS 7 ，然后回车
![Install CentOS 7](https://img.lbjheiheihei.xyz/Fty0GL2w1hWJ4C7suIAMI1Hdw_3n "Install CentOS 7")
一行一行的命令行就会出现，快速地闪过
![命令行](https://img.lbjheiheihei.xyz/FhnI9D3cSxPyIu-wXiFP6y-3h9OC "命令行")
在安装镜像加载到内存完成后，就可以看到这个欢迎界面

![欢迎界面](https://img.lbjheiheihei.xyz/Ftni_yFQBiIPxkIgFOVkNVc6uQ6s "欢迎界面")
下划，选择好语言，继续。

![选择语言](https://img.lbjheiheihei.xyz/FtUJTtkxS2cCNvKsKXldd9OzqG9T "选择语言")
然后就会进入这个界面, 一般说来，日期和时间、键盘、语言支持、安装源都不用再看了，直接默认就好。

![默认就好](https://img.lbjheiheihei.xyz/FvS2szEzLdA2NEf69pCXRS__Zxiy "默认就好")

如果想让虚拟机连接到网络，请在*网络和主机名*那打开以太网
![以太网](https://img.lbjheiheihei.xyz/FutcZwTpL6C8unQHB4eVvr-7xXOg "以太网")

软件选择这里非常重要，默认的是最小安装，安装完后是没有桌面的。所以要进去修改一下

**GNOME 桌面环境**可以这样选择，供你参考
![GNOME 桌面环境](https://img.lbjheiheihei.xyz/FuyF9UVIquCWyGdkEsUj8bioll_- "GNOME 桌面环境")
**KDE** 的话，可以这样选择。还是供你参考
![KDE](https://img.lbjheiheihei.xyz/FsaKHT-wJUr59BuKgBKAVvX9Eye9 "KDE")
如果是**带 GUI 的服务器**，你看着来吧，我没试过。
![带 GUI 的服务器](https://img.lbjheiheihei.xyz/FlB4CgyJYPDjkGb8aCipmhukNwCo "带 GUI 的服务器")

这里我选择的是 GNOME 桌面环境，确保所需要的东西都搞定了之后，选择开始安装
![GNOME 桌面环境](https://img.lbjheiheihei.xyz/FoUmsfU5k_CFdOUIUIdgQ97kQsTa "GNOME 桌面环境")
点击开始安装后你会看到这个界面，需要去设置 ROOT 密码，还需要创建一个用户
![创建用户](https://img.lbjheiheihei.xyz/Fq-l66GqqC1ygQLBntk5CCcpuzLI "创建用户")
先把 root 用户的密码搞定，这个一定要记下来，忘记了的话，之后都不用不了 root 权限。

root 账户是每个 Linux 系统的最高管理账户密码，它拥有所有的权限。（包括删库的权限，rm -rf/*)
![ROOT 密码](https://img.lbjheiheihei.xyz/FpVSpv61Am8jemwfYWWfmvVT8cFD "ROOT 密码")

再创建一个用户，这个的密码也要记住。用 root 账户运行系统是非常危险的，可能一个不小心就把系统搞废了，所以要创建一个用户。
![创建一个普通用户](https://img.lbjheiheihei.xyz/FsGjnN2Z6iivT-GYD1zbfVFoDTYZ "创建一个普通用户")

到这里就搞定了，等系统安装完就可以了。要等多久？玄学，不知道，反正挺久的。
看到下面这个就说明安装完了，点击重启。
![重启](https://img.lbjheiheihei.xyz/FnXg5wdn7uEKZOT-Xc3LGMJSVYQK "重启")

#  4  进入
如果重启后看到这个，不用慌，点击一下许可证那里，进去确认一下就好。
![许可证](https://img.lbjheiheihei.xyz/Fmfsevrx4s4NqWfku2icvFY7_oQv "许可证")
然后就变成这样，再点击完成配置。

![初始设置](https://img.lbjheiheihei.xyz/Fv7ZAAZM60FI296lDR5w2KODrgWH "初始设置")
看到这个，说明已经搞定了，输入密码就可以进系统。

![centos](https://img.lbjheiheihei.xyz/Fjzd96Qd49Jpw8xM7B3cfNqM7QkO "centos")
进入之后，需要设置一下，自己会弹出来的，喜欢怎么来就怎么来。

![语言](https://img.lbjheiheihei.xyz/FpxFGTjPnEXgHskYaEnxEqZrHFbT "语言")
![输入](https://img.lbjheiheihei.xyz/FiSpnTMmO8c3TceP2sDrdh7OMvqz "输入")
![隐私](https://img.lbjheiheihei.xyz/FtxMyNt4gJ2GGpLGr0CKa-nfE8Td "隐私")

设置完后，你就会看到这个，开始愉快地使用吧~
![愉快地使用吧](https://img.lbjheiheihei.xyz/FkIWDvZRNOxHl-kR3LXHvQUHbpKO "愉快地使用吧")
