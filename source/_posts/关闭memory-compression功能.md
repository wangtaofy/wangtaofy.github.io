---
title: 关闭memory compression功能
date: 2018-03-14 10:01:18
tags: 
categories: 
- 其他
---

memory compression 是win10的内存管理机制，主要是压缩不长访问的内存页面，来减少对硬盘的读取和写入，但是在装有SSD的电脑上体验很差，会占用大量内存，据说跟HDD配合会比较好。

<!--more-->

可以用下面的方式来禁用它：

开始菜单 -> windows powershell(管理员身份运行) -> 输入命令 `Disable-MMAgent -mc`回车 -> 重启电脑

这样会禁用内存压缩功能