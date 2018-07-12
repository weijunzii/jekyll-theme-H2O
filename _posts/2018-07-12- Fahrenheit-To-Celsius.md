---
layout: post
title: '华氏温度转摄氏温度~ C++ 做法'
subtitle: '这几天好热啊,想吃西瓜'
date: 2018-07-12
author: 伪君子
categories: 技术，编程
cover: ''
tags: 题解 C++

---

* content
{:toc}
#  题目：
###  描述:
输入一个华氏温度，要求输出摄氏温度。公式为 C=5(F-32)/9，取两位小数。
###  输入：
一个华氏温度，浮点数
###  输出:
摄氏温度，浮点两位小数
###  样例输入:
-40
###  样例输出：
c = -40.00

题目链接：[http://www.dotcpp.com/oj/problem1005.html](http://www.dotcpp.com/oj/problem1005.html)

#  分析：
C++ 中不能像 C 那样直接的用几个字符去控制输出，所以我们要引进 iomanip 这个头文件。

先是在输出后加上 setiosflags(ios::fixed)，它是用来设置格式的，把浮点数的输出格式成定点整数、小数点和小数部分。

setprecision(N) 表示设置浮点数的小数位数为 N-1

setiosflags(ios::fixed) 和 serprecision(N) 两个一起用时就表示保留 N 位小数输出。

设置之后的输出格式作用于后续的输出对象，如果要更改的话，需要用 resetiosflags(ios::fixed) 去重置一下格式。

这里可以查看 [http://www.cplusplus.com/reference/iomanip/](http://www.cplusplus.com/reference/iomanip/)

#  参考代码:
```C++
#include<iostream>
#include<iomanip>   //精度控制头文件
using namespace std;
int main()
{
	float Fahrenheit;  //华式温度
	cin >> Fahrenheit;
	float Celsius;  //摄氏温度
	Celsius = 5 * (Fahrenheit - 32) / 9;  //公式 C=5(F-32)/9
	cout << "c=" << setiosflags(ios::fixed) << setprecision(2) << Celsius << endl;
//setiosflags(ios::fixed) 和 serprecision(N) 两个一起用时就表示保留 N 位小数输出
	return 0;
}
```

本地运行结果如下图
![](https://upload-images.jianshu.io/upload_images/2989110-e961fc7df4c38206.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)