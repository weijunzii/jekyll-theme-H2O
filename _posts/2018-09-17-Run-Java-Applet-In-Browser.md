---
permalink: /2018/09/17/Run-Java-Applet-In-Browser.html
title: 在浏览器运行 Java Applet 小应用程序
subtitle: 哭了
cover: ""
author: 君子
tags: Java
date: 2018-09-17
layout: post
categories: 技术，编程
---

* content
{:toc}
## 0 前言

老师布置了一个作业，让我们编写一个 Java Applet 程序，使之能在浏览器显示信息。

一开始我想："那还不简简单单吗？照着书来就可以了”。事实证明，并不。

电脑是 win7，[Java 环境](https://weijunzii.github.io/2018/09/08/Install-Java.html)，用的编译器是 [Eclipse](https://weijunzii.github.io/2018/09/10/Install-Eclipse.html)。

## 1 代码

### 1.1 applet 程序代码

首先给出 applet 程序的代码，在 Eclipse 中肯定能运行的。这里省略 package，请自行添加。

```java
import java.awt.Graphics;
import java.applet.Applet;

public class MyJavaApplet extends Applet{
   public void paint (Graphics g)
   {
      g.drawString ("伪君子发来贺电~", 25, 50);
   }
}
```

保存好，能运行出结果就说明没问题，也不太可能会出现问题。
![运行结果](http://img.lbjheiheihei.xyz/Fh3QNmXcK7LPFJstPPSNCaHYcNmz "运行出结果")

接着就是按下 win+R，输入 cmd，接着回车。

进入之后输入 cd，然后空格 ，接着就是你的 applet 程序所在的路径，回车

再输入盘符，C： 或者是 D:, 回车就进入该路径了，如下图。

![盘符](https://img.lbjheiheihei.xyz/FkyphSOdlAf_EVZ9gr39nhRFn_ZE "盘符")

然后是输入命令，javac 程序名.java，完成后会在该路径下看见 程序名.class 这样的文件
![javac 程序名.java](https://img.lbjheiheihei.xyz/FnliBsmrC-S95t-VjMJmy4I6LY0V "javac 程序名.java")

### 1.2 html 代码

applet 标签后面的 codebase 是代码路径，code 是编译后的 class 文件的名字。

```html
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>Java Applet</title>
</head>
	<applet codebase="F:\" code="MyJavaApplet.class" height="200" width="300">
	</applet>
	<h1>哈哈哈</h1>
<body>
</body>
</html>
```

保存好文件，命名随意，.html 文件要放在和 .class 文件同一个目录下。

我们在 cmd 内输入 appletviewer 文件名.html，如果能看到结果，那说明是没出错。
![appletviewer 文件名.html](https://img.lbjheiheihei.xyz/Fsc2PJyHpHc5fORcSMBfGlUNCAGZ "appletviewer 文件名.html")

## 2 麻烦

这样是不能在浏览器显示信息的，把 html 文件拉进浏览器打开，只能看见 “哈哈哈” 3个字。

进入控制面版，找到 Java，点击进入
![Java](https://img.lbjheiheihei.xyz/Fgq8SM56kBjYe4uQug5ytZQAGdRO "Java")
接着找到安全，点击编辑站点列表

![编辑站点列表](https://img.lbjheiheihei.xyz/FnXfeWRUvcp4aA2fyOSYCWQwssRQ "编辑站点列表")

点击添加，我这里是`file:///F:/javaapplet.html`,把后面的路径和代码改成你本地的就好，然后回车。

`file:///`这个不能丢，一定要注意。
![file:/// 不能丢](https://img.lbjheiheihei.xyz/FrSPgsluw1Yds8NZ0k4Ma9WQZvvh "file:/// 不能丢")

看到警告是很正常的，继续就好，接着一路确定
![看到警告](https://img.lbjheiheihei.xyz/Ft6FcUDQe0L5eFUkwrBHUheL-icj "看到警告")

打开 ie，把 html 文件拉进去，如果浏览器能成功显示 **伪君子发来贺电~**，说明搞定了。

![成功显示](https://img.lbjheiheihei.xyz/Fn9HtnQhZcwgGOQl0471pYbJVMo6 "成功显示")

看到下图这样，说明不行。
![不行](https://img.lbjheiheihei.xyz/FqbiF5Z0enBX38erGs0Beqs3-isw "不行")

如果不行，点击工具，选择 Internet 选项
![Internet 选项](https://img.lbjheiheihei.xyz/Fm7-2lM1nUil4REbFCDbuAtS5FZ4 "Internet 选项")

找到安全，选择自定义级别。
![自定义级别](https://img.lbjheiheihei.xyz/FjTJLTJsmToU5kAwf_eKmgk_XzAo "自定义级别")

下拉，在脚本内找到 Java 小程序脚本，选择启用，一路确定下去。
![Java 小程序脚本](https://img.lbjheiheihei.xyz/FonnsafKd0MSGyLJKVMMlTpqnP68 "Java 小程序脚本")

这时肯定能看到 **伪君子发来贺电~**，如果还不行，那就是其中某一步出现问题了，快去找找哪出错了。
![成功显示](https://img.lbjheiheihei.xyz/Fn9HtnQhZcwgGOQl0471pYbJVMo6 "成功显示")

## 3 相关说明

为什么说那么困难呢，因为教材不行

Applet 程序代码
![Applet 程序代码](https://img.lbjheiheihei.xyz/FrvRUbnh6CCr9YmhqJ3mtgSRRGJD "Applet 程序代码")

html 代码
![html 代码](https://img.lbjheiheihei.xyz/FqF8SgWIcIl59CvZkh0JE4bhdyEl "html 代码")

至于我后面遇到的麻烦，里面一个都能没有说！！我还是找资料后才发现要用 ie 浏览器，还得弄那么多东西。

好在，Java Applet 程序也没有什么人用了，不然，谁会开 ie 浏览器呢。