---
layout: post
title: '蓝桥杯基础练习-十进制转十六进制'
subtitle: '我真的好菜啊'
date: 2019-03-21
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 十进制转十六进制  
问题描述：
>十六进制数是在程序设计时经常要使用到的一种整数的表示方式。它有 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F 共 16 个符号，分别表示十进制数的 0 至 15。十六进制的计数方法是满 16 进 1，所以十进制数 16 在十六进制中是 10，而十进制的 17 在十六进制中是 11，以此类推，十进制的 30 在十六进制中是 1E。

>给出一个非负整数，将它表示成十六进制的形式。

输入格式：
>输入包含一个非负整数 a，表示要转换的数。0<=a<=2147483647

输出格式：
>输出这个整数的 16 进制表示

样例输入：
>30

样例输出：
>1E

## 1 做题思路 & 注意事项
直接获取这个十进制数，然后使用 Integer.toHexString(i) 进行转换。

toUpperCase() 是因为要大写。

## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[]){
		Scanner sc = new Scanner(System.in);
		int i = sc.nextInt();
        System.out.println(Integer.toHexString(i).toUpperCase());
    }
}
```

相关文章：[基础练习 十六进制转十进制](https://weijunzii.github.io/2019/03/20/Hexadecimal-To-Decimal.html)