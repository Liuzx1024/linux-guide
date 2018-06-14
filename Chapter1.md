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











<div align="right">June 12, 2018 4:43 PM</div>

[1]:https://zh.wikipedia.org/wiki/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F
[2]:https://zh.wikipedia.org/wiki/Linux
[3]:kernel.org