---
layout: post
title: install ipython notebook 
category: python
tags: python
description: install ipython notebook
---

## 介绍
IPython是个比默认的Python Shell好用得多的Python交互命令行界面，支持变量自动补全、自动缩进、Bash Shell命令，并内置了许多有用的功能和函数。
IPython notebook 是一个基于 IPython REPL 的 web 应用。IPython运行结果可以单独保存，格式为 .ipynb 。现 GitHub 已提供 IPython notebook 的在线预览。
ipython notebook现在名为jupyter noteboook。

>此文章基于Windows系统环境

## 安装命令
在命令行下执行指令：

>pip install "ipython[notebook]"


## 运行Ipython notebook
在命令行下执行指令：

>ipython notebook

现在升级为jupyter，所以也可以使用命令

>jupyter notebook

默认浏览器会自动打开本地的Ipython notebook页面

>http://localhost:8888/tree#

如图：
![](/assets/postImg/2016-03-02-A01.png)

点击右上角的按钮New-->Folder, 新建文件夹用来存储IPython运行结果，新建文件夹默认名字为Untitled Folder。
选中此文件夹左侧的方框，会出现Rename按钮用来重命名此文件夹。
直接点击此文件夹，进入文件夹内部，
此时再点击右上角的New按钮，选择Python2，就会打开Ipython notebook的.ipynb文件的编辑页面，如下图：

![](/assets/postImg/2016-03-02-A02.png)

## 结束Ipython notebook
在上述命令行窗口按「Ctrl」键加「C」键

## 使用Ipython notebook过程中可能出现的问题

### 问题1： 快捷键怎么用？

答： 点击工具栏的Help————>Keyboard Shortcuts,即可看到所有快捷键的说明

### 问题2： tab键的变量自动补全、函数提示不能用.

答： IPython tab completion的功能不可用，是因为pyreadline library没有正确安装. 在Windows系统下的命令行输入：

>pip install pyreadline


### 问题3： pip install pyreadline不能正确执行。
答： 可以尝试重新安装Ipython，再执行pyreadline的安装命令：

>pip uninstall ipython

>pip install ipython

>pip install pyreadline


### 问题4： 正确安装pyredline之后，在如下情况下为何Tab键仍然失效？
![](/assets/postImg/2016-03-02-A03.png)

答：需要先按shift键+enter键执行代码import datetime后，datetime.<tab>才会凑效，如下图所示：

![](/assets/postImg/2016-03-02-A04.png)

### 问题5： 查看关于变量的一些通用信息(对象内省 object introspection)

答：在变量后加？问号，按shift键+enter键执行命令，即可看到关于变量b的一些通用信息，如下图所示：
![](/assets/postImg/2016-03-02-A05.png)

### 问题6： 使用matplotlib绘图，直接执行绘图命令后，GUI事件循环会接管IPython会话的控制权，直到该绘图窗口关闭为止，如下图所示，那么该如何实现交互式的数据分析可视化呢？
![](/assets/postImg/2016-03-02-A06.png)

答：在网页中嵌入绘图库绘制的图形，可以使用 %matplotlib inline 或者 %pylab inline 启动这个功能。
再次执行绘图命令，结果如下图所示：
![](/assets/postImg/2016-03-02-A07.png)