---
title: PPT中出现的MathType加载项每次启动显示加载错误
categories: 
- Office全家桶
- PPT
tag: MathType
---

之前是在word中为了输入数学符号方便，就在网上下载了MathType加载到word里面，用了一段之间感觉还蛮可以，之后做完课设之后发现MathType用的频率也不是很高，而且过了几天后MathType的一些重要功能都要**收费**才能使用,所以果断删除了

卸载之后发现这个根本删不干净，虽然我的word正常了，但是我的PPT每次打开后都出现了"抱歉，由于某种原因，PowerPoint无法加载：C:\Program Files\MathType\Office Support\32\MathType AddIn(powerpoint2016).ppam加载项"，这简直不能忍了，于是**谷歌**启动

<!-- more -->
网上找到的办法都是到注册表把MathType相关的项删除，然后重启PPT就可以了

1. win+R调出运行，输入regedit来编辑注册表信息
2. 删除计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\PowerPoint\Addins注册表下所有与mathtype相关的项
3. `ctrl + F`调出查找命令，输入**MathType AddIn**，删除找到的项就可以了

一开始我是用everything这个软件来找MathType，我把所有找到的文件都删了一遍，结果每次进去还是有这个提示，于是我在网上查了一下才知道，原来这个软件会在电脑自动生成很多的注册表，软件卸载时也会一大堆残留，跟以前卸载CAD2010卸不干净有的一拼了