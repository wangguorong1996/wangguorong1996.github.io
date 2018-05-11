---
layout:     post
title:      "JavaScript高级程序设计（五)"
subtitle:   "学习笔记"          
date:       2018-05-11 14:27:00
author:     "GR"
header-img: "img/post-bg-javascript1.jpg"
tags:
    - 笔记
    - js
    - JavaScript
---
> 转载请标明出处。<br><br>

# 第5章 引用类型
对象是某个特定引用类型的实例。
原生引用类型
## 1.Object类型
创建Object实例的方式：
- 使用new操作符后跟Object构造函数`var person = new Object();`
- 对象字面量表示法
                    `var person = {
                        name : "AAA",
                        age : 20};`
- 访问对象属性：
    - 点表示法`alert(person.name);`
    - 方括号表示法，属性是字符串形式`alert(person["name"]);`

## 2.Array类型
- 创建数组方式：
    - new后跟Array构造函数`var colors = new Array();`
    - 数组字面量表示法，`var colors = ["red","blue","green"];`
- 数组的项数保存在length属性中，可以设置这个属性，从数组的末尾移除或添加项。
`var colors = ["red","blue","green"];`
`colors.length = 2;                  //移除项`
`alert(colors[2]);                   //undefined`
`colors[colors.length] = "black";    //添加项`
`colors.length = 4;                  //添加项,不过项值为undefined`
- Array.isArray()方法，确定值是不是数组，不管在哪个全局执行环境中创建的
- 转换方法
    - toString()方法，返回数组每个值的字符串形式拼接成一个以逗号分隔的字符串
    - valueOf()方法
    - toLocaleString()方法，调用每一项的toLocaleString()方法
    - join()方法，接收一个作为分隔符的字符串的参数，使用不同的分隔符构建字符串
    - 数值某一项值为null或undefined，以上方法返回空字符串 
    - alert()接受字符串参数，后台调用toString()方法
    
- 模拟栈方法
<p>栈，后进先出的数据结构，项的插入、移除只发生在栈顶</p>
<p>push()方法，接收任意数量参数，添加到数组末尾，返回数组长度</p>
<p>pop()方法，移除最后一项，返回移除项</p>

- 模拟队列方法
<p>队列数据结构，先进先出，末端添加，前端移除</p>
<p>shift()方法，移除第一项，返回移除项</p>
<p>unshift()方法，前端添加任意个项，返回数组长度</p>

- 重排序方法

<p>reverse()方法，反转数组项的顺序</p>
<p>sort()方法，按升序排列数组项，调用每一项的toString()方法，比较的是字符串，"10"在"5"前面</p>

- 操作方法
    - concat()方法，创建一个副本数组，将接收的参数添加到副本数组末尾
    - slice()方法，只有一个参数，返回参数指定位置到数组末尾所有项，两个参数则返回起始到结束之间的项但不包括结束位置的项。参数为负则加上数组长度
    - splice()方法，向数组的中部插入项，返回删除的项组成的数组，无删除则空数组。可接受两个或三个参数splice(开始删除的项的位置，删除的项数，要插入的项)
- 位置方法
<p>接受两个参数，要查找的项和查找起点位置，返回查找项的位置，没找到返回-1</p>
    - indexOf()，数组开头向后查找
    - lastIndexOf()，数组末尾向前查找

- 迭代方法
<p>接收两个参数，要在每一项上运行的函数和运行该函数的作用域对象（可选）</p>
<p>运行的函数接收三个参数：数组项的值，该项位置（index则全部项），数组对象。都不会修改数组中的值</p>

    - every()：对数组每一项运行给定函数，每一项都返回true则返回true
    - filter()：返回true的项组成的数组
    - forEach()：无返回值
    - map()：函数调用的结果组成的数组
    - some()：任一项返回true则返回true
    
- 归并方法
<p>迭代所有项，构建一个最终返回的值。</p>
<p>方法接收两个参数，调用的函数和作为归并基础的初始值（可选）</p>
<p>调用的函数接收四个参数：前一个值，当前值，项的索引，数组对象</p> 

    - reduce(),正遍历
    - reduceRight()，反遍历

## 3.Date类型
- 创建一个日期对象，new操作符加Date构建函数`var now = new Date()；`
- 方法：
    - Date.parse()，接收一个表示日期的字符串参数，返回相应日期的毫秒数。如果字符串不能表示日期返回NaN。直接将日期字符串传递给构造函数Date会后台调用Date.parse()
    - Date.UTC()，可接收四个参数，前两个必须参数：年份，基于0的月份，基于1的日（默认1），基于0的小时数，分钟，秒以及毫秒数（默认0）
    - Date.now()，返回表示调用此方法的日期和时间的毫秒数

## 4.RegExp类型
通过此类型支持正则表达式
- 创建一个正则表达式`var expression = / pattern模式 / flags标志(g全局模式,i不区分大小写模式,m多行模式) ;`
- 
