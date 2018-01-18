---
title: js_基础
date: 2018-01-17 16:25:55
tags:
- javascript
categories:
- js
---
# 什么是 JavaScript？

js 是允许你在网页中实现复杂事情的一门语言，不只是显示静态信息，还显示及时更新的信息、交互式的地图、2D/3D动画、播放音视频等。

# js 可以做什么？

- 变量中储存有用的值

- 对一段文本进行操作

- 运行代码以响应网页中发生的特定事件

- 以及更多！

<!--more-->

更令人兴奋的是建立在 Javascript 语言核心之上的功能，即`应用程序编程接口(APIs)`。

APIs 是一套建立好的代码组件，可以让开发者实现除此之外很难甚至不可能实现的功能。

通常分为两大类：`浏览器 APIs(Browser APIs)` 和 `第三方 APIs(3rd party APIs)`。

## 浏览器 APIs

已经安装在你的浏览器中，且能从周围的计算机环境中揭露数据，做各种复杂有用的事情。

- `文档对象模型API[DOM(Document Object Model)API]`: 允许你操作 HTML和CSS，创建和修改 HTML，动态的应用样式到你的页面等等。

- `地理定位API[Geolocation API]`: 获取地理信息。

- `画布[Canvas]`和`WebGL APIs`: 可以创建生动的2D和3D效果。

- `音像和影像 APIs[Audio and Video APIs]`: 可以运行多媒体，比如在网页中播放视频和音频，或从网页摄像头中获取录像等。

## 第三方 APIs

默认是没有安装在浏览器中的，你需要从网络上的某些地方获取它们的代码和信息。比如 `推特API`、`谷歌地图API`等。

# js 在你的页面上做什么？

当你在浏览器读取一个页面，你在一个运行环境（浏览器）中运行你的代码，就像一个工厂，获取原材料（代码），然后生产一个产品（网页）。

在 HTML 和 CSS 已经组装成一个页面后，浏览器的 js 引擎开启执行 js 代码。这就保证了 js 开始执行的时候，页面的结构和样式已经在该出现的地方了。

## js 运行顺序

js 通常会按照从上到下的顺序执行代码。

## 变量声明提升

声明变量有三种方式：

- var: 在函数之外声明的变量是全局变量，在函数内声明的变量是局部变量。

- let: 声明带有作用域的变量。

- const: 声明只读的常量。

var 声明的变量会被提升到当前作用域的顶部，let、const 声明的变量不会被提升。

```
	console.log(a);  // undefined
	console.log(b);  // Uncaught ReferenceError: b is not defined
	console.log(c);  // Uncaught ReferenceError: c is not defined
	var a = 1;
	let b = 2;
	const c = 3;
```

## 函数提升

定义函数有两种方法，function 和 函数表达式，function 声明的函数会被提升，函数表达式不会。

# 数据类型

## undefined

变量未定义时的属性。

## null

空对象指针。

## String

### 把字符串看作对象

在 js 中，一切东西都可以看作对象，字符串自然也能看作对象。

- length: 获取字符串的长度，返回一个数字
	
	```
		str.length
	```

- indexOf(): 在某个字符串中查找某个字符串，找到了返回索引，未找到则返回-1。

	```
		var str1 = 'Hello World!';
		str1.indexOf('llo');  // 2
		str1.indexOf('asdasd');  // -1
	```

- slice(a, b): 截取 [a, b) 范围内的字符串，返回截取的字符串，不会改变原字符串的值。

如果不传第二个参数，则截取a及后面所有的字符。

	```
		var str = 'Hello World';
		str.slice(2, 7);  // llo W
		str.slice(2);     // llo World!
	```

- toLowerCase(): 将字符串转换成小写，返回转换后的字符串，不会改变原字符串的值。

	```
		var str = 'Hello World';
		str.toLowerCase();  // hello world!
	```

- toUpperCase(): 将字符串转换成大写，返回转换后的字符串，不会改变原字符串的值。

	```
		var str = 'Hello World';
		str.toUpperCase();  // HELLO WORLD!
	```

- replace(): 替换字符串中的值，可以传入正则表达式，不会改变原字符串的值。

	```
		var str = 'Hello World!';
		str.replace('World', 'Hello');  // Hello Hello!
	```

- split(): 根据某个指定的字符将字符串转换成数组。

```
	var str = 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle';
	str.split(',');    // ["Manchester", "London", "Liverpool", "Birmingham", "Leeds", "Carlisle"]
```

## Number

### 递增和递减操作符

- 只能作用于变量上，如 `number++`，不能直接作用于数字上，`3++` 是错误的。

- ++a：前置型，a的值先加1，在参与计算，a++: 后置型，a先参与计算，在加1

	```
		var a = 1, b = 2;
		++a + b++;  // 4
		a++ + b++;  // 5
		++a + ++b;  // 9
	```

## Boolean

true、false

## Array

- join(): 数组转换成字符串，用指定的字符分隔。

```
	var arr = ["Manchester", "London", "Liverpool", "Birmingham", "Leeds", "Carlisle"];
	arr.join(',');    // 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle'
```

- push(): 在数组的末尾追加一项，返回新数组的长度。

- pop(): 删除数组的最后一项，并返回删除的项。

- unshift(): 在数组的开头添加一项，返回新数组的长度。

- shift(): 删除数组的第一项，并返回删除的项。

## Object

## 数据类型的相互转换

### 字符串转数字

- parseInt(): 返回整数

- parseFloat(): 返回小数


# 函数

## 递归

一个函数可以指向并调用自身。

## 闭包

## arguments 对象

存储函数实参的类数组。
