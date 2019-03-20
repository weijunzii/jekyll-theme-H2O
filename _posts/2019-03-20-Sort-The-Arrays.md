---
layout: post
title: '蓝桥杯基础练习-数列排序'
subtitle: '我真的好菜啊'
date: 2019-03-20
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 数列排序  
问题描述
>给定一个长度为n的数列，将这个数列按从小到大的顺序排列。1<=n<=200

输入格式
>第一行为一个整数n。
>第二行包含n个整数，为待排序的数，每个整数的绝对值小于10000。

输出格式
>输出一行，按从小到大的顺序输出排序后的数列。

样例输入
>5
>8 3 6 4 9

样例输出
>3 4 6 8 9

## 1 做题思路 & 注意事项

先获取第一个数 n，然后根据 n 的值来创建一维数组，接着依次获得这些数，然后排序输出。

## 2 参考代码（Java）

```Java
import java.util.Scanner;
import java.util.Arrays;
public class Main
{
    public static void main(String args[])
    {
		Scanner scan = new Scanner(System.in);
		int n = scan.nextInt();
		int[] a= new int[n];
		for (int i=0;i<n;i++) {
			a[i]= scan.nextInt();
		}
		Arrays.sort(a);
		for (int num : a) {
	        System.out.print(num+" ");
	}
    }
}
```