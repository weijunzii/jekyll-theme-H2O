---
layout: post
title: 'leetcode 题解~两数之和 ~ C++做法'
subtitle: '丢脸了'
date: 2018-06-20
author: 伪君子
categories: 技术，编程
cover: ''
tags: 编程
---

* content
{:toc}


#  0  前言
最近打算把之前的东西捡起来，毕竟我实在是太水了，如果连这点东西都没有的话，那就真的太说不过去了。

#  1  实现
###  题目
给定一个整数数组和一个目标值，找出数组中和为目标值的**两个**数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。
![](https://upload-images.jianshu.io/upload_images/2989110-aa888246bf44ac6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


目标值就是 target，求出两个下标 i、j，要使得 nums[i] + nums[j] = target，返回下标。
###  代码
```C++
#include<iostream>
#include<vector>
#include<unordered_map>
using namespace std;

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
/*这里定义了两个顺序容器*/
        vector<int> v(2);  //创建一个向量存储容器 int，元素个数为 2
        for(int i = 0; i < nums.size(); i++) {  
/*nums.size()就是 nums 中元素的个数，for 循环，从第一个数开始循环，直到小于nums.size()，也就是 4 就结束循环*/
            for(int j = i + 1; j < nums.size(); j++) {  //和上面差不多，也是 for 循环
                if(nums[i] + nums[j] == target) {  //如果 nums[i] 加 nums[j]等于目标值，那么就进入这个循环
                    v[0] = i;  //把 i 的值付给 v[0]
                    v[1] = j;  //把 j 的值付给 v[1]
                    return v;  //返回 v
                }
            }
        }
    }
};
```

代码来自[https://www.liuchuo.net/archives/1006](https://www.liuchuo.net/archives/1006)，我太水了，只能通过写注释来理解代码。