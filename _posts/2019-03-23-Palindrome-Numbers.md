---
layout: post
title: '蓝桥杯历届试题-回文数字'
subtitle: '回得太多了'
date: 2019-03-23
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0 历届试题 回文数字
问题描述：
>观察数字：12321，123321 都有一个共同的特征，无论从左到右读还是从右向左读，都是相同的。这样的数字叫做：回文数字。

>本题要求你找到一些5位或6位的十进制数字。满足如下要求：
>该数字的各个数位之和等于输入的整数。

输入格式：
>一个正整数 n (10<n<100), 表示要求满足的数位和。

输出格式：
>若干行，每行包含一个满足要求的5位或6位整数。
>数字按从小到大的顺序排列。
>如果没有满足条件的，输出：-1

样例输入：
>44

样例输出：
>99899
>499994
>589985
>598895
>679976
>688886
>697796
>769967
>778877
>787787
>796697
>859958
>868868
>877778
>886688
>895598
>949949
>958859
>967769
>976679
>985589
>994499

样例输入：
>60

样例输出：
>-1

## 1 做题思路 & 注意事项
获取 n 的值，输出符合条件的的五位和六位十进制数，每个位数的数字求出，然后判断是否符合条件，如果是就输出。

五位的需要满足万位等于个位、千位等于十位、每个数加起来等于输入的值；六位类似。

m 是用来判断有没有满足条件的数值，到了最后面判断一下 m 的值是否为 0，如果是，输出 -1.

## 2 参考代码（Java）

```Java
import java.util.Scanner;
public class Main
{
	public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m=0;

        for(int i=10000;i<=99999;i++) {  // 5位的
	        int a = i % 100000/10000;
	        int b = i % 10000/1000;
	        int c = i % 1000/100;
	        int d = i % 100/10;
	        int e = i % 10;
	        if(a==e&&b==d&&(a+b+c+d+e==n)) {
	        	System.out.println(i);
	        	m++;
	        }
	    }

        for(int i=100000;i<=999999;i++) {  // 6位的
	        int a = i % 1000000/100000;
	        int b = i % 100000/10000;
	        int c = i % 10000/1000;
	        int d = i % 1000/100;
	        int e = i % 100/10;
	        int f = i % 10;
	        if(a==f&&b==e&&c==d&&(a+b+c+d+e+f==n)) {
	        	System.out.println(i);
	        	m++;
	        }
	    }
        if(m==0)
        	System.out.println(-1);
    }
}
```
相关文章：
[蓝桥杯基础练习-回文数](https://weijunzii.github.io/2019/03/21/Palindrome-Number.html)
[蓝桥杯基础练习-特殊回文数](https://weijunzii.github.io/2019/03/21/Special-Palindrome-Number.html)