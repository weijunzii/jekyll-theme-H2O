---
layout: post
title: '蓝桥杯历届试题-核桃的数量'
subtitle: '太抠门了'
date: 2019-03-23
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0 历届试题 核桃的数量
问题描述：
>小张是软件项目经理，他带领 3 个开发组。工期紧，今天都在加班呢。为鼓舞士气，小张打算给每个组发一袋核桃（据传言能补脑）。他的要求是：

>1. 各组的核桃数量必须相同

>2. 各组内必须能平分核桃（当然是不能打碎的）

>3. 尽量提供满足1,2条件的最小数量（节约闹革命嘛）

输入格式：
>输入包含三个正整数 a, b, c，表示每个组正在加班的人数，用空格分开（a,b,c<30）

输出格式：
>输出一个正整数，表示每袋核桃的数量。

样例输入 1：
>2 4 5

样例输出 1：
>20

样例输入 2：
>3 1 1

样例输出 2：
>3

## 1 做题思路 & 注意事项
其实就是求最小公倍数

## 2 参考代码（Java）

```Java
import java.util.Scanner;
public class Main

{
	public static int gcd(int a,int b) {  //最大公约数
		if(a==0)
			return b;
		return gcd(b%a,a);
	}
	
	public static int min(int m, int n) {  //最小公倍数=a*b/gcd(a,b)
		return m * n / gcd(m, n);
	}
	
    public static void main(String args[])
    {
    	Scanner sc =new Scanner(System.in);
    	int a=sc.nextInt();
    	int b=sc.nextInt();
    	int c=sc.nextInt();
    	int d=min(a,b);  //先求 a,b 的最小公倍数，赋值给d
    	System.out.println(min(d,c));  //再求 d,c 的最小公倍数，输出
    }
}
```