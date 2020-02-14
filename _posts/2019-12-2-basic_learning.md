---
layout: post
title: "学渣的本愿：编程基础"
date:   2019-12-2
tags: [Programming]
comments: true
author: OriginalXY
toc: true
---

本博作为学渣要补补基础，第一版是C++相关。因本人本科编程基础是从C出发，配上计算机基础偏向是。现在也有很多高校程序设计是从python出发，Anyway都一样（当然我知道很多人会去刷LeetCode，看剑指offer也可以，都是为了糊口饭吃，我菜所以飘过）之后会持续更新。

## 计算机基础综合

考过硕的应该知道408：数据结构、计算机组成原理、计算机网路、操作系统。

基础知识太重要了！这是科班区别于培训班的最大不同，理论知识不一定马上能用于项目上，但当与人讨论起某个技术问题时你能够知道它深层次的原因，看问题的角度会更加全面和系统。

比如：可能听过堆栈的名词，但知道它的具体结构和不同吗？学完数据结构就明白了；知道计算机会算加减乘除，但具体是如何实现的呢？组成原理会告诉答案；知道程序执行的时候怎么区分指令地址和数据地址的吗？操作系统会告诉答案。

所以如果大学不是计算机相关专业，或者是本专业但是没有完全吃透基础的话，建议务必抽时间好好学习。

### 书本参考

我觉得我本科学的教材就很好。

- 数据结构 

数据结构与算法分析 : C语言描述 

> 原书名：Data Structures and Algorithm Analysis in C:Second Edition  
> 作者：[美] Mark Allen Weiss  
> 出版社：机械工业出版社  
> 书号：ISBN 9787111127482   

![数据结构](https://originalxy.github.io/images/2019-12-2-basic_learning/数据结构.png)

挑战程序设计竞赛

适合入门刷OJ的，之后自己去刷吧
> 原书名：プログラミングコンテストチャレンジブック [第2版]　~問題解決のアルゴリズム活用力とコーディングテクニックを鍛える~  
> 作者：[日]秋叶拓哉 / [日]岩田阳一 / [日]北川宜稔  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115320100   

![挑战程序设计竞赛](https://originalxy.github.io/images/2019-12-2-basic_learning/挑战程序设计竞赛.png)

- 计算机组成原理  

计算机组成与设计：硬件/软件接口

> 原书名：Computer Organization and Design: The Hardware/Software Interface  
> 作者：[美] David A.Patterson / John L.Hennessy  
> 出版社：机械工业出版社  
> 书号：ISBN 9787111202141    

![计算机组成原理](https://originalxy.github.io/images/2019-12-2-basic_learning/计算机组成原理.png)

- 操作系统 

操作系统概念

> 原书名：Operating System Concepts(Ninth)  
> 作者：[美] Abraham Silberschatz / Peter B. Galvin / Greg Gagne  
> 出版社：机械工业出版社  
> 书号：ISBN 9787111604365     

![操作系统](https://originalxy.github.io/images/2019-12-2-basic_learning/操作系统.png)

- 计算机网络 

计算机网络--自顶向下方法

> 原书名：Computer Networking：A Top-Down Approach，Sixth Edition  
> 作者：[美] James F.Kurose / Keith W.Ross  
> 出版社：机械工业出版社  
> 书号：ISBN 9787111453789    

![计算机网络](https://originalxy.github.io/images/2019-12-2-basic_learning/计算机网络.png)

### 视频参考

国内MOOC做的还行，看过一点，Coursera的个人会更推荐，可以在知乎上面搜其他博主的推荐，当然B站也行。

[武汉大学-数据结构 MOOC网络课程 ](https://www.icourse163.org/course/WHU-1001539003)

[华中科技大学-计算机组成原理](https://www.icourse163.org/course/HUST-1003159001)

[电子科技大学-计算机组成原理](https://www.icourse163.org/course/UESTC-1001543002)

[华中科技大学-操作系统原理](https://www.icourse163.org/course/HUST-1003405007)

[哈尔滨工业大学-计算机网络](https://www.icourse163.org/course/HIT-154005)

## C++基础

**语法是一门语言的基础。**C++的基础语句和语法和C是很像的，最大的不同在class和异常处理机制，还有模板的应用，所以有C基础语法学起来是很快，没有C基础一样可以学。

- C++

C++ Primer 中文版（第五版）

> 原书名：C++ Primer, 5th Edition  
> 作者：[美] Stanley B. Lippman / Josée Lajoie / Barbara E. Moo  
> 出版社：电子工业出版社  
> 书号：ISBN 9787121155352  
 
![C++ Primer 中文版](https://originalxy.github.io/images/2019-12-2-basic_learning/C++ Primer 中文版.png)

C++ 大学教程（第九版）

> 原书名：C++ How to Program  
> 作者：[美]Paul Deitel / Harvey Deitel    
> 出版社：电子工业出版社  
> 书号：ISBN 9787121290015  
 
![C++ 大学教程](https://originalxy.github.io/images/2019-12-2-basic_learning/C++ 大学教程.png)

## C++进阶

STL源码剖析

STL提供了丰富的算法库支持和各种容器。C++标准库提供了包括最基础的标准输入输出`iostrem`、各种容器`vector、set、string` ，熟练掌握标准库，不用重复造轮子（练手学习目的的造轮子除外）写出更C++的代码。

> 原书名：STL源码剖析  
> 作者：侯捷      
> 出版社：华中科技大学出版社  
> 书号：ISBN 9787560926995  

![STL源码剖析](https://originalxy.github.io/images/2019-12-2-basic_learning/STL源码剖析.png)

Effective C++

改善程序与设计的55个具体做法，非常值得一看，老手和新手的差别由此产生。

> 原书名：Effective C++:55 Specific Ways to Improve Your Programs and Designs,3rd Edition  
> 作者：侯捷      
> 出版社：电子工业出版社  
> 书号：ISBN 9787121123320  

![Effective C++](https://originalxy.github.io/images/2019-12-2-basic_learning/Effective C++.png)

More Effective C++（中文版）

同一个作者，继Effective C++之后于1996推出这本“续集”。条款变得比较少，页数倒是多了，原因是这次选材更高阶，尤其第5章。Meyers将此章命名为技术。

> 原书名：More Effective C++:35 Specific Ways to Improve Your Programs and Designs  
> 作者：侯捷      
> 出版社：电子工业出版社  
> 书号：ISBN 9787121125706  

![More Effective C++](https://originalxy.github.io/images/2019-12-2-basic_learning/More Effective C++.png)

深度探索C++对象模型

> 原书名：Inside the C++ Object Model  
> 作者：侯捷      
> 出版社：电子工业出版社  
> 书号：ISBN 9787121149528  

![深度探索C++对象模型](https://originalxy.github.io/images/201-12-2-basic_learning/深度探索C++对象模型.png)

深入理解C++11

新标准提供了解决现有问题更优雅、更C++的实现。现行的大部分C++软件还是C++98的标准，C++98是C++的第一个标准，经历这么多年的发展，从前你需要从Boost库（一个在C++98年代的准C++标准）获得的对C++的扩充支持的大部分功能已经纳入了C++11和甚至C++2X更新的标准当中，与时俱进拿起更先进的生产工具，工具就是效率。

> 原书名：深入理解C++11：C++ 11新特性解析与应用  
> 作者：Michael Wong / IBM XL编译器中国开发团队  
> 出版社：机械工业出版社  
> 书号：ISBN 9787111426608  

![深入理解C++11](https://originalxy.github.io/images/2019-12-2-basic_learning/深入理解C++11.png)

## Linux基础

鸟哥的Linux私房菜

几乎所有互联网服务都跑在linux系统上，对Linux系统一无所知那更加谈不上后台开发了，所以要先学习linux系统操作，文件管理，系统命令，文件系统，权限管理，系统服务等。至于shell script 就类似win的批处理脚本。

> 原书名：鸟哥的Linux私房菜  
> 作者：鸟哥  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115226266  

![鸟哥的Linux私房菜](https://originalxy.github.io/images/2019-12-2-basic_learning/鸟哥的Linux私房菜.png)

Linux Shell脚本攻略

shell script 就类似win的批处理脚本。

> 原书名：Linux Shell Scripting Cookbook  
> 作者：(印)拉克什曼  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115264725  

![Linux Shell脚本攻略](https://originalxy.github.io/images/2019-12-2-basic_learning/Linux Shell脚本攻略.png)

## Linux进阶

UNIX环境高级编程

除了系统命令服务和利用shell script写小工具。还要学习系统编程接口、系统调用API、内存管理、进程间通信（IPC）。

> 原书名：Advanced Programming in the UNIX Environment  
> 作者： [美]W.Richard Stevens / Stephen A.Rago  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115147318  

![UNIX环境高级编程](https://originalxy.github.io/images/2019-12-2-basic_learning/UNIX环境高级编程.png)

UNIX网络编程 卷1：套接字联网API（第3版）

在同一台机器上进程间的通信（IPC）有多种方式，消息队列、FIFO、共享内存等。网络编程套接字是指：分布在不同机器上的程序通过系统提供的网络通信接口，跨越网络将不同机器上的进程连接起来，实现跨机器的网络通信。一般有UDP套接字、TCP套接字、Unix Domain，当然，如果你是通信从业者对SCTP套接字肯定也不会陌生。

> 原书名：Unix Network Programming, Volume 1: The Sockets Networking API (3rd Edition)  
> 作者：[美] W.Richard Stevens / Bill Fenner / Andrew M. Rudoff  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115228406  

![UNIX网络编程 卷1：套接字联网API](https://originalxy.github.io/images/2019-12-2-basic_learning/UNIX网络编程 卷1：套接字联网API.png)

UNIX网络编程 卷2：进程间通信（第2版）

> 原书名：UNIX Network Programming,Vovum 2：Interprocess Communications,Second Edition  
> 作者：[美]W. 理查德•史蒂文斯（W. Richard Stevens）  
> 出版社：人民邮电出版社  
> 书号：ISBN 9787115367204  

![UNIX网络编程 卷2：进程间通信](https://originalxy.github.io/images/2019-12-2-basic_learning/UNIX网络编程 卷2：进程间通信.png)

## 数据库和存储

程序运行数据都在易失性的内存中，需要持久化存储时就需要数据库。一个后台服务系统一般来说都需要考虑数据落地和持久性存储的问题，这时就会涉及到数据库选型和应用，数据库分为关系型数据库和非关系型数据库。

**关系型数据库**：指采用了关系模型来组织数据的数据库，代表是MySql。关系模型指的就是二维表格模型，而一个关系型数据库就是由二维表及其之间的联系所组成的一个数据组织。

**非关系型数据库**：以键值对存储，且结构不固定，每一个元组可以有不一样的字段，每个元组可以根据需要增加一些自己的键值对，不局限于固定的结构，可以减少一些时间和空间的开销。代表有redis、memcached，腾讯内部组件ckv也是非关系型数据库。

推荐看下[redis中文网](http://redis.cn/) 

SQL必知必会

> 原书名：Sams teach yourself SQL in 10 minutes,4th edition  
> 作者：[美]福达 (Ben Forta) 
> 出版社：人民邮电出版社  
> 书号：ISBN 787115313980  

![SQL必知必会](https://originalxy.github.io/images/2019-12-2-basic_learning/SQL必知必会.png)

高性能MySQL

> 原书名：High Performance MySQL,3rd  
> 作者：[美] 施瓦茨 (Baron Schwartz) / 扎伊采夫 (Peter Zaitsev) / 特卡琴科 (Vadim Tkachenko) 
> 出版社：电子工业出版社  
> 书号：ISBN 9787121198854  

![高性能MySQL](https://originalxy.github.io/images/2019-12-2-basic_learning/高性能MySQL.png)

## 算法基础

**计算机算法就是利用编程语言编写出计算机能理解的解决问题的方法。** 
除了上面数据结构和算法的书（有心看下算法竞赛入门经典/算法艺术与信息学竞赛也行，初高中玩信息学竞赛的书），同时在[牛客](https://www.nowcoder.com/activity/oj)或者[Leetcode](https://leetcode-cn.com/ )上刷题，因为看书太枯燥很容易失去耐心，在线刷题的好处是你可以每天定目标，享受每个题目通过的快感，有正向反馈更容易坚持下来。

## 架构能力

这时候考虑的东西会更多，包括服务模型的设计：是多进程还是多线程？甚至协程微线程，分布式还是集中式？存储的选型？数据库选型？存储的数据特征？应用场景？比如社交应用的数据用非关系型数据库来存储可能更好；如果是电商订单类型的数据，那么用关系型数据库来存储可能更好。

推荐个C++百科全书，类似Linux的man手册，平常开发查忘记了函数名或者容器用法直接搜索非常方便：[cppreference](https://en.cppreference.com/w/cpp)

## 总结

> 人们眼中的天才之所以卓越非凡，并非天资超人一等，而是付出了持续不断的努力。1万小时的锤炼是任何人从平凡变成世界级大师的必要条件。要成为某个领域的专家，需要10000小时，按比例计算就是：如果每天工作八个小时，一周工作五天，那么成为一个领域的专家至少需要五年。这就是一万小时定律。

如何提高编程能力？找项目，找感兴趣的东西用代码去实现它，爬虫，造轮子，小游戏，兴趣是最好的老师，这点在编程和技术学习上完全适用。


