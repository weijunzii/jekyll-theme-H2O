---
layout: post
title: '使用github搭建个人博客'
subtitle: '看了不吃亏哦～'
date: 2018-04-02
categories: 技术
cover: 'https://images.unsplash.com/photo-1518172001620-cd0e03e41ff4?ixlib=rb-0.3.5&s=9b2b996cbae53d6b9d97e8d2629cf565&auto=format&fit=crop&w=1955&q=80'
tags: 博客 github
---

* content
{:toc}


# 前言

为什么我要搭建一个个人博客呢？主要是为了方便自己分类一些东西，而且最近在学 *html* 和 *css* ，搭建一个博客来帮助自己理解一下。

文章主要分6个部分，需要懂一点点 HTML 和 CSS ，最需要的是不认输的精神。

# 1  注册 github



没什么好说的，要用 github 的服务，注册一下非常正常。[https://github.com/](https://github.com/)

这一步是最简单的一步了，省略不写

#2  新建一个库  

在 github 那新建一个库

![](https://upload-images.jianshu.io/upload_images/2989110-9cc70efff22ea703.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



或者使用链接的方式，[https://github.com/new

](https://github.com/new)

![建库](https://upload-images.jianshu.io/upload_images/2989110-274c9c0504bc6af2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



点击 Setting 进行设置



![image.png](https://upload-images.jianshu.io/upload_images/2989110-89cb3e1a595b248d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



下拉，找到 GitHub Pages 的 Select theme，我这里是选择过了的，所以不一样。



![52266980694](C:\Users\ASUS\AppData\Local\Temp\1522669806941.png)



进去后选择自己喜欢的主题，然后点击 Select theme 。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-0fe242e9f8963bff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 3  下载客户端

先下载 github 的客户端，然后安装。 [https://desktop.github.com/](https://desktop.github.com/)

登录 github ，然后选择第三个 Clone a repository 



![229102334.jpg](https://upload-images.jianshu.io/upload_images/2989110-ecc5eea2abe72730.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



接着就是把用户名 /用户名.github.io 这个克隆到本地，默认是 C 盘，可以自行修改。

最后找到目录，把.git 这个文件夹留下，别的全删了。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-bfd6ae31d295d606.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 4  选择模板

[http://jekyllthemes.org/](http://jekyllthemes.org/) 这个链接里面全都是 jekyll 主题，找到自己喜欢的做模板就好。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-d180f2491f66a55c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



有在线演示的，可以先看看喜不喜欢，如果喜欢就下载回来



![52267157278](C:\Users\ASUS\AppData\Local\Temp\1522671572782.png)



下载回来是压缩包，解压后全部复制到  /用户名.github.io 这个文件夹。

可以修改通用 `_config.yml` 文件来搭建自己的博客；文章都放在`_posts`文件夹数里，每篇文章的开头都需要设置一些头信息，这个不同的模板是不一样的，需要自行判断，自行修改。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-e5bdb52094df1827.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



修改完后要同步，Summary 自己能看懂就行，随便写写也无所谓。写完后

选择 Commit to master 。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-58166734bb18b0d8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



然后选择同步，Push origin。



![image.png](https://upload-images.jianshu.io/upload_images/2989110-65a024cd2f389a17.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![999545654.gif](https://upload-images.jianshu.io/upload_images/2989110-d45ec3c0ed27990c.gif?imageMogr2/auto-orient/strip)



同步可能会有延迟，要稍微等一下。

# 5  我的搭建

我是自己在 github 那 fork 了一份模板，然后修改的。

[https://github.com/kaeyleo/jekyll-theme-H2O

](https://github.com/kaeyleo/jekyll-theme-H2O)

![image.png](https://upload-images.jianshu.io/upload_images/2989110-0e41573ce047f49d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



然后就是根据它给的说明文档进行修改。

### 修改站点信息

![image.png](https://upload-images.jianshu.io/upload_images/2989110-5f7cd2580f41895e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###修改封面

![image.png](https://upload-images.jianshu.io/upload_images/2989110-5164b31454b2724d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###修改个人介绍

![image.png](https://upload-images.jianshu.io/upload_images/2989110-86ae80125e3e3ed8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

[https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O) 里面有详细的说明，不赘述。

# 6  相关说明

_posts 文件夹里面就是你写的博文，要用 markdown 语法写，不然解析不了。



**相关链接：**

参考的说明[http://cyzus.github.io/2015/06/21/github-build-blog/](http://cyzus.github.io/2015/06/21/github-build-blog/)

Github 的说明[https://pages.github.com/](https://pages.github.com/)

使用的模板[https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O)

