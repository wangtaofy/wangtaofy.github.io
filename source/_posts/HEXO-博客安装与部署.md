---
title: HEXO 博客安装与部署
date: 2019-11-13 19:04:47
tags:
- 博客
- hexo
categories:
- 搭建个人博客系列
---
# HEXO 博客安装与部署

首先需要安装 node、npm，建议用 nvm 来安装 node

安装完成后执行下列命令安装 hexo

> $ npm install hexo-cli -g

在本地新建存放博客文件的文件夹：hexo文件夹，文件夹的路径中尽量不要有中文。

进入该文件夹，右键，Git Bash，执行以下命令，HEXO 会自动下载搭建网站所需的所有文件

> $ hexo init

<!--more-->

安装依赖包

> $ npm install

执行以下命令

> hexo g
> hexo s

就可以在本地浏览生成的博客了。

接下来将博客文件放到 github 上

新建一个仓库，仓库名为 youname.github.io

ps: youname 必须是你的 github 的用户名

编辑 hexo 文件夹下的 _config.yml, 在该文件最下方添加如下配置：

```
deploy:
  type: git
  repository: https://github.com/github用户名/仓库名字.git
  branch: master
```

ps: hexo 配置文件中':'后面必须有一个空格

配置好后保存，执行以下命令部署到 github

> $ hexo g
> $ hexo d

如果出现以下错误

> ERROR Deployer not found : git

执行以下命令

> $ npm install hexo-deployer-git --save

发布成功后在浏览器中访问你的仓库地址就可以看到博客了，第一次访问可能访问不了，需要等几分钟在访问

# hexo 常用命令

1.$ hexo g #完整命令为 hexo generote, 用于生成静态文件

2.$ hexo s #完整命令为 hexo server, 用于启动服务器，主要用于本地浏览,后面加上 --debug 为调试模式

  $ hexo s -p 5000 修改默认端口

3.$ hexo d #完整命令为 hexo deploy, 用于将本地文件发布到github上

4.$ hexo n title #完整命令为 hexo new, 用于新建一篇文章

5.$ hexo new page #用于生成一个页面

6.$ hexo clean #清除缓存

ps: 顺序 new/修改文章 -> clean -> g -> d
