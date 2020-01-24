---
title: hexo备份管理
tags: backup
categories: 学习日记
---

#### 前言
今天逛星球的时候看到一位老兄电脑存的两年数据因为电脑重装系统没有了，全是心血，就这样没了，想死的心都有了。无独有偶，我的一位好友也因为win系统更新丢了许多珍贵的数据，所以为了避免重蹈这两位老兄的覆辙了，我把一些电脑的一些重要文件都备份了。至于这个博客的话，因为是静态网站，这些源码都保存在我电脑里，我怕有一天电脑坏了，没办法备份下来，所以为了预防风险，我在网上查了一下怎么备份hexo博客

我这个人比较懒，能躺着就不愿意坐着，所以我采用了最省事的一个办法：用backup插件管理
<!-- more -->
#### 备份博客
##### 安装backup
github上有git-backup的源码，[git-backup官网](https://github.com/coneycode/hexo-git-backup)，[git-backup的中文说明](https://github.com/coneycode/hexo-git-backup/wiki/%E4%B8%AD%E6%96%87%E8%AF%B4%E6%98%8E-zh_CN)，看着这个说明安装即可

安装步骤：
1. 在电脑桌面上右键打开`git-bash`
2. 一般来说，现在的hexo大部分都是3.0版本的了，所以使用`npm install hexo-git-backup --save`即可
3. 插件更新先使用`npm remove hexo-git-backup`卸载，然后再用`npm install hexo-git-backup --save`更新

##### 创建新分支
在github上打开存放博客源代码的仓库，找到下图所示的Branch新建一个分支，我直接命名为backup
![](https://blog-1258579174.cos.ap-chengdu.myqcloud.com/images/%E5%88%86%E6%94%AF.png)

##### 配置主题文件
打开hexo根目录下的`_config.yml`，注意是站点配置文件，不是主题配置文件
在文件后添加
```
backup:
   type: git
   repository:
      github: git@github.com:xxx/xxx.git,branchName
      gitcafe: git@github.com:xxx/xxx.git,branchName`
```
如果想把主题也一起备份的话，只需要在_congfig.yml文件中加入`theme: next,landscape,xxx`即可，我使用的是next主题，所以为了避免备份博客之后重新配置主题，我是选择把主题也一起备份的
```
backup:
  type: git
  theme: next,landscape,xxx
  repository:
     github: git@github.com:xxx/xxx.git,branchName
     gitcafe: git@github.com:xxx/xxx.git,branchName
```

##### 添加ssh-keys
我电脑中本来是安装有ssh-keys，但是却是另一个github账号的密钥，所以出现了下面的错误提示
![](https://blog-1258579174.cos.ap-chengdu.myqcloud.com/images/%E9%94%99%E8%AF%AF%E6%8F%90%E7%A4%BA.png)

解决办法：删除.ssh文件夹下的密钥文件，在`git bush中`重新配置密钥
1. 运行：`ssh-keygen -t rsa -C "yourname@email.com"`，一路回车即可
2. 将.ssh目录下的公钥(也就是`id_rsa.pub`)文件用记事本打开，复制
3. 登录github，添加`new SSH key`，title名字可以随便填
4. 最后点击`add SSH key`即可

##### 备份
配置完成之后在git bash运行`hexo b`就可以备份自己的博客了，以后养成习惯在写完博客的时候hexo d 完之后顺便hexo b备份一下就OK了

