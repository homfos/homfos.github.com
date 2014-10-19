---
layout: default
title: 我的Blog
---

#github的第一篇
---
##前言
很久前都有在github上创建自己的博客的想法，但总由于项目上的事情太忙而作罢。最近几天项目上的事情暂告一段落，所以就顺便整理一下博客。主要是试用github的博客功能，找找自己顺手的工具，为以后的博客更新做准备。

#github page试用体会
---
##工具
- MarkDown编辑器：MarkdownPad2
- Jekyy
- Git
- prettify:代码高亮插件

---

##步骤
1. github上设置个人page，就是简单的创建一个Repository，命名按照username.github.com（如homfos.gitbub.com）的规则即可
2. 安装Jekyll，因为使用windows系统，在官网找到对应的Jekyllwindows[安装方法](http://jekyll-windows.juthilo.com/)。按照官网安装方式，部署Jekyll共分好几步，按照官网介绍一步步来就可以了，值得一提的一点是由于国情的原因Ruby默认的源很慢，而且经常连接超时报错，所以可以先把系统默认的源给删掉，添加国内淘宝的源，具体方法如下：
	- $ gem sources --remove  https://rubygems.org/
	- $ gem sources -a https://ruby.taobao.org/
	- $ gem sources -l
3. 使用Markdown。Markdown上手较容易，详见[Markdown语法介绍](http://daringfireball.net/projects/markdown/syntax#list)
4. 使用Jekyll。相对Markdown，因为Jekyll涉及的东西多一点，如（Jekylly配置、YAML、Liquid等），所以稍微复杂一点。不过Jekyll的文档还是比较齐全的，按照[使用文档](http://jekyllrb.com/docs/usage/)还是比较容易上手。
5. 使用Git进行部署。github page通过Git进行blog部署。其中_site无需纳入版本管理。github有Jekyll引擎可以自动根据上传的文件后台自动生成。每次提交完，需要等10分钟才能看到最新的blog页面。
6. 使用prettify进行代码的高亮显示。prettify是google的代码高亮显示JS模块。通过[使用手册](https://code.google.com/p/google-code-prettify/wiki/GettingStarted)可以很快上手。

---
##总结
这里只是把大致的步骤列了一下。如需详细步骤，可打开文章中的超链接。虽然东西不复杂但是也还是折腾了一两天。主要是Jekyll上手还是稍微复杂了一点。