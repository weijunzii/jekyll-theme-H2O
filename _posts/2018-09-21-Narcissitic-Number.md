---
permalink: /2018/09/21/Narcissitic-Number.html
title: 输出所有的水仙花数
subtitle: 喜欢了
cover: ""
author: 君子
tags: Java 题解
date: 2018-09-21
layout: post
categories: 技术，编程
---

* content
{:toc}
## 题目

### 描述

打印所有的"水仙花数"，所谓"水仙花数"是指一个三位数，其各位数字立方和等于该本身。 例如：153 是一个水仙花数，因为$$153=1^3+5^3+3^3$$

原题链接：[http://www.dotcpp.com/blog/4304.html](http://www.dotcpp.com/blog/4304.html)

## 解题思路

因为水仙花数是一个三位数，所以先用一个 for 循环进行遍历，从 100~999 ，然后对数进行计算，分别求出个位、十位、百位的数字，然后进行比对，如果个位、十位和百位的三次方加起来等于该数，则输出那个数。

## 参考代码

### C++ 代码

```c++
#include<iostream>
using namespace std;
int main()
{
  int i, a, b, c;
  for (i = 100; i <= 999; i++)
  {
     a = i % 10;
     b = (i / 10) % 10;
     c = (i / 100) % 10;
     if (i == a*a*a + b*b*b + c*c*c)
         cout << i << " ";
  }
return 0;
}
```



### Java 代码 1

```java
public class Main {

  public static void main(String[] args) {
     int i, a, b, c;
     for (i = 100; i <= 999; i++){
       a = i % 10;//个位
       b = (i / 10) % 10;//十位
       c = (i / 100) % 10;//百位
       if (i == a*a*a + b*b*b + c*c*c){
          System.out.print(i+" ");
     }
   }
  }
}
```

### Java 代码 2

这里是先求出百位数，然后再求十位数，最后是求个位数

```java
public class Main {
	public static void main(String args[])
	{
		int i, a, b, c;
	     for (i = 100; i <= 999; i++){
	    	a=i/100;//百位
	 		b=(i-100*a)/10;//十位
	 		c=(i-100*a-10*b);//个位
	    	if (i == a*a*a + b*b*b + c*c*c){
		          System.out.print(i+" ");
	    	 }
	     }   
	}
}
```