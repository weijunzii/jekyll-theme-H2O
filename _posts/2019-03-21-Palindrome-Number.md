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


## 0   基础练习 回文数
问题描述：
>1221是一个非常特殊的数，它从左边读和从右边读是一样的，编程求所有这样的四位十进制数。

输出格式：
>按从小到大的顺序输出满足条件的四位十进制数。

## 1 做题思路 & 注意事项
所有符合条件的的四位十进制数，把个位、十位、百位、千位求出来，然后只要同时满足个位等于千位，十位等于百位就输出。

所以直接遍历一遍就好，简单粗暴。

## 2 参考代码（Java）
```Java
public class Main {
    public static void main(String[] args) {
        for(int i=1000;i<=9999;i++) {
	        int b = i % 10000/1000;
	        int c = i % 1000/100;
	        int d = i % 100/10;
	        int e = i % 10;
	        if(b==e&&c==d)
	        	System.out.println(i);
	    }
    }
}
```