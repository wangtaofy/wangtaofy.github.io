---
title: jQuery 基础知识
date: 2017-09-25 13:16:56
tags:
- jQuery
- javascript
categories:
- jQuery
---

# jQuery 基础知识

## 方法

<!--more-->

* $.error(): 当元素发生错误时，触发error事件

* $.extend(): jquery的扩展方法，可以将多个对象合并为一个对象，后面对象的属性跟前面对象相同是，会覆盖前面的属性

  $.extend(dest, src, src, ...): 将src对象合并到dest中

  $.extend(src): 将src合并到jquery全局对象中，即静态方法

* $.fn.func = function() {}: 添加实例方法

* $().data(name, value): 向选中的元素中添加数据，name: 添加的数据的名字 value: 数据的值

  $().data(name): 从选中的元素中获取名字为name的数据

  $().data(): 从选中的元素中以对象的形式返回所有存储的数据

* $().text(): 返回被选元素的文本内容

  $().text(value): 设置元素的文本内容

* $().unbind(): 移除被选元素的事件处理程序

  $().bind(): 添加事件处理程序
