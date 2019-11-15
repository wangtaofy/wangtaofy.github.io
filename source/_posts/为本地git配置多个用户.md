---
title: 为本地git配置多个用户
date: 2019-11-15 09:02:22
tags:
- git
categories:
- git
---
# 为本地git配置多个用户

假如我有两个账户，github和gitlab，一个自己用，一个工作用，那就不能全局设置用户，而是要在为项目单独配置

首先，清除全局设置的用户，如果你没有全局设置过的话，可以跳过

> git config --global --unset user.name 
> git config --global --unset user.email

然后

> cd ~/.ssh

<!--more-->

生成ssh key

> ssh-keygen -t rsa -C "your_emailA"

enter后，会让你输入生成的文件名，比如 id_rsa_home_github

然后enter，会让你输入密码，注意这个密码是以后push的时候需要输入的密码，可以不填，直接enter，这样push时就不需要输密码

完成之后，.ssh目录会生成 id_rsa_github 和 id_rsa_github.pub两个文件，将 .pub 文件打开，复制里面的内容，去github添加一个ssk key，把复制的内容粘贴进去

然后为gitlab创建ssh key，重复上面的步骤

最后来配置confg，在.ssh/config，没有这个文件就新建一个

> # github
> Host home_github
> HostName github.com
> User git
> IdentityFile ~/.ssh/id_rsa_home_github
> 
> # gitlab
> Host work_gitlab
> HostName gitlab的域名
> User git
> IdentityFile ~/.ssh/id_rsa_gitlab

添加文件到ssh

> ssh-agent bash
> ssh-add id_ras_home_github
> ssh-add id_ras_work_gitlab

测试一下能不能连接成功

> ssh -vT git@home_github
> ssh -vT git@work_gitlab
