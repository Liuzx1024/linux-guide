<!--Chapter1.md-->
# 第一章 基础知识

## 1.1 绪论：操作系统
<blockquote>&emsp;&emsp;操作系统理论在计算机科学中，為歷史悠久而又活跃的分支；而操作系统的设计与实现则是软件工业的基础与核心。<div align="right">——来自[维基百科][1]</div></blockquote>

> 没有软件的计算机只是一堆废铁

&emsp;&emsp;操作系统（Operating System，OS），是管理计算机硬件和软件资源的计算机程序，同时也是计算机系统的核心和基石。操作系统需要处理如管理和配置内存、决定系统资源供应的优先次序、控制输入输出装置、操作网络及管理文件系统等基本事务。操作系统为用户提供与应用程序交互的方式，如**图形用户界面（Grapical User Interface，GUI）**、**命令行（Command Line或者Shell）**等。应用程序通过**系统调用（System Call)**（在Windows上叫Windows API）来通过操作系统内核访问硬件资源。一般而言，一个完整的计算机系统由**内核（Kernel）**和**用户态应用程序(Usermode Application，APP)/库(Library，参见后文)**组成。

<div align="center"> <img src="400px-Operating_system_architecture.svg.png"></div>

&emsp;&emsp;简单来讲上面的图可以带给我们底下的概念：
* **操作系统的核心直接根据硬件写成，所以一个特定的操作系统核心不能在不同的硬件架构下运行。**举例来讲，pc版的Win10不能在手机上运行。
* **操作系统只是管理整个硬件资源，包括cpu、内存等。**如果没有其他应用程序，操作系统只能让计算机get ready而无法运作其他功能。
* **任何应用程序的开发都依赖于操作系统提供的借口。**比如说，给windows开发的程序无法在linux上运行。

> 为了与**浏览器中的web应用程序**区分，上述的用户态应用程序也被称为**本地应用程序（Native Application）**。本指南所讲述的“软件开发”主要指Native Application的开发。

&emsp;&emsp;操作系统的类型非常多样，不同类型的计算机安装的操作系统可从简单到复杂，从物联网的嵌入式设备到手机、PC再到超级计算机，操作系统存在着很大的差异。因而许多操作系统的开发者对于它涵盖的定义的认识也不大一致，例如有些操作系统整合了GUI，有些则将GUI看成非必要的应用程序。

&emsp;&emsp;常见的操作系统（过了气的就不列举了）:

* Windows：由Microsoft开发，由于哲学理念（见前言）以及**设计过于玄学**以及正版太贵盗版横行以及在这个平台上开发跟~~往屁股里塞榴莲~~一样浑身难受（虽说Visual Studio被称为宇宙第一IDE），我不喜欢这玩意——虽然说这玩意在PC操作系统市场上占据的份额最多，一般人也大多用它（略略略）——话说回来，微软近年形象改变了许多，在开源上的投入也在不断加大，甚至打出了Microsoft Love Linux的旗号，Win10上也推出了**Linux子系统（Windows Subsystem for Linux，WSL）**（很多人说性能不好？），可以在Windows Store搜索Linux了解一下。
*  MacOS（OSX）和IOS：由苹果公司开发，基于**开源（开放源代码，Open Source，即代码可以被自由的获得）**的Darwin。优化就不要说了，业界领先，就是设备*太贵*，买不起（略略略）——这个平台上开发算是比较舒服的，很多程序员也喜欢，毕竟是个类UNIX，逼格也高。（**价格与逼格是主要矛盾**）
* Linux:很多人对Linux的不良印象来自中科红旗的倒闭，但要问世界上哪个操作系统被最广泛的使用——不是Windwos，而是Linux。从物联网（Internet of Things，IOT）嵌入式设备到安卓手机还有大部分的服务器和超级计算机——都基于Linux。可以说，**Linux象征着未来**。——说到底，中国人目前没有能力做自主操作系统——可别跟我说什么氢OS miui，安卓换了个皮而已。

## 1.2 初识Linux
<div align="center"><img src="150px-NewTux.svg.png"></div>

> &emsp;&emsp;Linux是一種自由和開放源碼的**類UNIX（Unix Like）**作業系統。该操作系统的**内核**由林纳斯·托瓦兹（Linus  Torvald）在1991年10月5日首次发布，再加上**使用者空間的應用程式**之後，成為Linux作業系統。Linux也是自由软件和开放源代码软件发展中最著名的例子。只要遵循**GNU通用公共许可证（GPL）**，任何个人和机构都可以自由地使用Linux的所有底层源代码，也可以自由地修改和再发布。
——来自[维基百科][2]


### 1.2.1 历史：Linux之前
<blockquote> <strong>“C语言因Unix而生”</strong></blockquote>

1. 1969年以前:一个伟大的梦想——Bell,MIT与GE的Multics系统
2. 1969年:Ken Thompson 的小型file server system
3. 1973年:**Unix的正式诞生**,Ritchie等人以** C 语言**写出第一个正式 Unix 核心
4. 1977年:重要的 Unix 分支——BSD 的诞生
5. 1979年:重要的 System V 架构与版权宣告
6. 1984年之一:x86 架构的 Minix 操作系统开始撰写并于两年后诞生
7. 1984年之二:GNU 计划与 FSF 基金会的成立
8. 1988年:图形接口 XFree86 计划
9. 1991年:芬兰大学生 Linus Torvalds 的一则简讯——Linux诞生

### 1.2.2 Linux发展史

> &emsp;&emsp;Linux 操作系统的诞生、发展和成长过程始终依赖着五个重要支柱：UNIX 操作系统、MINIX 操作系统、GNU计划、POSIX 标准和Internet 网络。
——来自[百度百科][4]

* 1981 年IBM公司推出微型计算机IBM PC。
* 1991年，GNU计划已经开发出了许多工具软件，最受期盼的GNU C编译器已经出现，GNU的操作系统核心HURD一直处于实验阶段，没有任何可用性，实质上也没能开发出完整的GNU操作系统，但是GNU奠定了Linux用户基础和开发环境。
* 1991年初，林纳斯·托瓦兹开始在一台386sx兼容微机上学习minix操作系统。1991年4月，林纳斯·托瓦兹开始酝酿并着手编制自己的操作系统。
* 1991 年4 月13 日在comp.os.minix 上发布说自己已经成功地将bash 移植到了minix 上，而且已经爱不释手、不能离开这个shell软件了。
* 1991年7月3日，第一个与Linux有关的消息是在comp.os.minix上发布的（当然此时还不存在Linux这个名称，当时林纳斯·托瓦兹的脑子里想的可能是FREAX，FREAX的英文含义是怪诞的、怪物、异想天开等）。
* 1991年的10月5日，林纳斯·托瓦兹在comp.os.minix新闻组上发布消息，正式向外宣布Linux内核的诞生（Freeminix-like kernel sources for 386-AT）。
* 1993年，大约有100余名程序员参与了Linux内核代码编写/修改工作，其中核心组由5人组成，此时Linux 0.99的代码大约有十万行，用户大约有10万左右。
* 1994年3月，Linux1.0发布，代码量17万行，当时是按照**完全自由免费**的协议发布，随后正式采用GPL协议。
* 1995年1月，Bob Young创办了RedHat（小红帽），以GNU/Linux为核心，集成了400多个源代码开放的程序模块，搞出了一种冠以品牌的Linux，即RedHat Linux,称为Linux"发行版"，在市场上出售。这在经营模式上是一种创举。
* 1996年6月，Linux 2.0内核发布，此内核有大约40万行代码，并可以支持多个处理器。此时的Linux 已经进入了实用阶段，全球大约有350万人使用。
* 1998年2月，以Eric Raymond为首的一批年轻的"老牛羚骨干分子"终于认识到GNU/Linux体系的产业化道路的本质，并非是什么自由哲学，而是市场竞争的驱动，创办了"Open Source Intiative"（开放源代码促进会）"复兴"的大旗，在互联网世界里展开了一场历史性的Linux产业化运动。
* 2001年1月，Linux 2.4发布，它进一步地提升了SMP系统的扩展性，同时它也集成了很多用于支持桌面系统的特性：USB，PC卡（PCMCIA）的支持，内置的即插即用，等等功能。
* 2003年12月，Linux 2.6版内核发布，相对于2.4版内核2.6在对系统的支持都有很大的变化。
* 2004年的第1月，SuSE嫁到了Novell，SCO继续顶着骂名四处强行“化缘”， Asianux， MandrakeSoft也在五年中首次宣布季度赢利。3月，SGI宣布成功实现了Linux操作系统支持256个Itanium 2处理器。&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;——以上均选自[百度百科][4]

## 1.2.3 Linux的基本思想
&emsp;&emsp;Linux的基本思想有两点最主要的：第一，一切都是文件。是的没错，Linux把系统中所有东西都归结为文件，包括一些设备（软件或硬件）、命令、进程、甚至是操作系统。可以把他们理解为具有各自特性或类型的文件。&emsp;&emsp;第二，每个软件都有自己确定的用途。这也是实现前文所说的系统高效的重要条件。











<div align="right">July 26, 2018 4:57 PM</div>

[1]:https://zh.wikipedia.org/wiki/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F
[2]:https://zh.wikipedia.org/wiki/Linux
[3]:kernel.org
[4]:https://baike.baidu.com/item/linux