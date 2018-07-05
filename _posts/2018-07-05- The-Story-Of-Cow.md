---
layout: post
title: '蓝桥杯题解 ~ 母牛的故事 （C++做法）'
subtitle: '别人都去旅游， 我在研究母牛'
date: 2018-07-05
author: 伪君子
categories: 技术，编程
cover: ''
tags: 蓝桥杯 题解 C++

---

* content
{:toc}
#  题目：


##  描述：

有一头母牛，它每年年初生一头小母牛。每头小母牛从第四个年头开始，每年年初也生一头小母牛。请编程实现在第 n 年的时候，共有多少头母牛？



##  输入：

输入数据由多个测试实例组成，每个测试实例占一行，包括一个整数 n(0<n<55)，n 的含义如题目中描述。

n=0 表示输入数据的结束，不做处理。



##  输出：

对于每个测试实例，输出在第 n年的时候母牛的数量。

每个输出占一行。

题目链接：[http://www.dotcpp.com/oj/problem1004.html](http://www.dotcpp.com/oj/problem1004.html)
![](https://upload-images.jianshu.io/upload_images/2989110-bc1ebbb9c3a2acd7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  分析：



我们先列出一个表格，把每一年对应的母牛数量写出来。

| 第 n 年：  | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    |
| ---------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| f[n] 头牛: | 1    | 2    | 3    | 4    | 6    | 9    | 13   | 19   |



先看第 4 年，对应有 4 头母牛，4 = 3+1；
再看第 5 年，对应有 6 头母牛，6 = 4+2；
最后看第 6 年，对应有 9 头母牛，9 = 6+3；



没错，是有规律的，该年母牛的数量就是一年前的数量再加上三年前的数量，

用公式表示就是 f[n] = f[n-1] + f[n-3]



#  参考代码:

##  迭代法：

先给出用迭代法的代码，因为它长
```c++
#include<iostream>
using namespace std;
int main()
{
    int n, i;
    int f1, f2, f3, fn;
    while (cin >> n && n != 0)  //输入 n 的值，且 n 不等于0，则进入，否则退出
    {
        f1 = 1;
        f2 = 2;
        f3 = 3;
        if (n == 1)
            cout << f1 << endl;
        else if (n == 2)
            cout << f2 << endl;
        else if (n == 3)
            cout << f3 << endl;
        else
        {
            for (i = 4; i <= n; i++)
            {
                fn = f3 + f1;  
                //把该年迭代为一年前,一年前迭代为两年前，依次类推
                f1 = f2;  //f1代表 3 年前
                f2 = f3;  //f2代表 2 年前
                f3 = fn;  //f3代表 1 年前
            }
            cout << fn << endl;  //fn
        }
    }
    return 0;
}
```
##  数组：

最后给出用数组的，用数组相对来说会好一点，因为迭代一次，然后就可以输出了。上面那个代码每输入一个数都需要重新迭代，数量大且多的话，花费的时间会比较多。
```c++
#include<iostream>
using namespace std;
int main()
{
    int n, i;
    int f[55] = { 0,1,2,3 };  //f[0]=0,f[1]=1,f[2]=2,f[3]=3
    for (i = 4; i < 55; i++)
        f[i] = f[i - 1] + f[i - 3];
    while (cin >> n && n != 0)  //输入 n 的值，且 n 不等于0，则进入，否则退出
    {
        cout << f[n] << endl;
    }
    return 0;
}
```
