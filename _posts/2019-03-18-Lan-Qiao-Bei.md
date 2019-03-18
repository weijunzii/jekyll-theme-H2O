---
layout: post
title: '蓝桥杯入门训练题'
subtitle: '我好菜啊'
date: 2019-03-18
author: 伪君子
categories:
cover: ''
tags: Java 题解 蓝桥杯
---

* content
{:toc}


## 0 前言
蓝桥杯入门训练题，别问，再问我就哭了。

## 1 入门训练 A+B问题
问题描述:
>输入 A、B，输出 A+B。

输入格式:
>输入的第一行包括两个整数，由空格分隔，分别表示 A、B。

输出格式:
>输出一行，包括一个整数，表示 A+B 的值。

样例输入:
>12 45

样例输出:
>57

数据规模与约定:
>-10000 <= A, B <= 10000。

### 解题思路：
获取两个数的值，加起来，然后输出。
### 参考代码（Java）：
```Java
import java.util.*;
public class Main
{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        Integer a = sc.nextInt();
        Integer b = sc.nextInt();
        System.out.println(a + b);
    }
}
```
## 2 入门训练 序列求和  
问题描述:
>求 1+2+3+...+n 的值。

输入格式:
>输入包括一个整数n。

输出格式:
>输出一行，包括一个整数，表示 1+2+3+...+n 的值。

样例输入:
>4

样例输出:
>10

样例输入:
>100

样例输出:
>5050

数据规模与约定:
>1 <= n <= 1,000,000,000。

### 解题思路：
直接使用 (1+n)*n/2，这个公式就可以了。但是要注意的是，int 型最大值是 2^31 - 1，输入这里是可以的，但是输出就不行了，很可能会超过这个值。

所以直接用 Long，2^63 -1，肯定足够的。
### 参考代码（Java）：
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        Long n = sc.nextLong(); // int 不够用，所以用 long
        System.out.println((1+n)*n/2);
    }
}
```
## 3 入门训练 圆的面积
问题描述：
>给定圆的半径 r，求圆的面积。

输入格式：
>输入包含一个整数 r，表示圆的半径。

输出格式：
>输出一行，包含一个实数，四舍五入保留小数点后 7 位，表示圆的面积。

样例输入：
>4

样例输出：
>50.2654825

数据规模与约定：
>1 <= r <= 10000。

提示：
>本题对精度要求较高，请注意π的值应该取较精确的值。你可以使用常量来表示 π，比如 PI=3.14159265358979323，也可以使用数学公式来求 π，比如 PI=atan(1.0)*4。

### 解题思路：
获得值，计算，然后格式化输出。

这里 import java.text.DecimalFormat; 因为需要格式化输出，"#.0000000" 表示保留小数点后 7 位，有就显示，没有就补零.

"00000" 是输出 5 位，不足就补零。
### 参考代码（Java）：
```Java
import java.util.Scanner;
import java.text.DecimalFormat;
public class Main
{
    public static void main(String args[])
    {
    	double pi=3.14159265358979323;  //直接使用常量
        Scanner sc = new Scanner(System.in);
        Integer r = sc.nextInt();
        double s = pi*r*r;
        DecimalFormat df=new DecimalFormat("#.0000000");  //格式化，保留小数点后 7 位
        System.out.println(df.format(s));  //输出
    }
}
```

## 4 入门训练 Fibonacci数列
问题描述：
>Fibonacci 数列的递推公式为：Fn=Fn-1+Fn-2，其中 F1=F2=1。

>当 n 比较大时，Fn 也非常大，现在我们想知道，Fn 除以 10007 的余数是多少。

输入格式：
>输入包含一个整数n。

输出格式：
>输出一行，包含一个整数，表示 Fn 除以 10007 的余数。

样例输入：
>10

样例输出：
>55

样例输入：
>22

样例输出：
>7704

数据规模与约定：
>1 <= n <= 1,000,000。

###解题思路：
Fn=Fn-1+Fn-2，其中 F1=F2=1,直接套这个公式，直接计算除以 10007 的余数。

这里要注意的是，1 也可以是输入。

### 参考代码 1 （Java）：
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  //获得 n
        int[]f = new int[n];   //用数组记录第 n 项的余数

        if (n == 1 || n == 2) {
             f[n - 1] = 1;
        }
        else {
            for (int i = 2;i < n;i++) {
                f[0] = 1;
                f[1] = 1;
                f[i] =(f[i - 1] + f[i - 2]) % 10007;
             }
        }

        System.out.println(f[n - 1]);
    }
}
```
### 参考代码 2 （Java）：
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[])
    {

		int[] f= new int[1000001];
		f[1] = f[2] = 1;

		for (int i = 3; i <= 1000000; i++) {
			f[i] = (f[i-1] + f[i-2]) % 10007;
		}
		
		System.out.println(f[sc.nextInt()]);
    }
}
```

### 参考代码 3 （Java）：
```Java
import java.util.Scanner;
public class Main
{
    public static void main(String args[])
    {
    	Scanner sc = new Scanner(System.in);
    	int n = sc.nextInt();
		int[] f= new int[n+1];
		if(n==1) {
			f[1]=1;
		}
		else {
			f[1] = f[2] = 1;
			for (int i = 3; i <= n; i++) {
				f[i] = (f[i-1] + f[i-2]) % 10007;
			}
		}
		
		System.out.println(f[n]);
    }
}
```