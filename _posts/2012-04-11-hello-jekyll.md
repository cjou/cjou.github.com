---
layout: post
permalink: /techlog/hello-jekyll/
title: "Hello Jekyll"
tagline: 入门及安装
description: "ff"
category: "TechLog"
tags: ["Jekyll"]

---
{% include JB/setup %}

[Jekyll](http://jekyllrb.com) 是一款使用 Ruby 开发的轻量级 Blog、静态网站发布程序 ( Generator )。跟 WordPress 等动态程序不同，它是根据一个模板目录以及约定的结构作为站点构成的基础，从而生成一个完整的静态站点。由于生成的是全静态站点，你可以将站点部署到 Apache 等任何支持静态页面的Web服务器上。

Jekyll 同时也是 [ Github Pages ](http://pages.github.com/)的后台引擎，因为你也以将它托管到 Github Pages 上，完全免费并且支持自定义域名。

Jekyll 的特性如下：

* 支持 [Markdown](http://daringfireball.net/projects/markdown/)
* 全静态站点
* 支持扩展及插件 ( 评论，Analytics 等 )
* 主题更换



###安装

Jekyll 的部署和安装并没有想像中的简单，但相于WordPress等来说也不会复杂太多。

首先确保已经安装了 Ruby。 OSX 系统下已经默认安装 Ruby，因此只需更新一下 RubyGems 

<pre class="prettyprint" id="bash">
<code>$ sudo gem update --system</code>
</pre>
	
官方推荐以 Gem 方式安装 Jekyll

<pre class="prettyprint" id="bash">
<code>$ sudo gem install jekyll</code>
</pre>	

Jekyll 默认的 Maruku 对中文支持不好，可以选择安装 rdiscount 

	$ sudo gem install rdiscount

安装 pygments，用于语法高亮

	$ sudo easy_install pygments

### 创建 Blog

创建一个 Jekyll 博客最简单的方法就是从 Github 上克隆一个 [Jekyll Bootstrap](http://jekyllbootstrap.com/) 分支。

首先从 Github 上创建一仓库 ( Repository )，名为 XXX.github.com
( XXX 这里替换成你的 Github 用户名 )，然后用 Git 克隆一个分支到本地机器。
<pre class="prettyprint" id="bash">
$ git clone https://github.com/plusjade/jekyll-bootstrap.git XXX.github.com
$ cd XXX.github.com
$ git remote set-url origin git@github.com:XXX/XXX.github.com.git
$ git push origin master
</pre>

### 运行 

以上步骤完成后就可以在本地上运行 Jekyll 看看实际效果了。

<pre class="prettyprint" id="bash">
$ cd XXX.github.com
$ jekyll --server
</pre>

启动成功后在本地浏览器输入 http://localhost:4000/ 访问。

### 部署

Github Pages 是 Github 免费的项目主页、博客托管服务，并且支持自定义域名，唯一需要要做的就是 Push 本地代码到 Github

<pre class="prettyprint" id="bash">
git commit -a  -m "commit"
git push
</pre>

提交成功大约几分钟后就可以通过 http://XXX.github.com 来访问你的站点。

### 自定义域名

Github Pages 支持 [Custom Domains](http://help.github.com/pages/#custom_domains)。只需在 XXX.github.com 项目根目录下建立文件 CNAME，文件内容为需要绑定的域名 （ 比如 blog.xxx.com ），并提交到 Github 上。然后添加一个该域名的 CNAME 并指向 XXX.github.com。而顶级域名的话添加A记录解析到 204.232.175.78 便可以了。

成功后访问 http://XXX.github.com 就会自动跳转到自定义域名。




 

