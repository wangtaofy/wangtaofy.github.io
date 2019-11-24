---
title: 本地git有github、gitlab等多个账号，hexo推送到github
date: 2019-11-19 23:43:22
tags:
- 博客
- hexo
categories:
- 搭建个人博客系列
---

# 本地git有github、gitlab等多个账号，hexo推送到github

hexo安装目录 -> _config.yml，添加

```
deploy:
  type: git
  repository: 
    github: 项目地址
```

ps: ':'后面要有一个空格

hexo安装目录 -> .deploy_get -> .git -> config文件

添加以下内容

```
[user]
email = 邮箱
name = 用户名
```
