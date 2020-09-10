---
permalink: /2018/09/10/Install-Eclipse.html
title: 安装和配置 Eclipse
subtitle: 不难的~
cover: ""
author: 君子
tags: Java 安装
date: 2018-09-10
layout: post
categories: 技术，编程
---

* content
{:toc}
## 0 前言

之前安装了 [Java](https://weijunzii.github.io/2018/09/08/Install-Java.html) 并且配置好了 Java 的环境变量，现在来搞一下开发环境，下面就是下载安装和配置 Eclipse 的教程。

## 1 下载和安装

[https://www.eclipse.org/downloads/packages/installer](https://www.eclipse.org/downloads/packages/installer)

选择合适的进行下载，链接下面也有安装的教程，虽然只有英文，但是也很贴心了。
<img data-src="https://img.lbjheiheihei.xyz/FvtSgqO4Dc1qGPkAafeO2NVXCSmJ" class="lazyload"  alt="Eclipse" title="Eclipse">

因为安装的是 Java，所以选择 `Eclipse IDE for Java Developers`
<img data-src="https://img.lbjheiheihei.xyz/FhLj5-2khqCRwhokobQnzG-BM0X-" class="lazyload"  alt="Eclipse IDE for Java Developers" title="Eclipse IDE for Java Developers">

可以更改安装路径，点击安装后需要同意一个东西
<img data-src="https://img.lbjheiheihei.xyz/Ft6nVYUkGrs9SjQu02xmDiZqFZgM" class="lazyload"  alt="安装路径" title="安装路径">

安装完直接点 LAUNCH 就好
<img data-src="https://img.lbjheiheihei.xyz/Ft7N6H40v03ykK26txAkB4_lR9WT" class="lazyload"  alt="LAUNCH" title="LAUNCH">

## 2 打开和使用

Workspace 直译过来就是工作空间，用来保存设置的，可以更改。可以把圈住的这个勾选了，不然每一次打开都会提醒一次
<img data-src="https://img.lbjheiheihei.xyz/FroLDX75CDhiegk8_qp7Os3zuDEJ" class="lazyload"  alt="Workspace" title="Workspace">

打开来之后先关掉欢迎页面，再新建一个 Java 项目
<img data-src="https://img.lbjheiheihei.xyz/Fteo85VsAdvGaQcS2-DctOZD4BqL" class="lazyload"  alt="新建一个 Java 项目" title="新建一个 Java 项目">

项目名选择一个好记住的，开头字母要大写，勾选 Use a project specific JRE，这一步很重要，不然下次会有点麻烦。
<img data-src="https://img.lbjheiheihei.xyz/FmjXCdEpGa3msYeqttpweMrDU_QT" class="lazyload"  alt="Use a project specific JRE" title="Use a project specific JRE">

新建一个的 test 包，在 src 那点击鼠标右键，New，然后选择 Package
<img data-src="https://img.lbjheiheihei.xyz/FoSb6YD2TBSdVEGny38omkS2cd3r" class="lazyload"  alt="Package" title="Package">

名字嘛，看缘分命名了
<img data-src="https://img.lbjheiheihei.xyz/Fvp0IAf7UQ9kyT4-ir1T-yLiUp2n" class="lazyload"  alt="命名" title="命名">

在新建的 test 包那点击一下右键，然后 New 一个 Class。
<img data-src="https://img.lbjheiheihei.xyz/Fnc5BnB9CjNI-tZyx_2heig2ZAhs" class="lazyload"  alt="New 一个 Class" title="New 一个 Class">

Class 的名字也就是类的名字首字母要大写。
<img data-src="https://img.lbjheiheihei.xyz/FjoaCGG-sIgJbZI1kkzjcr4FRBNV" class="lazyload"  alt="Class 的名字" title="Class 的名字">

全部完成之后就是下图这样，当然，我这里的命名都是皮一下的，正式项目千万不要这样来命名。
<img data-src="https://img.lbjheiheihei.xyz/FjWebyp06IhZgb84uiyQVsUqlTG7" class="lazyload"  alt="全部完成之后" title="全部完成之后">

写完代码后，点击图中标识的那个按键就可以运行了。
<img data-src="https://img.lbjheiheihei.xyz/FgrXkLCe9UZfXuKrG3AOfs7REe-R" class="lazyload"  alt="运行" title="运行">

## 3 修改主题和字体

点击 Window ，接着点击 Preferences
<img data-src="https://img.lbjheiheihei.xyz/FlW57p_vWilPp8M-oGGmab4js2jh" class="lazyload"  alt="Preferences" title="Preferences">

找到 General，接着找到 Appearance，接着选择自己喜欢的主题样式，点击 Apply 就是应用
<img data-src="https://img.lbjheiheihei.xyz/FpFueB2zpSVHTq0V7yggufLGxZYO" class="lazyload"  alt="Appearance" title="Appearance">

把 Appearance 展开就能看见 Colors and Fonts，进入后双击 Java，打开后找到 Java Editor Text Font，接着按 Edit Default。
<img data-src="https://img.lbjheiheihei.xyz/FpNxPwno2XPOj8r339Leebv8EnDQ" class="lazyload"  alt="Edit Default" title="Edit Default">

接着就是修改一下字体和字体大小，修改完后确定
<img data-src="https://img.lbjheiheihei.xyz/FoVNDoMR3CFg21Lh4BqjocdaNXqE" class="lazyload"  alt="字体和字体大小" title="字体和字体大小">

确定主题和字体都合适之后，点击 Apply and Close 退出就好了。
<img data-src="https://img.lbjheiheihei.xyz/FnwJHRBxERvwdDKZWa9b0ll-I_ul" class="lazyload"  alt="合适" title="合适">