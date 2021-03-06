---
layout: post
title: Jekyll + Github Pages = 博客
date: 2019-11-22
tags: [Writing]
comments: true
author: OriginalXY
toc: true
---

其实一开始并没有打算用jekyll来搭建，然而WordPress还要自己去找机子来搭有点麻烦（其实官方也提供了），关键是想做个整合，把知乎V2EX微博githubCSDN什么的都管起来，所以博客只是其次，主要是搬运工、个人学习和成果展示。

初期想着直接从模板上搬运（好吧其实现在这个也是搬运的...），可以参考[三分钟在GitHub上搭建个人博客](https://zhuanlan.zhihu.com/p/28321740)，里面用到的模板是[HTML5 UP](https://html5up.net/)，虽然已经放弃这个方案了但后期的很多改造还是会参考这里的模板改进。

<!-- more -->

## Github配置

先看下博客整体效果。[预览我的博客](https://originalxy.github.io/)

- Powered By Jekyll

- 文章搜索

- 自定义社交链接

- 不蒜子网站访客统计

- Google Analytics 网站分析

- Gitalk评论功能

- 自定义关于about页面

- 中文布局

- 归档与标签

- 其他功能正在规划中...
  

### 建立Git仓库

首先你要在[github](https://github.com/)上有自己博客仓库，用来生成和存放博客文章。

### 修改仓库名称

进到你自己的博客仓库，修改博客仓库名称成你自己的用户名。github page解析的时候找的是这个 username.github.io的仓库名。

此时，不出意外的话，打开域名https://username.github.io 就能看到你刚搭建的博客了。注意替换username成你自己的github用户名。

### 博客配置

博客的配置文件是仓库根目录下的_config.yml文件，直接点开它编辑。

你还需要更改以下配置：

#### 名称和描述

name和description分别是博客名称和描述，自己任意写点啥。

#### 网址配置

```
# Your website URL (e.g. http://barryclark.github.io or http://www.barryclark.co)
# Used for Sitemap.xml and your RSS feed
url: https://yourname.github.io
```

这里配置你自己的博客地址。

## 如何写博客

好了，博客有了。如何更新文章呢？

文章markdown语法，写好统一放在_post文件夹下上传，git page会自动从你的git仓库拉去解析成网页，立刻就能在你的博客网页浏览。

关于文章的**命名格式**：博客文章必须按照统一的命名格式 `yyyy-mm-dd-blogName.md` 比如我这篇博客的名字是`2019-11-22-create_blog_with_github_pages.md`

## Jekyll配置

到目前为止，我们提交的文章都是必须上传到github仓库才能预览。如果你想写完在本地浏览器看一下效果在上传也可以

### 安装 Ruby 和 DevKit

在官网下载，[点这里]( https://rubyinstaller.org/downloads/ )下载适合系统版本的 [Ruby+Devkit](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.6.5-1/rubyinstaller-devkit-2.6.5-1-x64.exe) 包。安装，弹出的窗口选3

![安装ruby](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/安装ruby.png)

`gem -v` `ruby -v` 查看得到版本号就说明成功了。

如果是在墙内，需要切换安装源到https://gems.ruby-china.com/。墙外请忽略。

`gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/` 切换安装源

`gem sources -l` 查看版本

### bundler安装

`gem install bundler` 安装bundler 

`bundle -v 查看版本
 bundle config mirror.https://rubygems.org https://gems.ruby-china.com` 切换安装源

### 安装jekyll

` gem install jekyll`

### 预览博客

` jekyll server` 输入之后打开浏览器，不出意外输入localhost:4000即可看到博客内容。

![jekyll_server安装](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/jekyll_server成功.png)

如果你没这么顺利，那以下的错误解决供参考

#### 常见错误

- 缺少某个包

![jekyll_error](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/jekyll_error.png)

如图，缺少jekyll-paginate，安装即可`gem install jekyll-paginate`若还提示缺少就装啥。

![jekyll_server_erro错误2](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/jekyll_server_erro错误2.png)

- 权限拒绝

  socket.rb:201:in `bind` :Permission denied - bind(2) for 127.0.0.1:4000 (Error:EACCES)

![jekyll_error_EASSE](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/jekyll_error_EASSE.png)

出现这个错误一般是4000端口被占用了，解决方法：

1.  netstat -ano|findstr "4000" 找到占用4000端口的进程ID

2. 查看最后一列数字就是PID=312964

   ![netstat查看](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/查看netstat.png)

3. 打开windows资源管理器，结束该进程.

   ![任务管理器](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/任务管理器.png)

4. `$ tasklist|findstr 312964`也能查看进程名，查到结束掉他同步骤3.

## 1. Gitalk功能

这个是评论功能的配置。评论功能基于gitalk，在配置文件中找到gitalk配置项目：

修改规则如下：

```yml
gitalk:
  clientID: <你的clientID>
  clientSecret: <你的clientSecret>
  repo: <你的repository名称>
  owner: <你的GitHub用户名>
```

原理是利用github的issues评论文章。其中clientID和clientSecret需要[点击这里创建](https://github.com/settings/applications/new)

![创建Gitalk鉴权](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/创建Gitalk鉴权.png)


## 2. Google统计功能

首先你要去注册一个[Google Analytics]( https://analytics.google.com/analytics/ )账号，它可以统计你博客网站的访问人数，访问来源等非常丰富的网站数据。

```
# Enter your Google Analytics web tracking code (e.g. UA-2110908-2) to activate tracking
google_analytics: UA-XXXXXXX-X
```  

## 3. 搜索文章功能

搜索功能依赖[Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search)提供支持。

### 配置search.json

[复制这份代码到你博客的根目录](https://github.com/christian-fei/Simple-Jekyll-Search/blob/master/example/search.json)

这个配置文件代表可以按博客的标题、标签、时间、分类搜索。

### 下载simple-jekyll-searchj文件

[下载这整个文件夹](https://github.com/christian-fei/Simple-Jekyll-Search/tree/master/example/js)，里面包含simple-jekyll-search.min.js和simple-jekyll-search.js两个文件，连同js文件夹放在你的根目录下面。

### 配置搜索框标签

在你想展示搜索框的页面我的是index.html，这个页面和每个人的博客模板有关，可能需要一点前端知识，添加如下的html标签。

```html
<div class="search-container">
  <input type="text" id="search-input" placeholder="search blog posts...">
  <ul id="results-container"></ul>
</div>

<!--script src="https://unpkg.com/simple-jekyll-search/dest/simple-jekyll-search.min.js"></script-->
<script src="{{ site.baseurl }}/js/simple-jekyll-search.min.js"></script>

<script>
	window.simpleJekyllSearch = new SimpleJekyllSearch({
	searchInput: document.getElementById('search-input'),
	resultsContainer: document.getElementById('results-container'),
	json: '{{ site.baseurl }}/search.json',
	searchResultTemplate: '<li><a href="{url}?query={query}" title="{desc}">{title}</a></li>',
	noResultsText: 'No results found',
	limit: 10,
	fuzzy: false,
	exclude: ['Welcome']
  })
</script>
```

其中，以下两个是二选一的，一个是用云端的js一个是用本地的js如果本地有的话。

`<script src="https://unpkg.com/simple-jekyll-search/dest/simple-jekyll-search.min.js"></script--> `

`<script src="{{ site.baseurl }}/js/simple-jekyll-search.min.js"></script>`

配置完成，打开博客，你得到这样一个搜索框。

![search_block](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/search_block.png)

### 搜索框样式

搜索框的样式是可以改变的，这里有修改HTML中CSS样式的方法，我搞后端的，前端现学现卖。

[html插入标签样式方法](https://blog.csdn.net/u014103733/article/details/72961366)


## 4. 社交链接功能

这里配置社交链接按钮，没配的不显示，可以配微博、知乎、邮箱、github等账号。其他你想加自己加上就可以。比如没有知乎链接，或者你想增加自定义的链接，都可以通过以下方法添加。以增加zhihu链接为例。

链接的图片是svg格式的知道)，大概了解一下什么是svg和viewBox

[viewBox](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute/viewBox)

> viewBox属性的值是一个包含4个参数的列表 `min-x`, `min-y`, `width` and `height`， 以空格或者逗号分隔开， 在用户空间中指定一个矩形区域映射到给定的元素,查看属性 

[深入简出 SVG 教程](https://zhuanlan.zhihu.com/p/36138381)

### 配置_config.yml

```yml
footer-links:
  weibo: yourname #请输入你的微博个性域名 https://www.weibo.com/<yourname>
  zhihu: yourname #输入你知乎主页链接上的名字 https://https://www.zhihu.com/people/<yourname>
```

### 修改svg-icons.html

因为footer.html中调用了svg-icons.html来生成社交链接。

可见是先调用了svg-icon.html显示社交链接，所以修改_include/svg-icons.html增加zhihu链接

{% highlight liquid linenos%}
{% raw %}
{% if site.footer-links.zhihu %} 
    <a href="https://zhihu.com/people/{{ site.footer-links.zhihu }}" 
    class="icon-2 zhihu" title="ZhiHu">
      <svg viewBox="0 0 600 600">
        <path d="M170.54 148.13v217.54l23.43.01 7.71 26.37 42.01-26.37h49.53V148.13H170.54zm97.
        75 193.93h-27.94l-27.9 17.51-5.08-17.47-11.9-.04V171.75h72.82v170.31zm-118.46-94.39H97.
        5c1.74-27.1 2.2-51.59 2.2-73.46h51.16s1.97-22.56-8.58-22.31h-88.5c3.49-13.12 7.87-26.66 
        13.12-40.67 0 0-24.07 0-32.27 21.57-3.39 8.9-13.21 43.14-30.7 78.12 5.89-.64 25.37-1.18 
        36.84-22.21 2.11-5.89 2.51-6.66 5.14-14.53h28.87c0 10.5-1.2 66.88-1.68 73.44H20.83c-11.
        74 0-15.56 23.62-15.56 23.62h65.58C66.45 321.1 42.83 363.12 0 396.34c20.49 5.85 40.91-.
        93 51-9.9 0 0 22.98-20.9 35.59-69.25l53.96 64.94s7.91-26.89-1.24-39.99c-7.58-8.92-28.06
        -33.06-36.79-41.81L87.9 311.95c4.36-13.98 6.99-27.55 7.87-40.67h61.65s-.09-23.62-7.59-23
        .62v.01zm412.02-1.6c20.83-25.64 44.98-58.57 44.98-58.57s-18.65-14.8-27.38-4.06c-6 8.15-
        36.83 48.2-36.83 48.2l19.23 14.43zm-150.09-59.09c-9.01-8.25-25.91 2.13-25.91 2.13s39.52 
        55.04 41.12 57.45l19.46-13.73s-25.67-37.61-34.66-45.86h-.01zM640 258.35c-19.78 0-130.91.
        93-131.06.93v-101c4.81 0 12.42-.4 22.85-1.2 40.88-2.41 70.13-4 87.77-4.81 0 0 12.22-27.
        19-.59-33.44-3.07-1.18-23.17 4.58-23.17 4.58s-165.22 16.49-232.36 18.05c1.6 8.82 7.62 17.
        08 15.78 19.55 13.31 3.48 22.69 1.7 49.15.89 24.83-1.6 43.68-2.43 56.51-2.43v99.81H351.
        41s2.82 22.31 25.51 22.85h107.94v70.92c0 13.97-11.19 21.99-24.48 21.12-14.08.11-26.08-1.
        15-41.69-1.81 1.99 3.97 6.33 14.39 19.31 21.84 9.88 4.81 16.17 6.57 26.02 6.57 29.56 0 45.
        67-17.28 44.89-45.31v-73.32h122.36c9.68 0 8.7-23.78 8.7-23.78l.03-.01z"/>
      </svg><!--[if lt IE 9]><em>YouTube</em><![endif]-->
    </a>
  </li>
{% endif %}
{% endraw %}
{% endhighlight %}


上面配置内容应该都能理解，`viewBox` 指定图片大小。

主要是`path d=` 内容的获取，这里其实是指定svg图片的内容，我们可以从 [这里](https://raw.githubusercontent.com/FortAwesome/Font-Awesome/master/svgs/brands/)获取到大部分svg素材，比如知乎的svg[在这](https://github.com/FortAwesome/Font-Awesome/blob/master/svgs/brands/zhihu.svg)，点`raw` 按钮查看源文件，复制`path d=`后面的内容到上面的配置即可。

![zhihuSvg](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/知乎svg.png)



## 5. 网站计数功能

网站统计[由不蒜子](http://busuanzi.ibruce.info/)提供支持，可以统计网站当前访问次数和人数。配置也非常简单[官方指引](http://ibruce.info/2015/04/04/busuanzi/#more)在这里。但现在不允许注册初始化，因此统计数据仅供参考，正在寻找其他统计工具。

### 修改页面html

想让统计显示在哪个页面，需要修改那个页面的html，增加如下内容：

```html
<!--不蒜子网站访客统计-->
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js">
</script>
<!-- pv的方式，单个用户连续点击n篇文章，记录n次访问量 -->
<div align="center">
	<span id="busuanzi_container_site_pv" style="font-family:Consolas;color:Silver;font-size:12px;">
		View:<span id="busuanzi_value_site_pv" style="font-family:Consolas;color:Silver;font-size:12px;"></span>
	</span>
	<!-- uv的方式，单个用户连续点击n篇文章，只记录1次访客数 -->
	<span id="busuanzi_container_site_uv" style="font-family:Consolas;color:Silver;font-size:12px;">
		User:<span id="busuanzi_value_site_uv" style="font-family:Consolas;color:Silver;font-size:12px;"></span>
	</span>
</div>
```

### style标签说明

可以通过style标签改变字体颜色与大小。具体参考:[html颜色表](http://xh.5156edu.com/page/z1015m9220j18754.html)和[html style属性](https://www.geeksforgeeks.org/html-style-attribute/)

eg.  `style="font-family:arial;color:Gainsboro;font-size:10px; text-align:right;width:200px;background-color:gray;`

## 6. 滚动条功能

默认肯定是overflow: auto，但想尝试将目录的滚动条隐藏起来保持美观（文章肯定要保留滚动条...），网上找到三种办法，[效果参考](http://caibaojian.com/demo/2018/3/scroll.html)。

### 方法一：计算滚动条宽度并隐藏

滚动条通过定位把它隐藏起来，这个代码巧妙的向右移动了17个像素，刚好等于滚动条的宽度。这个值是手动调试得来的。在chrome和IE没发现问题。[效果参考](http://caibaojian.com/demo/2018/3/scroll2.html)。

```html
<div class="outer-container">
    <div class="inner-container">
    	......
    </div>
</div>
```

```css
.outer-container{
	width: 360px;
	height: 200px;
	position: relative;
	overflow: hidden;
}
.inner-container{
	position: absolute;
	left: 0;
	top: 0;
	right: -17px;
	bottom: 0;
	overflow-x: hidden;
	overflow-y: scroll;
}
```
### 方法二：使用三个容器包围

该代码最早是在[Microsoft博客](https://docs.microsoft.com/zh-cn/archive/blogs/kurlak/hiding-vertical-scrollbars-with-pure-css-in-chrome-ie-6-firefox-opera-and-safari)上看到的，跟上面的思路差不多，只不过里面又加多了一个盒子，将内容限制在盒子里面了。这样子就看不到滚动条同时也可以滚动。[效果参考](http://caibaojian.com/demo/2018/3/scroll3.html)

```html
 <div class="outer-container">
     <div class="inner-container">
        <div class="content">
            ......
        </div>
     </div>
 </div>
```

```css
.element, .outer-container {
  width: 200px;
  height: 200px;
}

.outer-container {
  border: 5px solid purple;
  position: relative;
  overflow: hidden;
}

.inner-container {
  position: absolute;
  left: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}

.inner-container::-webkit-scrollbar {
  display: none;
}
```
### 方法三：css隐藏滚动条

通过CSS隐藏滚动条的方法，不过这个方法不兼容IE和Firefox，做移动端的可以使用。那就是自定义滚动条的伪对象选择器::-webkit-scrollbar，关于webkit-scrollbar可以[参考文章](http://caibaojian.com/webkit-scrollbar.html)，[效果参考](http://caibaojian.com/demo/2018/3/scroll4.html)

```css
.element {
  overflow-y: scroll;
}

// Chrome和Safari
.element::-webkit-scrollbar { 
  width: 0 !important 
}

// IE 10+
.element { 
  -ms-overflow-style: none; 
}

// Firefox
.element { 
  overflow: -moz-scrollbars-none; 
}
```

## 7. 如何传图片

写markdown最头疼的就是图片的插入了，推荐用[PicGo](https://picgo.github.io/PicGo-Doc/zh/guide/)一键上传得到链接，直接可以插入markdown。

PicGo支持图片上传github、SM.MS图床、阿里云、腾讯云等主流图床或云端。直接拖图片，上传云端、得到链接一步搞定，方便快捷。

![PicGo](https://cdn.jsdelivr.net/gh/OriginalXY/originalxy.github.io/images/2019-11-22-blog_with_github_pages/PicGo.png)

## 8. 字数统计与阅读时间

字数统计有两种，官方给的是英文的字数统计，网友提供的字数统计只有中文，中英文还不知道怎么合并，要对字符的属性来做区分判断了，参考[Jekyll 中如何做中文字数统计](http://taoalpha.github.io/blog/2015/05/21/tech-jekyll-count-of-chinese-characters/)。

### 英文字数统计

详见[Jekyllcn官方统计字数](http://jekyllcn.com/docs/templates/)

{% highlight liquid linenos%}
{% raw %}
{{ page.content | number_of_words }}
{% endraw %}
{% endhighlight %}
  
### 中文字数统计

研究半天发现是信息熵的问题，其实有人已经在jekyll的issue中问过类似的问题[Jekyll的中文切分问题](https://github.com/jekyll/jekyll/issues/1921)。语法规则的问题可以浏览[liquid官方API文档](https://liquid.bootcss.com/)

{% highlight liquid linenos %}
{% raw %}
共 {{ page.content | strip_html | strip_newlines | remove: " " | size }} 字 <b>/</b> 阅读全文约需{{ 
page.content | strip_html | strip_newlines | remove: " " | size | divided_by: 350 | round }} 分钟
{% endraw %}
{% endhighlight %}

## 其他功能

[小功能](https://blog.csdn.net/ds19991999/article/details/81293467)

[好用的github插件](https://blog.csdn.net/u012702547/article/details/100533763)

## 网站结构

根目录的index.html生成blog首页

_include/footer.html生成侧边栏

_include/svg-icons.html生成社交头像的链接

## 参考
- [Jekyll使用教程笔记](https://juejin.im/post/5b235a1cf265da597568a97d)
- [一篇文章了解Liquid Template Engine 模版引擎 (Jekyll模版)](https://www.jianshu.com/p/5c6d68bcd836)
- [搭建Hexo博客进阶篇---主题自定义（三）](https://www.jianshu.com/p/4b9ee8fec3a3)