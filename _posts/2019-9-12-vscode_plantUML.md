---
layout: post
title: VSCode + PlantUML绘图
date: 2019-9-12
tags: [Software Engineering]
comments: true
author: OriginalXY
toc: true
---

一般来说遇到画图的时候通常可以用用draw.io来画流程图，draw.io已经类似visio了，但是有时候拖拉起来也挺麻烦，所以想到找个工具用代码生成流程图。网上实际上工具蛮多的，typora就可以自带流程图，但是不是那么强大，也不如PlantUML专业，另一方面就是github不支持扩展的markdown语法。

## VSCode
Microsoft在2015年4月30日Build 开发者大会上正式宣布了 Visual Studio Code 项目：一个运行于 Mac OS X、Windows和 Linux 之上的，针对于编写现代 Web 和云应用的跨平台源代码编辑器。
<!-- more -->

该编辑器也集成了所有一款现代编辑器所应该具备的特性，包括语法高亮(syntax high lighting)，可定制的热键绑定(customizable keyboard bindings)，括号匹配(bracket matching)以及代码片段收集(snippets)。Somasegar 也告诉笔者这款编辑器也拥有对 Git 的开箱即用的支持。引用[百度百科](https://baike.baidu.com/item/visual%20studio%20code/17514281?fr=aladdin)

## PlantUML
PlantUML 是一个开源项目，支持通过脚本绘图，所以 PlantUML 是一种建模语言。根据[官网描述](http://plantuml.com/zh/)，PlantUML 可以绘制如下种类的 UML 图： 

> 时序图  
> 用例图  
> 类图  
> 活动图  
> 组件图  
> 状态图  
> 对象图  
> 部署图  
> 定时图 

同时还支持以下非UML图:

> 线框图形界面  
> 架构图  
> 规范和描述语言 (SDL)  
> Ditaa Diagram  
> 甘特图  
> MindMap Diagram  
> Work Breakdown Structure Diagram  
> 以 AsciiMath 或 JLaTeXMath 符号的数学公式  
> Entity Relationship Diagram  

通过简单直观的语言来定义这些示意图，与MarkDown有相似的作用，这两种语言一个主要面向文本渲染一个主要用于图形绘制。

### 语法

语法简单明了，查看以下[官方教程](http://plantuml.com/zh/sequence-diagram)，截取几个官网的事例图片在这里

- 活动图
![活动图](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-9-12-vscode_plantUML/活动图.png)
- 类图
![类图](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-9-12-vscode_plantUML/类图.png)
- 时序图
![时序图](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-9-12-vscode_plantUML/时序图.png)
- 用例图
![用例图](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-9-12-vscode_plantUML/用例图.png)
- 状态图
![状态图](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-9-12-vscode_plantUML/状态图.png)

### 安装
- 安装graphviz-2.38.msi
- 安装2个vscode插件:
> PlantUML、Graphviz Preview

#### 例子查看
```bash
@startuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response
@enduml
```
#### 预览
> Alt + D

#### 文件格式
> .wsd, .pu, .puml, .plantuml, .iuml

#### 如何导出
> F1/ctrl + shift+p; PlantUML:导出当前图表；
> 选择导出格式png，导出即可。

#### 参考
- [PlantUml基于VSCode的环境搭建](https://blog.csdn.net/xiaozhengchenxxm/article/details/82861433)
- [VSCode中Plantuml的使用](https://www.jianshu.com/p/5c7bc062aa2b)

