---
layout:     post
title:      "JavaScript高级程序设计（一)"
subtitle:   "学习笔记"          
date:       2018-05-08 14:27:00
author:     "GR"
header-img: "img/post-bg-javascript1.jpg"
tags:
    - 笔记
    - js
    - JavaScript
---
> JavaScript高级程序设计第1-5章。<br><br>

# 第1章 JavaScript简介
<div>
    <br>
    <ol>
        <br><li>在Netscape Navigator 2正式发布前，Netscape为了搭上媒体炒热的Java的顺风车，临时把LiveScript改名为JavaScript。</li>
        <br>
        <br><li>微软在其Internet Explorer 3 中加入了名为JScript的JavaScript实现。</li>
        <br>
        <br><li>欧洲计算机制造商协会ECMA指定39号技术委员会（TC39）完成了ECMA-262--一种名为ECMAScript的新脚本语言标准。</li>
        <br>
        <br><li>一个完整的JavaScript实现由三个部分组成：核心（ECMAScript）、文档对象模型（DOM）、浏览器对象模型（BOM）。 </li>
        <br>
        <br><li>ECMA-262第3版标志着ECMAScript成为一门真正的编程语言。 </li>
        <br>
        <br><li>TC29下属的一个小组认为第4版跨度太大，提出ECMAScript3.1的替代性建议。ESMA-262第4版在正式发布前被放弃，ESMAScript3.1成为ECMA-262第5版。 </li>
        <br>
        <br><li>文档对象模型（DOM）是针对XML但经过扩展用于HTML的应用程序编程接口API，提供访问的操作页面内容的方法和接口。 </li>
        <br>
        <br><li>浏览器对象模型（BOM），提供与浏览器交互的方法和接口。 </li>
        <br>
        <br><li>五个主要浏览器：IE微软、Firefox火狐、Chrome谷歌、Safari苹果、Opera欧朋 </li>
        <br>
    </ol>
</div>

# 第2章 在HTML中使用JavaScript
## `<script>`元素
- type属性的值依旧还是text/javascript但不是必需。
- 解释器对`<script>`元素内部的所有代码求值完毕以前，页面其余内容都不会被浏览器加载或显示。
- 解析外部JavaScript文件时，页面处理会暂停。
- defer属性，脚本立即下载，但延迟到整个页面解析完毕后（文档完全呈现）顺序执行，只适用于外部脚本文件。
- async属性，不必等待其他脚本和文档呈现，但不保证先后顺序执行。
- `<noscript>`元素可以在不支持脚本、脚本被禁用的浏览器中显示替代内容。

# 第3章 基本概念

## 语法
### 区分大小写
### 标识符
驼峰大小写格式，第一个单词小写，剩下的每个单词首字母大写
不能把关键字、保留字、ture、false、null用作标识符
### 注释
// 单行注释
`/*`
 `*`多行注释
 `*/`
### 严格模式
指定函数中、脚本顶部添加编译指示`"use strict";`
### 语句
分号;结尾
多条语句组合到一个{}代码块
应该在控制语句中使用代码块，即使代码块只有一条语句
## 关键字
break do instanceof typeof
case else new var
catch finally return void
continue for switch while
debugger function this with
default if throw
delete in try
## 变量
松散类型，保存任何类型的数据
var操作符定义的变量是定义该变量的作用域中的局部变量，如果在函数中，变量在函数退出后被销毁。
## 数据类型
### typeof操作符
检测变量数据类型，可能返回字符串：“undefined”未定义、“boolean”布尔值、“string”字符串、“number”数值、“object”对象或null、“function”函数
### undefined类型
在使用var声明变量但未对其初始化，这个变量值就是undefined
### null类型
null值表示一个空对象指针，所以typeof检测null才会返回object
undefined值是派生自null值的，相等性测试null==undefined返回ture
### Boolean类型
两个字面值ture和false
转型函数Boolean（）转换规则
## 操作符

## 语句

## 函数

