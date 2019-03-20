---
layout: post
title: '蓝桥杯基础练习-十六进制转十进制'
subtitle: '我真的好菜啊'
date: 2019-03-20
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0  基础练习 十六进制转十进制
问题描述
>从键盘输入一个不超过 8 位的正的十六进制数字符串，将它转换为正的十进制数后输出。
>注：十六进制数中的 10~15 分别用大写的英文字母 A、B、C、D、E、F 表示。

样例输入
>FFFF

样例输出
>65535

## 1 做题思路 & 注意事项
直接获取这个十六进制数的字符串，然后调用 API 进行转换。

用 Long 是因为可能会超出 int 的范围。

## 2 参考代码（Java）
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[]){
		Scanner scan = new Scanner(System.in);
		String hex_num = scan.nextLine();
		long dec_num = Long.parseLong(hex_num, 16);
        System.out.println(dec_num);
    }
}
```