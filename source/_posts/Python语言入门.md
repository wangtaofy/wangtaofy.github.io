---
title: Python语言入门（Python3）
date: 2018-01-18 21:51:50
tags: 
- python
categories: 
- python
---

# 运算符

- / : 浮点数元算符

- // : 整数运算符

- ** : 平方运算符

# 语句

- =: 赋值

- print: 输出信息

- return: 函数中返回值

- import: 引入模块

<!--more-->

# 控制结构

## 选择/分支结构

```
  if condition:
    if 语句块
  elif condition:
    elif 语句块
  else:
    else 语句块
```

## 循环结构

- for 语句：循环次数已知

  range(a, b): a <= i < b

  ```
    for i in range(a, b):
      for 语句块
  ```

- while 语句：循环次数未知

  只要表达式为真，则不断执行语句

  ```
    while running:
      while 语句块
  ```

  continue: 结束本次循环，进入下一次循环

  break: 跳出循环

# 引入类库

import 类库名

例子：

引入随机数类库 `import random`

# #coding=utf-8

如果在 .py 文件中有中文，要在文件第一行写上这行代码。

# 函数

- raw_input()：读取控制台的输入与用户交互。
  
- int()：将一个数字或base类型的字符串转化为整数。
  
- format()：格式化字符串

  1、位置参数

  位置参数不受顺序约束，可以为 {}

  ```
    >>> print 'My name is {}, age {}'.format('hoho', 23)
    My name is hoho, age 23
  ```
  参数索引从0开始

  ```
    >>> print 'My name is {0}, age {1}'.format('hoho', 24)
    My name is hoho, age 24
    >>> print 'My name is {0}, age {1}, name {0}'.format('hoho', 25)
    My name is hoho, age 25, name hoho
  ```

  可以传参数列表数组: *li

  ```
    >>> li = ['hoho', 23]
    >>> print 'My name is {}, age {}'.format(*li)
    My name is hoho, age 23
  ```

  2、关键字参数

  关键字参数值要对应

  ```
    >>> print 'My name is {name}, age {age}'.format(name='hoho', age=23)
    My name is hoho, age 23
  ```

  可以传入对象: **hash

  ```
    >>> hash = {'name': 'hoho', 'age': 23}
    >>> print 'My name is {name}, age {age}'.format(**hash)
    My name is hoho, age 23
  ```

- type()：查看变量的类型

```
  >>> a = 5
  >>> type(a)
  int
```

- len()：返回字符串的长度

# 数据类型

## 整数型(Int)

- 长度无限制

- 可以用十进制表示，也可以用八进制(前缀0)和十六进制(前缀0x)表示

  ```
    >>> 077
    63
    >>> 0xF5
    245
  ```

- 两个整型进行除法运算，结果仍是整型

  ```
    >>> a = 17
    >>> b = 5
    >>> a/b
    结果是3，而不是3.4
  ```

## 浮点型(Float)

- 十进制形式：1.23、1.7

- 指数型：789E3，即 789 * 10^3 => 789000.0

- 指数型和浮点数的运算结果为浮点数

```
  >>> a = 10
  >>> b = 2.5
  >>> c = a*b
  >>> c
  25.0
  >>> type(c)
  float
```

## 字符串(String)

- 要保留字符串的原始格式(比如换行)，使用三个连续的双引号或单引号

```
  >>> str = '''The is a pig.
  Name is pug'''
  >>> str
  The is a pig.
  Name is pug
```

整型、浮点型、字符串相互转换

- 整型、字符串转浮点型

```
  >>> a = 3
  >>> b = float(a)
  >>> b
  3.0
  >>> type(b)
  float
  >>> a = '3.14'
  >>> b = float(a)
  >>> b
  3.14
  >>> type(b)
  float
```

- 浮点型、字符串转整型：int()

```
  >>> a = 3.14
  >>> b = int(a)
  >>> b
  3
  >>> type(b)
  int
  >>> a = '4'
  >>> b = int(a)
  >>> b
  4
  >>> type(b)
  int
```

- 浮点型、整型转字符串：str()

```
  >>> a = 3.14
  >>> b = str(a)
  >>> b
  3.14
  >>> type(b)
  str
```

## 布尔值(Boolean)

- 表示布尔值：true、false

- 逻辑运算：与、或、非

## 列表型

- 复杂的数据类型: [1,'asd']

- 列表中的数据称为元素

- 索引从0开始

- 列表连接

```
  >>> a = [1, 4]
  >>> b = [2, 5]
  >>> a + b
  [1, 4, 2, 5]
```

- 列表切片 [a:b]: 截取列表[a, b)索引内的元素

```
  >>> a = [1, 2, 3, 4, 5]
  >>> a[1:4]
  [2, 3, 4]
```

## 字典型

- 有很多条目组成：key - value，key 建立索引，value 存储数据

```
  >>> person = {'name': 'hoho', 'age': 13}
  >>> person['phone'] = 12345678901
```

# 函数

## 定义函数

用 def 关键字来定义函数。

```
  def say_hello():
		print 'Hello World'

	say_hello()  # Hello World
```

# 函数库

import 引入函数库

## python 标准函数库

### random

生成随机数。

- random.random()

  生成[0,1)之间的随机数。

- random.randint(a, b)

  生成 [a, b] 之间的一个整数。

### keyword

- keyword.kwlist

关键字列表

### os

包含普遍的操作系统功能。

- os.name: 判断现在正在使用的平台，windows 返回 'nt'，linux 返回 'posix'

- os.getcwd(): 获得当前的工作目录，不是当前文件的目录

- os.listdir(): 列出某个目录下所有的文件和目录名

```
	os.listdir('./')
```

- os.remove(): 删除指定文件

```
	os.remove('aa.txt')
```

- os.rmdir(): 删除指定目录

- os.mkdir(): 创建一个目录

- os.makedirs(): 递归创建目录

### sys

### math

### file

读写文件

## 第三方函数库

# 类

用 class 关键字来定义类。
