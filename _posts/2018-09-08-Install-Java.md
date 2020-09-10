---
permalink: /2018/09/08/Install-Java.html
title: 安装和配置 Java 开发环境
subtitle: 真的不难
cover: ""
author: 君子
tags: Java 安装
date: 2018-09-08
layout: post
categories: 技术，编程
---

* content
{:toc}
## 0 前言

下面的在 win7 32 位电脑上安装 Java 的过程，目前最新的是 Java 10，由于 Java 10 Windows x86 的版本，所以只能下载和安装 Java 8.

下载的时候记得要看清楚，选择合适直接电脑的版本进行下载。

## 1 下载

[http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

下载合适的 Java 版本，这里下载的是 Java SE 8u181 的 JDK(Java Development Kit)，点击一下就能跳转到下载节目了。
<img data-src="https://img.lbjheiheihei.xyz/Fje86fUb12koGxABiFTzxhpjurvi" class="lazyload"  alt="Java SE 8u181" title="Java SE 8u181">

需要 Accept License Agreement 才能下载，选择合适的进行下载。
<img data-src="https://img.lbjheiheihei.xyz/FtszfbVLW9xP6tGEL6sBdOcn4qd-" class="lazyload"  alt="Accept License Agreement" title="Accept License Agreement">

下载回来后查看一下有没有下载错，如果没有，双击安装就是了
<img data-src="https://img.lbjheiheihei.xyz/FrpgBTEFQdInkP0oqo9c7Ah7IFtH" class="lazyload"  alt="双击安装" title="双击安装">

打开后是这个样子，点击下一步就是了
<img data-src="https://img.lbjheiheihei.xyz/Fgc-QtEFXbuGN7o0LMaZDbYwJ9F7" class="lazyload"  alt="下一步" title="下一步">

建议是修改一下安装路径，安装路径要记住或者保存。如果懒得记录，建议还是用默认的安装路径。我就懒得改了。
<img data-src="https://img.lbjheiheihei.xyz/FkcVkZ6vT1ZxSe4exrpZGqc9qA3R" class="lazyload"  alt="安装路径" title="安装路径">

修改完之后点击下一步
<img data-src="https://img.lbjheiheihei.xyz/FrkgPslA4WC_9PyKilX4Zv06nzng" class="lazyload"  alt="下一步" title="下一步">

安装完成之后就这样，一个 jdk，一个 jre
<img data-src="https://img.lbjheiheihei.xyz/FjZzyr2ri7vu2mSmhWd9bVK7zqP-" class="lazyload"  alt="一个 jdk，一个 jre" title="一个 jdk，一个 jre">

jdk 文件夹里面是这样的
<img data-src="https://img.lbjheiheihei.xyz/FhJhezDoytqhOQ10gQbKw5VDebDL" class="lazyload"  alt="jdk 文件夹" title="jdk 文件夹">

## 2 配置

是的，安装完之后还需要进行配置。右键 **我的电脑**，然后选择 **属性**
<img data-src="https://img.lbjheiheihei.xyz/FhY5HeDkTzpXB64rBQDVpN055kvq" class="lazyload"  alt="属性" title="属性">

进入后选择 **高级系统设置**
<img data-src="https://img.lbjheiheihei.xyz/Fi2ye7T4YOxpkvDZ2eyjlvP0JIfZ" class="lazyload"  alt="高级系统设置" title="高级系统设置">

接着找到环境变量，再点击一下。进入后选择新建
<img data-src="https://img.lbjheiheihei.xyz/FuVOca-pcxXl6XKtP4nmDFUzvrg2" class="lazyload"  alt="新建" title="新建">

新建的时候，变量名填 `JAVA_HOME`，变量值填安装路径，比如我的安装路径就是 `C:\Program Files\Java\jdk1.8.0_181\` ，然后按确定。
<img data-src="https://img.lbjheiheihei.xyz/Fu3Lg5XBq2KnUv6Czp0j0VS0vNPQ" class="lazyload"  alt="JAVA_HOME" title="JAVA_HOME">

接着就是添加 JAVA 的变量值到 Path 中，在系统变量中找到 Path，然后点击编辑。
<img data-src="https://img.lbjheiheihei.xyz/FtLsGPGr1EVI731nWjg09qtyylhV" class="lazyload"  alt="Path" title="Path">

在后面加上`;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;` ，确定。(虽然我试了只填`;%JAVA_HOME%\bin;`也能用，但是还是推荐加上后面的）

还得新建一个系统变量，变量名填CLASSPATH ，变量值填`.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;`（我学校的教材是多一个 `%JAVA_HOME%\lib\rt.jar;` ，可以考虑在后面加上）

或者填写变量值为`.;%JAVA_HOME%\lib;%JAVA_HOME%\jre\lib`
<img data-src="https://img.lbjheiheihei.xyz/FoOVOICNXvc63BOnbdGVxG97eBET" class="lazyload"  alt="CLASSPATH" title="CLASSPATH">

要测试一下环境配置好了没，按下 win+R，输入 cmd，接着回车。
<img data-src="https://img.lbjheiheihei.xyz/Ft7cJT9NF0Kk0AX9hjhaQnyM5rwe" class="lazyload"  alt="win+R" title="win+R">

分别输入 `java` 、`javac`、`java -version`，如果都有显示类似的文字的话，说明环境的配置完成了。
<img data-src="https://img.lbjheiheihei.xyz/Ft-u71PK2UJ4vTPOBNhynLoGqYAk" class="lazyload"  alt="java -version" title="java -version">

如果是报错，那就说明配置错了。找找看哪里错了，如果还不行，可以再试试。
<img data-src="https://img.lbjheiheihei.xyz/FiHt8GX9YcNLMwy8dC3Xkm7iwiEq" class="lazyload"  alt="javac" title="javac">