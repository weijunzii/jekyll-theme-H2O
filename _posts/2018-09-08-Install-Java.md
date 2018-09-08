---
layout: post
title: '安装和配置 Java 开发环境'
subtitle: ''
date: 2018-09-08
author: 伪君子
categories: 技术，编程
cover: ''
tags: Java 安装

---

* content
{:toc}
## 0 前言

下面的在 win7 32 位电脑上安装 Java 的过程，目前最新的是 Java 10，由于 Java 10 Windows x86 的版本，所以只能下载和安装 Java 8.

下载的时候记得要看清楚，选择合适直接电脑的版本进行下载。

## 1 下载

[http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

下载合适的 Java 版本，这里下载的是 Java SE 8u181 的 JDK(Java Development Kit)，点击一下就能跳转到下载节目了。
![](https://upload-images.jianshu.io/upload_images/2989110-6d095ef8a703079c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

需要 Accept License Agreement 才能下载，选择合适的进行下载。
![](https://upload-images.jianshu.io/upload_images/2989110-ec30ae1403785386.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

下载回来后查看一下有没有下载错，如果没有，双击安装就是了
![](https://upload-images.jianshu.io/upload_images/2989110-c7a6dafaa895a77e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
打开后是这个样子，点击下一步就是了
![](https://upload-images.jianshu.io/upload_images/2989110-2a59b18c1fc29295.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
建议是修改一下安装路径，安装路径要记住或者保存。如果懒得记录，建议还是用默认的安装路径。我就懒得改了。
![](https://upload-images.jianshu.io/upload_images/2989110-3ef0f372eb4c0343.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
修改完之后点击下一步
![](https://upload-images.jianshu.io/upload_images/2989110-d699fbf59ab4cc79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](https://upload-images.jianshu.io/upload_images/2989110-6111ebc02ed0ca12.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
安装完成之后就这样，一个 jdk，一个 jre
![](https://upload-images.jianshu.io/upload_images/2989110-e27acbca4443d1e7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
jdk 文件夹里面是这样的
![](https://upload-images.jianshu.io/upload_images/2989110-e60fa1345fd680dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2 配置

是的，安装完之后还需要进行配置。右键 **我的电脑**，然后选择 **属性**
![](https://upload-images.jianshu.io/upload_images/2989110-3cd34158dfc489af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入后选择 **高级系统设置**
![](https://upload-images.jianshu.io/upload_images/2989110-66744f3dbf4997a6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着找到环境变量，再点击一下。进入后选择新建
![](https://upload-images.jianshu.io/upload_images/2989110-516e6fd9177ba59f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
新建的时候，变量名填 `JAVA_HOME`，变量值填安装路径，比如我的安装路径就是 `C:\Program Files\Java\jdk1.8.0_181\` ，然后按确定。
![](https://upload-images.jianshu.io/upload_images/2989110-7bc39c66089464df.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接着就是添加 JAVA 的变量值到 Path 中，在系统变量中找到 Path，然后点击编辑。
![](https://upload-images.jianshu.io/upload_images/2989110-cd007dcde6c6d9d6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在后面加上`;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;` ，确定。(虽然我试了只填`;%JAVA_HOME%\bin;`也能用，但是还是推荐加上后面的）
![](https://upload-images.jianshu.io/upload_images/2989110-4a7154c158c5e3f1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

还得新建一个系统变量，变量名填CLASSPATH ，变量值填`.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;`（我学校的教材是多一个 `%JAVA_HOME%\lib\rt.jar;` ，可以考虑在后面加上）

或者填写变量值为`.;%JAVA_HOME%\lib;%JAVA_HOME%\jre\lib`
![](https://upload-images.jianshu.io/upload_images/2989110-1f3af398060de4a3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
要测试一下环境配置好了没，按下 win+R，输入 cmd，接着回车。
![](https://upload-images.jianshu.io/upload_images/2989110-993820d1ac43d57b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
分别输入 `java` 、`javac`、`java -version`，如果都有显示类似的文字的话，说明环境的配置完成了。
![](https://upload-images.jianshu.io/upload_images/2989110-e151a25277be04b2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果是报错，那就说明配置错了。找找看哪里错了，如果还不行，可以留言。
![](https://upload-images.jianshu.io/upload_images/2989110-cd7b9dfed2414312.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)