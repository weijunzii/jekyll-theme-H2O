---
layout: post
title: '字节跳动在线笔试题--硬币问题'
subtitle: '我好菜啊'
date: 2019-04-28
author: 伪君子
categories:
cover: ''
tags: Java 题解
---

* content
{:toc}


## 0 前言
这是大概一个月前做的字节跳动的在线笔试题，显然，我被否了。

为什么写这个呢，因为最近忙，没时间和精力写别的，只能把存货拿出来更新了。

## 1 题目

Z 国的货币系统包含面值 1 元、4 元、16 元、64 元共计 4 种硬币，以及面值 1024 元的纸币。
现在小 Y 使用 1024 元的纸币购买了一件价值为 N(0<N<=1024) 的商品，请问最少他会收到多少硬币？

输入描述:

>一行，包含一个数N。

输出描述:

>一行，包含一个数，表示最少收到的硬币数。

输入：

>200

输出：

>17

说明：

>花 200，需要找零 824 块，找 12 个 64 元硬币，3 个 16 元硬币，2 个 4 元硬币即可。

备注：对于100%的数据，N(0<N<=1024)

## 2 Java 题解
先获取 N 的值，然后设总数 total 为 1024，1024 减去 N 就是找零 change。

change 除以64 就是 64 元硬币的数量，其余硬币的数量也可以依次算出。

```Java
import java.util.Scanner;
import static java.util.Arrays.sort;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  //整数 n
        int total=1024;  //一共 1024
        int change=total-n;  //找零

        int a=change/64;  //64 元硬币的数量
        int b=(change-(a*64))/16;  //16 元硬币的数量
        int c=(change-(a*64+b*16))/4;  //4 元硬币的数量
        int d=(change-(a*64+b*16+c*4))/1;  //1 元硬币的数量
        System.out.println(a+b+c+d);
    }
}
```