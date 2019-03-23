---
layout: post
title: '蓝桥杯基础练习-数列特征'
subtitle: '我是真的菜'
date: 2019-03-23
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 数列特征   
问题描述:
>给出 n 个数，找出这 n 个数的最大值，最小值，和。

输入格式:
>第一行为整数 n，表示数的个数。

>第二行有 n 个数，为给定的 n 个数，每个数的绝对值都小于 10000。

输出格式:
>输出三行，每行一个整数。第一行表示这些数中的最大值，第二行表示这些数中的最小值，第三行表示这些数的和。

样例输入:
>5
>1 3 -2 4 5

样例输出:
>5
>-2
>11

数据规模与约定:
>1 <= n <= 10000。

## 1 做题思路 & 注意事项
注意了，n 可以是1，如果是这种情况，最大值、最小值、和都是输入的那个数。


## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int max=0,min=0,sum=0;  //一开始都赋值为 0

        int n = sc.nextInt();  //整数 n
        int[] a = new int[n]; //数组

        for(int i=0;i<n;i++) {  // i 是行
        	a[i]=sc.nextInt();
        	if(i==0) { //如果 n=1，则最大最小都是那个值
        		min=a[i];
        		max=a[i];
        	}
        	if(a[i]>max)  //如果 a[i] 大于 max，那么把 a[i] 的值赋给max
        		max=a[i];
        	if(a[i]<min)  //如果 a[i] 小于 min，那么把 a[i] 的值赋给min
        		min=a[i];
        	sum+=a[i];
        }

        System.out.println(max);
        System.out.println(min);
        System.out.println(sum);
    }
}
```