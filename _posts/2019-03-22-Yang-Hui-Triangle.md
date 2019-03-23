---
layout: post
title: '蓝桥杯基础练习-杨辉三角形'
subtitle: '简单的杨辉三角'
date: 2019-03-22
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 杨辉三角形 
问题描述
>杨辉三角形又称Pascal三角形，它的第i+1行是(a+b)i的展开式的系数。它的一个重要性质是：三角形中的每个数字等于它两肩上的数字相加。

>下面给出了杨辉三角形的前4行：
>   1　
>  1 1　　
> 1 2 1　　
>1 3 3 1


>给出 n，输出它的前 n 行。

输入格式:
>输入包含一个数 n。

输出格式:
>输出杨辉三角形的前 n 行。每一行从这一行的第一个数开始依次输出，中间使用一个空格分隔。请不要在前面输出多余的空格。

样例输入:
>4

样例输出:
>1
>1 1
>1 2 1
>1 3 3 1

数据规模与约定:
>1 <= n <= 34。

## 1 做题思路 & 注意事项
最好是自己先画个图理解一下，其实不难的，创建二维数组，然后一一赋值，最后输出就好。

## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  //整数 n
        int[][] a = new int[n][n]; //创建二维数组

        for(int i=0;i<n;i++) {  // i 是行
        	for(int j=0; j<=i; j++){  // j 是列
        		if(i==j||j==0) {  //每一行的第一个和最后一个是 1
        			a[i][j]=1;
        		}
        		else {  //其余的是上面两个数相加
        			a[i][j]=a[i-1][j-1]+a[i-1][j];
        		}
        	}
        }

        for(int i=0; i<n; i++){
			for(int j=0; j<=i; j++){  //输出
				System.out.print(a[i][j] + " ");
			}
			System.out.println();  //换行
		}
    }
}
```