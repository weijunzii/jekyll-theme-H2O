---
layout: post
title: '蓝桥杯基础练习-特殊的数字'
subtitle: '水仙花数'
date: 2019-03-22
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 特殊的数字  
问题描述：
>153 是一个非常特殊的数，它等于它的每位数字的立方和，即 ```153=1*1*1+5*5*5+3*3*3```。编程求所有满足这种条件的三位十进制数。

输出格式：
>按从小到大的顺序输出满足条件的三位十进制数，每个数占一行。

## 1 做题思路 & 注意事项
其实就是水仙花数,从 100 遍历到 999，如果符合条件就输出。

## 2 参考代码（Java）
```Java
public class Main {
    public static void main(String[] args) {

        for(int i=100;i<=999;i++) {
	        int a = i % 1000/100;
	        int b = i % 100/10;
	        int c = i % 10;

	        if(Math.pow(a,3)+Math.pow(b,3)+Math.pow(c,3)==i)
	        	System.out.println(i);
	    }
    }
}
```