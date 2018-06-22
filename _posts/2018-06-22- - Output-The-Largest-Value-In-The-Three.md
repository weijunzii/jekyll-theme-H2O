---
layout: post
title: '输出 3 个数中的最大值'
subtitle: '介绍'
date: 2018-06-22
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程 题解

---

* content
{:toc}
### 题目：


输入 a、b、c 三个值，输出其中最大值。

**样例输入**:

10 20 30

**样例输出**:

30

原题链接：[输出 3 个数中的最大值](http://www.dotcpp.com/oj/problem1002.html)
>http://www.dotcpp.com/oj/problem1002.html

![](https://upload-images.jianshu.io/upload_images/2989110-6d5c1f4e34459db5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


**解题思路:**

说实在话，这一题有很多方法可以解决。如果用 C 来实现，一般都是使用 if 来判断，说白了就是用两个 if else。

直接给出部分代码
```C
	if (a > b)  //判断 a，b 哪个大，把大的数赋值给 x1
		x1 = a;
	else 
		x1 = b;
	if (x1 > c) //判断 x1，c 哪个大
		printf("%d", x1);  //如果是 x1 大，输出 x1
	else
		printf("%d", c);  //如果是 c 大，输出 c
```

如果用 C++ 来实现，那就有简单一点的做法, 还是先给出部分代码，这里涉及到 STL 算法，max 这个算法就是用来返回最大值的。

```C++
int x1 = max(a, b);
int x2 = max(x1, c);
cout << x2 << endl;
```

>[http://www.cplusplus.com/reference/algorithm/](http://www.cplusplus.com/reference/algorithm/)

![](https://upload-images.jianshu.io/upload_images/2989110-4dbecce8bd6b0a7a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 参考代码:
先给 C 的代码
```c++

#include <stdio.h>
int main()
{
	int a, b, c,x1,x2;
	scanf("%d%d%d",&a,&b,&c);
	if (a > b)  // 判断 a，b 哪个大，把大的数赋值给 x1
		x1 = a;
	else 
		x1 = b;
	if (x1 > c) // 判断 x1，c 哪个大
		printf("%d", x1);  // 如果是 x1 大，输出 x1
	else
		printf("%d", c);  // 如果是 c 大，输出 c
	return 0;
}
```
再给 C++ 的代码

```C++
#include<iostream>
#include <algorithm>
using namespace std;
int main()
{
	int a, b, c;
	cin >> a >> b >> c;
	int x1 = max(a, b);  // 把 a，b 中大的值赋给 x1
	int x2 = max(x1, c);  // 把 x1，c 中大的值赋给 x2
	cout << x2 << endl;  // 输出最大值
	return 0;
}
```

本地测试结果如下图：
![](https://upload-images.jianshu.io/upload_images/2989110-3ab90d0858079377.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)