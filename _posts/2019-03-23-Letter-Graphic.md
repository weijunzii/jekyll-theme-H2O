---
layout: post
title: '蓝桥杯基础练习-字母图形'
subtitle: '题目不太合理'
date: 2019-03-23
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0 基础练习 字母图形    
问题描述:
>利用字母可以组成一些美丽的图形，下面给出了一个例子：

>ABCDEFG
>BABCDEF
>CBABCDE
>DCBABCD
>EDCBABC

>这是一个5行7列的图形，请找出这个图形的规律，并输出一个n行m列的图形。

输入格式:
>输入一行，包含两个整数 n 和 m，分别表示你要输出的图形的行数的列数。

输出格式:
>输出 n 行，每个 m 个字符，为你的图形。

样例输入:
>5 7

样例输出:
>ABCDEFG
>BABCDEF
>CBABCDE
>DCBABCD
>EDCBABC

数据规模与约定:
>1 <= n, m <= 26。

## 1 做题思路 & 注意事项
一开始的思路是获取 n 和 m 的值，然后根据这两个的值来创建二维数组，提交了之后发现不对，试了好多次，发现有人说数组直接定死 26 就可以通过了，试了一下，正解。（题目不太合理）

其实是有规律的，只看 A 的位置，都是在　[0][0]，[1][1]，[2][2] 这样的位置，往前往后都是 +1。所以先把 A 的位置定下来，然后往前的依次 +1，往后的也依次 +1。

处理好之后输出。

## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  //整数 n,行
        int m = sc.nextInt();  //整数 m,列
        char[][] a = new char[26][26]; //char 型二维数组

        for(int i=0;i<n;i++) {
        	char str='A';
        	for(int j=i;j<m;j++) {  //往后
        		a[i][j]=str++;
        	}
        	str='A';
        	for(int j=i-1;j>=0;j--) {  //往前
        		a[i][j] = ++str;
        	}
        }

        for(int i=0;i<n;i++) {
        	for(int j=0;j<m;j++) {
        		System.out.print(a[i][j]);  //输出
        	}
        	System.out.println();  //换行
        }
    }
}
```