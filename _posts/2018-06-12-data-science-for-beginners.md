---
layout: post
title: "Data science for beginners"
date: 2018-06-12
tags: [beginners]
comments: true
---

从零开始学Data Science多少不易，我深有体会。以下是我总结筛选的data science从入门到进阶的经典学习资料，希望减少初学者走弯路，尽快掌握必备技能。按顺序，难度依次递增，流统、实验方向的，拿走R就非常好了。

#### 有问题请查

1. 软件、程序包、方法、函数的官方文档.
2. Google.所以学会翻墙很重要,网上有教程.
3. 百度.
4. Communities. e.g. Stackoverflow, CSDN, github.

#### R
流统、实验方向的，拿走R就非常好了.
1. [Data Science Specialization](https://www.coursera.org/specializations/jhu-data-science) by Roger Peng et al from Johns Hopkins。非常经典的数据分析课程系列，总共10门课。不用担心R小白或统计小白，这个系列会系统地教授如何选择合适的分析方法以及不能再详细的数据分析步骤。
2.  [Tutorial: An example of data analysis using the R environment for statistical computing](http://www.css.cornell.edu/faculty/dgr2/pubs/list.html#pubs_m_R) by DG Rossiter from Cornell。上完Peng的课，刚好拿这个论文实例练手。

#### Machine learning

1. [Machine Learning](https://www.coursera.org/learn/machine-learning) by Andrew Ng from Stanford. (不想学Matlab，代码可以参考爱心人士的python代码哈[seddonr](https://github.com/seddonr/Ng_ML))
2. 南京大学周志华的西瓜书.
3. [值得时不时温习的书籍](https://www.zhihu.com/question/22221180).


#### Python and Deep learning

1. [Python for beginners](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000) by Xuefeng Liao.学python3版本为主,python2了解即可.python2虽然逐渐退出历史舞台了，但依然有不少代码是用python2写的，有时候难免要去解读。
2. [Deep learning](https://www.coursera.org/specializations/deep-learning) by Andrew Ng from Stanford.

#### Linux系统操作
有些程序包含成千上万条代码，普通台式机、笔记本执行时间动不动好几天上月，这时候就有必要将程序转移到服务器运行。服务器一般包含多个CPU、大容量内存，甚至有多个GPU，前面的程序运行时间可缩短至几个小时甚至更快。服务器操作系统一般是Linux，在台式机、笔记本的命令行窗口（Windows是cmd，mac是Terminal）输入命令，进行远程操控。为什么要用命令
行？因为远程操控的服务器，没有图形界面。Linux语言和Mac的Unix语言基本一致，所以两个系统的命令差不多。Windows则不同。

1. Mac用户请进：Mac OS X Terminal入门。
2. Windows用户请进：Windows 相比cmd，建议装Mobaxterm软件。
3. Linux入门.初学者先装个virtual box的虚拟机，然后装个Linux的ubuntu发行版就可以练Linux了。网上教程很多。
4. Tricky tools for Linux: **tmux**，必备，我最喜欢的功能是防止因为网络中断而程序中断、分屏；**vim**，最强的的代码编辑器；[proxchains4](https://www.jianshu.com/p/812f163cb1e2), 用来加快下载速度；**anaconda**，非常好用的python程序包和虚拟环境管理工具；**htop**查看cpu使用情况；**docker**。
5. Tricky tools for python:**ipdb**; **visdom**; **docker**; **visual studio code** especially the right click-go to definition, peek definition, find all references.
