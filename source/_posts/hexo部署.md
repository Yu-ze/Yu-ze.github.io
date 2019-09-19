---
title: 建立博客
categories: Hexo
---

#### 前言

刚开始是打算用worldpress建站的，因为这个网上教程比较多。以前也有过类似经历，后来就放弃了，因为从长久来看，我就快要毕业了，没有学生优惠的话，一个月的月租还是负担重了点。建站的话首选阿里云的轻量级服务器，这个里面都部署好了各种建站的配置。而且学生认证后的话只要9.5元一个月，还算比较便宜的，在阿里云官网搜索云翼计划就可以找到相关优惠了。当然，腾讯云也有学生优惠，但我这里用的是github page + Hexo做的博客，那接下来就聊聊这过程吧。

刚开始是要要安装git在电脑上的，我的是windows操作系统。以前尝试过用github page做，但是中间出现了好多错误，就没成功，没想到这次可以部署了。之后要安装Node.js，这个之前我电脑也装过了。所以这次就不用装了，我只在B站上搜的教程，之后再配合官方hexo文档做的。官方文档比较详细，但是自己看视频跟着步骤走更容易一点，也就是结果复现。
<!-- more -->
#### 安装Hexo

1. 等所有的上面两个程序安装完成后就可以用nmp安装Hexo.在任意位置点击鼠标右键，然后打开Git Bash进入git命令操作台，然后输入以下命令
```
$ npm install -g hexo-cli
```
2. 在D盘或其他盘创建一个博客根目录，名字随意。例如我的就是blog
```
$ hexo init blog
$ cd blog
$ npm install
```
3. 安装完成之后根目录的内容如下
![图片](https://blog-1258579174.cos.ap-chengdu.myqcloud.com/images/blog%E6%88%AA%E5%9B%BE.png)

4. 在Git Bash执行命令
```
$ hexo g
$ hexo s
```
5. 在浏览器上输入http://localhost:4000就可以看到你的站点了，刚开始使用的是hexo的默认主题landscape

#### github配置
> 使用github托管hexo
1. 登录到github，新建一个仓库(New repository)
2. 只需要填写Repository name即可，名字格式为你的github用户名.github.io
![仓库](https://blog-1258579174.cos.ap-chengdu.myqcloud.com/images/github%E4%BB%93%E5%BA%93.png)

#### Hexo部署到github上
1. 修改站点配置文件，在hexo有两份主要的配置文件，一份是站点配置，另一份是主题配置,名称都是_config.yml。我这用的是VS code修改
```
deploy:
  type: git
  repo:
      github: git@github.com:chentging/yourname.github.io.git,master
```
2. 将hexo部署到github上
```
$ hexo g -d
```
执行完毕后再访问测试一下就可以了，访问测试：http://yourname.github.io

