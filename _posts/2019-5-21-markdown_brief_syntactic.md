---
layout: post
title: Markdown 语法
date: 2019-5-21
tags: [Writing]
comments: true
author: OriginalXY
toc: true
---
Markdown是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。markdown是为那些需要经常码字或者进行文字排版的、对码字手速和排版顺畅度有要求的人群设计的，他们希望用键盘把文字内容打出来后就已经排版好了，最好从头到尾都不要使用鼠标。这些人包括经常需要写文档的码农、博客写手、网站小编、出版业人士等等** 参考[**百度百科**](https://baike.baidu.com/item/markdown/3245829?fr=aladdin)

<!-- more -->

## Markdown语法
开始学习markdown就有必要了解一下基本的语法，这里罗列一些基本的语法，这些语法是非常简单且常用的，能够帮助你快速掌握这门轻量的标记语言并且能够动手写自己的小博客，动手写起博客之后一些高级的用法可以边用边学。

- **标题样式**
在Markdown中，若一段文字被定义为标题，只要在这段文字前加 # 号即可。注意这里#号后面是有空格的。
>'# '一级标题， '## '二级标题， '### '三级标题
- **列表**

无序列表使用`*`、+和-来做为列表的项目标记，这些符号是都可以使用的,注意符号与字符间**必须有一个空格**。
>* Candy.
>* Gum.
>* Booze.
>- Candy.
>- Gum.
>- Booze.
>+ Candy.
>+ Gum.
>+ Booze.

有序的列表则是使用一般的数字接着一个英文句点作为项目标记：
>1. Red
>2. Green
>3. Blue
- **目录**
>用`[TOC]`生成目录
- **加粗** 用双*号
>`**xxx**` **xxx**
- **引用** 由'>'开头
>`>`
- **斜体**单*号
>`*x*` *x*
- **删除线** 双波浪线
>`~~xx~~` ~~xx~~
- **分割线** 另起一行输入三个连续*
>`***` 
- **详细描述** 由'<'开头（注意：在sublime中每条<末尾要加两个空格才会连续显示，否则会独立显示）
>`<`

- **下划线** ++ 开头 ++结尾
>`++下划线++` ++下划线++

- **高亮标记** ==开头 ==结尾
>`==高亮标记==` ==高亮标记==

- **换行**  在末尾敲击两个以上空白，然后回车

- **插入链接**
>语法：`[链接说明](uri)`

- **插入图片**   
>语法: `![image](uri)` 语法上和插入链接只是多了个！ 插入图片的方法有很多种，csdn markdown提供插入图片功能，也可以注册各种图床（七牛云，SM.MS，工具可以用PicGO）   

## 图片插入中遇到的问题

其实github做图床还是不错的，索性直接引用，但要注路径问题，三种方式：
1. 项目绝对路径：https://raw.githubusercontent.com/用户名/项目名称/master/图片文件夹/xxx.png
2. 博客绝对路径：https://githubpages地址/图片文件夹/xxx.png
3. 图片还可以用相对路径的方法插入，必须和markdown文件相同目录下的文件或文件夹，但这种方法不适合写单篇的csdn或知乎文章，可以用于写书写个人博客。语法示例：   
`![pic](image/test.png) 或 ![pic](test.png)`

- **程序员必备代码段**  以三个 ` 开头带程序类型和 ``` 结尾，中间包含代码段
```cpp
#include<iostream>
using namespace std;
class test
{
  int a;
  string str;
};
```
- **代码框** 用两个 ` 把代码框在中间就是代码段，也可以用于防止markdown语法生效（类似转义符）   

    `it is code`

- **表格**   

header 1 | header 2  
---|---   
row 1 col 1 | row 1 col 2  
row 2 col 1 | row 2 col 2



## 编辑器推荐

- Typora。

	实时显示Markdown神器，推荐设置：
	1. 勾选自动保存；
	2. 禁止发送匿名使用数据；
	3. 勾选一体化；
	4. 勾选显示状态栏；
	5. 勾选侧边栏的大纲视图允许折叠和展开；
	6. 勾选显示行号。

- Sublime。

	顺便提下sublime浏览器预览的设置：
	1. 如果只是简单的在浏览器中预览，不需要像网上说的那样安装`SideBarEnhancements`插件。因为这个插件功能太强，配置起来也麻烦；
	2. 在不需要其他复杂功能的情况下，推荐使用`openInBrowser`插件，推荐使用`Package Control`进行安装；
	3. 安装完成后，只需要一句简单的设置——绑定快捷键即可：打开`Preference->Key Bindings - User`，在里面加上一句：`{ "keys": ["f12"], "command": "open_in_browser" }` ；
	4. 设置完成后，按'F12'键就可以直接在 默认浏览器 中打开并预览了。

- VSCode

- MarkdownPad

## 参考
- [Typora 安装及设置插入图片](https://www.jianshu.com/p/4a4af09af914)
- [Typora 完全使用详解](https://sspai.com/post/54912)
- [写作系统三件宝：印象笔记，幕布，Typora](https://www.jianshu.com/p/67edbe3f864b)