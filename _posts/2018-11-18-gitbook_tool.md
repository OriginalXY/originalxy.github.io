---
layout: post
title: "Gitbook文章编辑工具"
date:   2018-11-18
tags: [Writing]
comments: true
author: OriginalXY
toc: true
---

什么是Gitbook? 简单说就是可以把用md写的多个文档组织成**书**发布，md你可以放在github管理，配置gitbook关联github可以实现实时commit的预览生成。也可本地预览，甚至生成各种格式文档输出的强大工具。

<!-- more -->

## 安装Gitbook
* 安装nodejs可以去[官网](http://nodejs.cn/download/)下载对应版本  
*  安装gitbook，打开win cmd输入npm install gitbook-cli -g   
> 常用命令：  
> **gitbook -V 查看版本**    
> **gitbook serve 生成网页localhost:4000预览** - 命令输入要进到SUMMARY.md所在目录![gitbook_serve](https://originalxy.github.io/images/2018-11-18-gitbook_tool/gitbook_serve.png)    
> gitbook init //初始化目录文件   
> gitbook help //列出gitbook所有的命令   
> gitbook --help //输出gitbook-cli的帮助信息   
> gitbook build //生成静态网页   
> gitbook serve //生成静态网页并运行服务器  
> gitbook build --gitbook=2.0.1 //生成时指定gitbook的版本, 本地没有会先下载  
> gitbook ls //列出本地所有的gitbook版本  
> gitbook ls-remote //列出远程可用的gitbook版本  
> gitbook fetch 标签/版本号 //安装对应的gitbook版本  
> gitbook update //更新到gitbook的最新版本  
> gitbook uninstall 2.0.1 //卸载对应的gitbook版本  
> gitbook build --log=debug //指定log的级别  
> gitbook builid --debug //输出错误信息  

## 转换Markdown文件生成PDF

### 安装Calibre 
* 电子书生成下载依赖calibre否则会报错，建议先安装，[下载地址](https://calibre-ebook.com/download)
* 配置calibre环境变量，我的目录是C:\Program Files\Calibre2

  ![环境变量设置](https://originalxy.github.io/images/2018-11-18-gitbook_tool/环境变量设置.png)

### 生成PDF

打开win cmd命令行，到SUMMARY.md所在目录执行 **gitbook pdf 生成pdf**    
> 转换PDF失败原因：
1. 没有安装calibre
2. 安装calibre之后需要设置环境变量C:\Program Files\Calibre2   

## Gitbook关联github

Gitbook上左上角为个人仓库，不能参与协同编辑，左中为组织空间可以协同编辑，右边是项目。进入个人仓库在左侧栏第六个图标中勾选Github关联。

### 发布到Github Pages
### GitHub Pages 站点的类型
有三种类型的 GitHub Pages 站点：项目、用户和组织。 项目站点连接到 GitHub 上托管的特定项目，例如 JavaScript 库或配方集合。 用户和组织站点连接到特定的 GitHub 帐户。

用户和组织站点始终从名为 user.github.io 或 organization.github.io 的仓库发布。 除非您使用自定义域，否则用户和组织站点位于 http(s)://username.github.io 或 http(s)://organization.github.io。

项目站点的源文件与其项目存储在同一个仓库中。 除非您使用自定义域，否则项目站点位于 http(s)://user.github.io/repository 或 http(s)://organization.github.io/repository。
[更多](https://help.github.com/cn/github/working-with-github-pages/about-github-pages)

- master, 保存书籍的源码
- gh-pages, 保存书籍编译后的 HTML 文件   

**步骤：**

- `gitbook build` 将书籍内容输出到默认目录，也就是当前目录下的 _book 目录

  ![gitbook_pdf](https://originalxy.github.io/images/2018-11-18-gitbook_tool//gitbook_pdf.png)

- 创建gh-pages分支，并且删除不需要的文件,仅保留git目录和 _book目录
> $ git checkout --orphan gh-pages   
$ git rm --cached -r .  
$ git clean -df  
$ rm -rf *~`
- 然后，加入 _book 下的内容到分支中：
> $ cp -r _book/* .  
$ git add .  
$ git commit -m "Publish book"  
- 将编译好的书籍内容上传到 GitHub 项目的 远程gh-pages 分支了
> $git push -u origin gh-pages


### 参考

- [发布到Github Pages](http://www.chengweiyang.cn/gitbook/github-pages/README.html)
- [详细教程](https://jackchan1999.github.io/2017/05/01/gitbook/GitBook%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B/)   
- [官方指引-integrations-Github](https://docs.gitbook.com/integrations/github)   
- [Github的GitBook项目](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)  
- [Github Pages中文帮助](https://help.github.com/cn/github/working-with-github-pages/about-github-pages)