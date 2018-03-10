---
title: learn-全选/全不选
date: 2018-03-09 16:11:28
tags: 
- js
categories: 
- learn-day
---

- 效果预览：<a href="https://wangtaofy.github.io/learn-day/%E5%85%A8%E9%80%89-%E5%85%A8%E4%B8%8D%E9%80%89/index.html">DEMO</a>

- 代码：<a href="https://github.com/wangtaofy/learn-day/blob/master/%E5%85%A8%E9%80%89-%E5%85%A8%E4%B8%8D%E9%80%89/index.html">github</a>

## 介绍

这是一个简单的 `全选/全不选` 的一个demo，功能很简单，全部使用原生js写的，只是记录一下日常学习的成果，以后还会添加新的功能。

<!--more-->

## 功能

- 全选/全不选

- 反选

## 实现原理

定义了一个存储选项列表checked的值的数组checkeds，根据checkeds的值来渲染选项列表。

每次操作都先更新checkeds的值
