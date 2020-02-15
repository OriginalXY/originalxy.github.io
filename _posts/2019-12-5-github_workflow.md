---
layout: post
title: Github分支策略与工作流
date: 2019-12-5
tags: [Programming]
comments: true
author: OriginalXY
toc: true
---

本文以图例和实际开发流程来讲解什么是分支策略以及分支的作用，以及经典的GitFlow工作流

## 分支策略

在团队开发中，一个项目的发布版本通常使用master分支，这也是一个项目最基本的和不可或缺的分支，当一个项目很小，代码量不多的情况下，团队成员可以只对master分支进行修改操作，并提交修改后的代码。 

![master分支](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/master分支.png)

但我们假设项目上线后，我们需要增加新的模块，这时候去修改master分支的代码显然不合适，因为master分支的代码应该是安全的和经过测试的，所以这时我们需要有develop分支。develop分支是开发时使用的分支，我们检出develop分支用以修改代码，修改完了之后，将develop分支和master分支合并，即可将修改的代码同步至master分支，这时的master分支才是稳定的。一个GitHub项目中至少有master分支和develop分支，这是最简单的分支策略。

![develop分支](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/develop分支.png)

## 分支功能

* master分支，即主分支。任何项目都必须有个这个分支。对项目进行tag或发布版本等操作，都必须在该分支上进行。
* develop分支，即开发分支，从master分支上检出。团队成员一般不会直接更改该分支，而是分别从该分支检出自己的feature分支，开发完成后将feature分支上的改动merge回develop分支。同时release分支由此分支检出。
* release分支，即发布分支，从develop分支上检出。该分支用作发版前的测试，可进行简单的bug修复。如果bug修复比较复杂，可merge回develop分支后由其他分支进行bug修复。此分支测试完成后，需要同时merge到master和develop分支上。
* feature分支，即功能分支，从develop分支上检出。团队成员中每个人都维护一个自己的feature分支，并进行开发工作，开发完成后将此分支merge回develop分支。此分支一般用来开发新功能或进行项目维护等。
* fix分支，即补丁分支，由develop分支检出，用作bug修复，bug修复完成需merge回develop分支，并将其删除。所以该分支属于临时性分支。
* hotfix分支，即热补丁分支。和fix分支的区别在于，该分支由master分支检出，进行线上版本的bug修复，修复完成后merge回master分支，并merge到develop分支上，merge完成后也可以将其删除，也属于临时性分支。

![分支功能](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/分支功能.png)

## 经典工作流

1. 创建项目，添加协助者，详见[Github如何增加协助者](https://jingyan.baidu.com/article/948f5924f43f47d80ff5f9f9.html)

2. 克隆项目
```bash
git clone https://github.com/pbrong/GitHubTest.git
```
![工作流1](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/工作流1.png)

3. 从master分支上检出develop分支，此时develop分支和master分支是完全一样的，我们查看文件发现没有变化，其实此时的文件就是develop分支中的文件
```bash
git checkout -b develop
```

4. 修改develop分支的文件，例如我要增加一个查询商品模块AddItem.java，模拟数次的add和commit
![工作流2](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/工作流2.png)

5. 切换到master分支
```bash
git checkout master
```
经过数次修改，确认代码无误后切换回master分支，此时的文件结构中并不含有AddItem.java，说明这数次修改都是在develop分支进行的，master分支还是我们一开始的代码没有变化
![工作流3](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/工作流3.png)

6. 分支合并
```bash
git merge --no-ff develop
```
![工作流4](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/工作流4.png)
即可看到，master分支出现了AddItem.java文件，说明分支合并成功，此时master分支的代码是经develop分支测试过的，安全可靠的
![工作流5](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-12-5-github_workflow/工作流5.png)

7. 提交master分支至版本库中

## 同步分支
克隆和某一仓库后，会出现只有master分支而没有develop分支的情况，这时只需要在master分支的基础上检出develop分支，然后请求同步即可。
```bash
git checkout -b develop
git pull origin develop
```