---
layout: post
title: 使用github托管你的博客
category: blog
description: 蛋疼，瞎折腾
tags : [intro, beginner, jekyll, tutorial]
---
{% include JB/setup %}




## 最后效果

就是你所看到的这个样子

## 电脑系统

我使用的是mac os 10.8.5,所以以下所有描述都仅仅针对mac os系统

## 为什么要使用github托管博客

目前，可作为博客托管的环境且比较知名的免费服务有：

* 新浪的sae ，支持python，php
* 百度的bae，支持python，php，nodejs（处于内测阶段，我申请了好几次也不给我，擦）

另外还有一些知名的码农论坛，cnblogs，csdn等可以放心大胆的托管你的博客。为什么不用这些论坛写博客，却要用github来托管博客？确实我也觉得挺不可思议的。

github作为一个被码农关注度极高的网站，在你看不见的地方存放了大量优秀且开源的代码。你觉得好，对你有帮助你可以fork，如果你有什么意见，还可以contribute。好不夸张的说：如果你要成为一个牛逼的code，用github吧。所以为了习惯这种方式git的方式，我决定以后在github上放个博客，分享一些自己的学习心得。这就是我的目的，单不是唯一目的。

扁平化设计越来越流行了，连苹果都改了，改成了丑不拉几的ios7了。但不可否认的是现在的趋势是朝向简洁化，简洁才是王道。利用jekyll你可以轻松实现一个简洁的博客模板，然后push到github上。另外，jekyll自带了一些模块，比如：代码高亮，提供了一个可评论模块。这些才是我用jekyll，push到github托管博客的主要原因。

##jekyll是个神马？？

    如果你用过nodejs的express，你知道   express -t ejs blog 

    如果你用过yii，你知道：yiic webapp blog

    如果你用过python的django，你知道：django-admin.py startproject djproject

    好吧，jekyll就是类似上面的东西，它可以快速创建一个github博客。

## 来吧，按步骤来吧，创建一个属于你的github博客


### 1.安装jekyll

安装命令很简单：
    $ gem install jekyll
不过你很可能会遇到以下错误：
    ERROR:  Error installing jekyll:    
    ERROR: Failed to build gem native extension....Results logged to /Library/Ruby/Gems/1.8/gems/fast-stemmer-1.0.2/ext/gem_make.out

原因：Ruby 版本 1.8.7，太低，推荐升级到 1.9.3 。
建议使用 RVM，然而执行安装命令

### 2.安装rvm

注意在安装过程中输出的信息，会提示如何使用，如我安装过程是:
  
    To start using RVM you need to run `source /Users/irou/.rvm/scripts/rvm` 

当然也可以在打开终端时自动加载，在~/.bash_profile最后添加
    [[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
验证下是否安装成功：
    $ rvm --version

    rvm 1.23.14 (stable) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]
### 3.安装ruby

在RVM中安装Ruby 1.9.3

    rvm install 1.9.3

安装完后，测试下：

    gem --version

如果你看到：

    2.1.10

恭喜，你已经安装成功

启用： ruby 1.9.3

    rvm use 1.9.3

### 4.jekyll

通过ruby gems安装：

    gem install jekyll

    gem install jekyll-tagging


### 5.用jekyll创建博客

1.create a new respository

    go to your https://github.com and create a new respository named USERNAME.github.com

    注意：这里的USERNAME是占位，是你的github账户名，比如我的：wuya1234.github.com

2.git clone jekyll bootstrap到本地，文件名比如就叫：wuya1234.github.com

    git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.com

    cd USERNAME.github.com

  修改repo地址为你的repo，然后提交即可

    git remote set-url origin https://github.com/wuya1234/wuya1234.github.com.git
    git push origin master

 
 ### 6.本地预览

jekyll还提供一个本地预览模式。通过在终端：

jekyll server 

按照提示,在浏览器中输入：localhost:4000

就能本地预览啦，注意如果你的模板中有错误，本地预览是通不过的，通过--trace能看到哪报错进行调试

调试ok就可以push到github了

大功告成！！希望对你有用