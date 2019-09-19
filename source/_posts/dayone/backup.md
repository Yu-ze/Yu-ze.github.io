---
title: hexo备份管理
tags: backup
categories: 学习日记
---

#### 前言
今天逛星球的时候看到一位老兄电脑存的两年数据因为电脑重装系统没有了，全是心血，就这样没了，想死的心都有了。无独有偶，我的一位好友也因为win系统更新丢了许多珍贵的数据，所以为了避免重蹈这两位老兄的覆辙了，我把一些电脑的一些重要文件都备份了。至于这个博客的话，因为是静态网站，这些源码都保存在我电脑里，我怕有一天电脑坏了，没办法备份下来，所以为了预防风险，我在网上查了一下怎么备份hexo博客。

我这个人比较懒，能躺着就不愿意坐着，所以我采用了最省事的一个办法：用backup插件管理。

#### 备份博客
##### 安装backup
github上有git-backup的源码，[git-backup官网](https://github.com/coneycode/hexo-git-backup)，[git-backup的中文说明](https://github.com/coneycode/hexo-git-backup/wiki/%E4%B8%AD%E6%96%87%E8%AF%B4%E6%98%8E-zh_CN)，看着这个说明安装即可。

安装步骤：
1. 在电脑桌面上右键打开`git-bash`
2. 一般来说，现在的hexo大部分都是3.0版本的了，所以使用`npm install hexo-git-backup --save`即可
3. 插件更新先使用`npm remove hexo-git-backup`卸载，然后再用`npm install hexo-git-backup --save`更新

##### 创建新分支
在github上打开存放博客源代码的仓库，
