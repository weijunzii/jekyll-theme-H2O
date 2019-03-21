---
layout: post
title: '蓝桥杯基础练习-回文数'
subtitle: '我真的好菜啊'
date: 2019-03-21
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 特殊回文数  
问题描述:
>123321 是一个非常特殊的数，它从左边读和从右边读是一样的。
>输入一个正整数 n， 编程求所有这样的五位和六位十进制数，满足各位数字之和等于 n 。

输入格式:
>输入一行，包含一个正整数 n。

输出格式:
>按从小到大的顺序输出满足条件的整数，每个整数占一行。

样例输入:
>52

样例输出:
>899998
>989989
>998899

数据规模和约定:
>1<=n<=54。

## 1 做题思路 & 注意事项
所有符合条件的的五位和六位十进制数，每个位数的数字求出，然后判断是否符合条件，如果是就输出。

五位的需要满足万位等于个位、千位等于十位、每个数加起来等于输入的值；六位类似。

## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.close();

        for(int i=10000;i<=99999;i++) {
	        int a = i % 100000/10000;  //万位
	        int b = i % 10000/1000;  //千位
	        int c = i % 1000/100;  //百位
	        int d = i % 100/10;  //十位
	        int e = i % 10;  //个位
	        if(a==e&&b==d&&(a+b+c+d+e==n))  //符合条件就输出
	        	System.out.println(i);
	    }

        for(int i=100000;i<=999999;i++) {
	        int a = i % 1000000/100000;  //十万位
	        int b = i % 100000/10000;  //万位
	        int c = i % 10000/1000;  //千位
	        int d = i % 1000/100;  //百位
	        int e = i % 100/10;  //十位
	        int f = i % 10;  //个位
	        if(a==f&&b==e&&c==d&&(a+b+c+d+e+f==n))  //符合条件就输出
	        	System.out.println(i);
	    }
    }
}
```
相关文章：[基础练习 回文数 ](https://weijunzii.github.io/2019/03/21/Palindrome-Number.html)