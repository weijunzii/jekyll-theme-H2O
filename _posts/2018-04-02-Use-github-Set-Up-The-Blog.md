---
permalink: 2018/04/02/Use-github-Set-Up-The-Blog.html
title: 使用 GitHub 搭建个人博客
subtitle: 紧张刺激又有趣
cover: https://img.lbjheiheihei.xyz/lrszjb1TWjv-O5Zykf12AQeKN2rs
author: 君子
tags: 博客 GitHub
date: 2018-04-02T00:00:00.000Z
layout: post
---

* content
{:toc}


# 前言

为什么我要搭建一个个人博客呢？主要是为了方便自己分类一些东西，而且最近在学 *html* 和 *css* ，搭建一个博客来帮助自己理解一下。

文章主要分6个部分，需要懂一点点 HTML 和 CSS ，最需要的是不认输的精神。

# 1  注册 GitHub



没什么好说的，要用 GitHub 的服务，注册一下非常正常。[https://github.com/](https://github.com/)

这一步是最简单的一步了，省略不写。

# 2  新建一个库

在 GitHub 那新建一个库


![建库](https://img.lbjheiheihei.xyz/FgzEeyC_rY9VyPFRD3vJwp5NYolp "建库")


或者使用链接的方式，[https://github.com/new](https://github.com/new)
![建库](https://img.lbjheiheihei.xyz/FpR7yYNB1uHbhKNeG79riLr6nx5W "建库")



点击 Setting 进行设置



![设置](https://img.lbjheiheihei.xyz/Fmwd4aHkR8Yol7sV1T7RGszF10L- "设置")




下拉，找到 GitHub Pages 的 Change theme，我这里是选择过了的，所以不一样。


![Change theme](https://img.lbjheiheihei.xyz/Flq2u8Roncye_7Rm-wdxbdrTo5I4 "Change theme")



进去后选择自己喜欢的主题，然后点击 Select theme 。

![Select theme](https://img.lbjheiheihei.xyz/Fh2jFjRYHrWkUMbMNk6HOShnTbRE "Select theme")





# 3  下载客户端

先下载 GitHub 的客户端，然后安装。 [https://desktop.github.com/](https://desktop.github.com/)

登录 GitHub ，然后选择第三个 Clone a repository 

![Clone a repository](https://img.lbjheiheihei.xyz/Fvs72LsndS2t9ROGBtLAVtL96I75 "Clone a repository")




接着就是把用户名 /用户名.github.io 这个克隆到本地，默认是 C 盘，可以自行修改。

最后找到目录，把.git 这个文件夹留下，别的全删了。



![.git文件夹](https://img.lbjheiheihei.xyz/FoJmpyNx3CL1pQc9NiI6b3TglC55 ".git文件夹")



# 4  选择模板

[http://jekyllthemes.org/](http://jekyllthemes.org/) 这个链接里面全都是 jekyll 主题，找到自己喜欢的做模板就好。



![jekyll 模板](https://img.lbjheiheihei.xyz/Fnl9fibSTVhSHQUE6j99LeG19yWa "jekyll 模板")



有在线演示的，可以先看看喜不喜欢，如果喜欢就下载回来


![下载/在线演示](https://img.lbjheiheihei.xyz/FgeCmplLp4fmy9Wx0crN41dubQ3s "下载/在线演示")



下载回来是压缩包，解压后全部复制到  /用户名.github.io 这个文件夹。

可以修改通用 `_config.yml` 文件来搭建自己的博客；文章都放在`_posts`文件夹数里，每篇文章的开头都需要设置一些头信息，这个不同的模板是不一样的，需要自行判断，自行修改。



![_config.yml](https://img.lbjheiheihei.xyz/FuIySDm1l-tTy86YjMj1RrqeXBW4 "_config.yml")



修改完后要同步，Summary 自己能看懂就行，随便写写也无所谓。写完后

选择 Commit to master 。


![Commit](https://img.lbjheiheihei.xyz/FvkRfRc_DWSnAoUNTAtctIl0roBY "Commit")



然后选择同步，Push origin。


![Push origin](https://img.lbjheiheihei.xyz/Frij2ok2r2d1lWfGavDDqWzuavLD "Push origin")



![gif演示](https://img.lbjheiheihei.xyz/FqRxYtf2wp7EYtHw3TwxG6naOTiV "gif演示")



同步可能会有延迟，要稍微等一下。

# 5  我的搭建

我是自己在 GitHub 那 fork 了一份模板，然后修改的。

[https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O)

![fork 的模板](https://img.lbjheiheihei.xyz/Fv4f9pD3wZJTsdCKNh-BsFMG-_zF "fork 的模板")



然后就是根据它给的说明文档进行修改。

### 修改站点信息

![修改站点信息](https://img.lbjheiheihei.xyz/FoTFlzuKI9iEG2pP05AEEXUIlZjW "修改站点信息")

### 修改封面

![修改封面](https://img.lbjheiheihei.xyz/FrmX9hKBgxC7CIdAcvIbhHTYU7wF "修改封面")

### 修改个人介绍

![修改个人介绍](https://img.lbjheiheihei.xyz/FtIBCi0XxBKD5yYLpYy23nay-M9B "修改个人介绍")

[https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O) 里面有详细的说明，不赘述。

# 6  相关说明

_posts 文件夹里面就是你写的博文，要用 markdown 语法写，不然解析不了。



**相关链接：**

参考的说明:[http://cyzus.github.io/2015/06/21/github-build-blog/](http://cyzus.github.io/2015/06/21/github-build-blog/)

GitHub 的说明: [https://pages.github.com/](https://pages.github.com/)

 jekyll 主题: <http://jekyllthemes.org/>

使用的模板: [https://github.com/kaeyleo/jekyll-theme-H2O](https://github.com/kaeyleo/jekyll-theme-H2O)

我博客的 Github 地址：[https://github.com/weijunzii/weijunzii.github.io](https://github.com/weijunzii/weijunzii.github.io)
