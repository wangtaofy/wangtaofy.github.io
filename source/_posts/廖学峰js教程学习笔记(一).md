---
title: 廖学峰js教程学习笔记(一)
date: 2018-03-12 16:00:01
tags: 
- js
categories: 
- 廖学峰js教程学习笔记
---

# 基础知识

## 语法

js 的语法跟 java 的类似，每一条语句以`;`结尾，语句块用`{...}`。如果不写分号，浏览器中执行js代码的引擎会自动在语句的尾部加分号。但有时候js引擎在语句后加的封号会改变语句的语义顺序，所以我们要尽量在每一条语句后加分号，避免发生错误。

<!--more-->

js是严格区分大小写的，大小写写错会发生错误。

js代码注释有行注释和块注释：

- 行注释：以`//`开头，注释一行的内容

  ```
  // 这是一个行注释
  ```

- 块注释：用 `/*...*/`包裹内容

  ```
  /*这是一个块注释
    这也是块注释
  */
  ```

## 数据类型和变量

js 的数据类型有5种基本数据类型：Number、String、Boolean、undefined、null，有两种复杂数据类型：Array、Object。

### Number

js 中没有区分整数和浮点数，统一都是Number类型

```
1 // 整数
1.3 // 浮点数
1.2345e3 // 科学记数法 1234.5
-99 // 负数
NaN // 无法得出计算结果时会返回NaN
Infinity // 表示无限大，当数值超出Number所能表示的最大值时，就会返回Infinity
```

NaN这个值跟所有值都不相等，包括它自己

```
NaN === NaN  // false
```

NaN只能用isNaN()来判断

```
isNaN(NaN)  // true
```

Number 所能表示的最大值为 Number.MAX_VALUE，最小值为 Number.MIN_VALUE

Number 可以直接做四则运算，规则和数学一样。

### 字符串 String

字符串是以''或""括起来的文本，如'abc'，"adas"。

### 布尔值 Boolean

布尔值只有两个值：true、false。

```
true  // true
false  // false
2 > 1  // true
2 >= 3  // false
```

&&运算符：两个值都为true时结果才为true。

```
true && true  // true
true && false  // false
false && true && false  // false
```

||运算符：有一个值是true，则结果为true

```
false || false  // false
true || false  // false
false || true || false  // true
```

!运算符：把true变成false，把false变成true

```
!true  // false
!false  // true
!(2 > 5)  // true
```

比较运算符：当我们对值做比较时，会得到一个布尔值。

```
2 > 5  // false
5 >= 2  // true
7 === 7  // true
```

js 在设计时，有两种等号运算符：

- `==`：会先把值转换数据类型，在进行比较

- `===`：不把值转换数据类型，直接进行比较，如果数据类型不一样，会返回false

### null和undefined

null 表示一个'空'的值，它和0、''不一样，0是一个数值，''表示长度为0的字符串

undefined 表示值未定义。

## 数组 Array

数组表示一组数据的集合，数据的每一项称为元素，数据项的值可以是任意的数据类型。

```
[1, 2, 'Hello', null, true]
```

数组的元素可以通过它的索引来访问，索引从0开始：

```
var arr = [1, 2, 'Hello', null, true];
arr[0] = 1;
arr[2] = 'Hello';
arr[6] = undefined;  // 没有该索引的值
```

## 对象 Object

对象是一组由键值对组成的无序集合，键是字符串，值可以是任意数据类型。

```
var obj = {
  name: 'Bob',
  age: 20,
  tags: ['js', 'web', 'mobile'],
  city: 'Beijing',
  hasCar: true,
  zipcode: null
};
```

可以用 `对象.键` 的形式来取到对应的值

```
obj.name;  // Bob
```

也可以用 `对象[键]` 的形式取到对应的值

```
obj['age'];  // 20
```

### 变量

js 的变量名可以是 `数字、字母、$、_` 组成，但不能以数字开头。

声明变量有三种方式：var、let、const，后两种是ES6新增的声明变量的关键字。

let 声明的变量具有局部作用域，即它的作用域在{...}语句块中。

const 声明的变量是常量，声明后不可更改，且const声明变量的时候必须给它赋值。和 let 一样，都有局部作用域。

### strict 模式

变量如果不用var声明的话，会自动变成全局变量，如果一个js文件中有多个地方使用了未经var声明的变量，那这些变量之间就会相互影响。

js 推出了strict严格模式，在js文件的顶部写上`'use strict;'`字符串，就能启用严格模式，在该模式下，使用未声明的变量会报错。


## 字符串

js 字符串指的是 '' 或 "" 括起来的内容。

字符串的很多字符都需要`\`来转义，如\n表示换行，\t表示指标符，'\'本身也需要转义，即'\\'。

```
'I\'m \"OK\"!'
```

### 多行字符串

ES6定义了一种写多行字符串的方式，用反引号`...`。

```
`多行
字符串
测试`;
```

### 模板字符串

可以用+号来连接字符串。

```
var a = 'Hello';
var b = '小明';
a + ', ' + b;  // Hello, 小明
```

但是如果变量太多，就会很麻烦，。

ES6定义了新的连接字符串的方式，即模板字符串。

```
var a = 'Hello';
var b = '小明';
`${a}, ${b}`;  // Hello, 小明
```

### 操作字符串

获取字符串的长度length:

```
var str = 'Hello, world!';
str.length;  // 13
```

根据索引获取字符串的某个字符：

```
str[0];  // H
str[5];  // ,
```

字符串是不可变的，对字符串的某个索引赋值，字符串不会有变化。

### toUpperCase()/toLowerCase()

把字符串所有字母变成大写/小写字母，并返回新的字符串。

```
var str = 'asdDFE';
str.toUpperCase();  // ASDDFE
str.toLowerCase();  // asddfe
```

### indexOf()

在字符串中查找指定的字符，找到就返回该字符的索引，否则返回-1.

```
var str = 'Hello, world!';
str.indexOf('llo');  // 2
```

### substring(a, b)

截取[a, b)范围内的字符串

```
var str = 'Hello, world!';
str.substring(3, 7);  // lo, w
str.substring(3);  // lo, world!
str.substring(3, 23);  // lo, world!
str.substring(20, 23);  // ''
```