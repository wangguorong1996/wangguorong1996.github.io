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
- 驼峰大小写格式，第一个单词小写，剩下的每个单词首字母大写
- 不能把关键字、保留字、ture、false、null用作标识符
### 注释
- // 单行注释
- `/*`
  `*`多行注释
  `*/`
### 严格模式
指定函数中、脚本顶部添加编译指示`"use strict";`
### 语句
- 分号;结尾
- 多条语句组合到一个{}代码块
- 应该在控制语句中使用代码块，即使代码块只有一条语句
## 关键字
- break do instanceof typeof
- case else new var
- catch finally return void
- continue for switch while
- debugger function this with
- default if throw
- delete in try
## 变量
- 松散类型，保存任何类型的数据
- var操作符定义的变量是定义该变量的作用域中的局部变量，如果在函数中，变量在函数退出后被销毁。
## 数据类型
### typeof操作符
检测变量数据类型，可能返回字符串：
- “undefined”未定义
- “boolean”布尔值
- “string”字符串
- “number”数值
- “object”对象或null
- “function”函数
### undefined类型
在使用var声明变量但未对其初始化，这个变量值就是undefined
### null类型
- null值表示一个空对象指针，所以typeof检测null才会返回object
- undefined值是派生自null值的，相等性测试null==undefined返回true
### Boolean类型
- 两个字面值true和false
- 转型函数Boolean（）转换规则
<table>
    <tr>
        <th>数据类型</th>
        <th>转换为true的值</th>
        <th>转换为false的值</th>
    </tr>
    <tr>
        <td>Boolean</td>
        <td>true</td>
        <td>false</td>
    </tr>
    <tr>
        <td>String</td>
        <td>任何非空字符串</td>
        <td>空字符串""</td>
    </tr>
     <tr>
        <td>Number</td>
        <td>任何非零数值（包括无穷大）</td>
        <td>0和NaN</td>
    </tr>
     <tr>
        <td>Object</td>
        <td>任何对象</td>
        <td>null</td>
    </tr>
     <tr>
        <td>Undefined</td>
        <td>n/a</td>
        <td>undefined</td>
    </tr>
</table>

### Number类型
- 八进制第一位是0，十六位进制第一位是0x
- 0.1加0.2不是0.3，而是0.30000000000000004，浮点数值计算会产生舍入误差
- 正无穷 Infinite
- 负无穷 -Infinite
- NaN（Not a Number）是一个特殊的数值，任何数值除以非数值会返回NaN，任何涉及NaN的操作都会返回NaN,NaN与任何数值都不相等包括NaN本身
`alert(NaN == NaN);     //返回false`
- isNaN（）函数接受一个任何类型的参数之后，尝试转换为数值（例如字符串"10"或Boolean值），不能转换则返回true
- 数值转换函数 
    - Number（）转换任何数据类型
    - parseInt（）字符串转换成数值<ul>
            <li>如果第一个字符不是数字字符或负号，返回NaN</li>
            <li>如果第一个字符是数字字符或负号，则继续解析第二个字符直到遇到非数字字符</li>
            <li>能够识别各种数据格式（十进制、八进制（ES5中不具备了）、十六进制）</li>
            <li>可为函数提供转换使用的进制作为第二个参数，制定后，字符串可以不带"0x"</li>
        </ul>
        
        
    - pareFloat（）同上<ul>
            <li>字符串中第一个小数点有效，第二个无效</li>
            <li>始终忽略前导的0，只能解析十进制，无第二参数指定进制用法</li>
            <li>字符串没有小数点或者小数点后面都是零，返回一个整数</li>
        </ul>
    
### String类型
#### 字符字面量
特殊字符字面量--转义字符
<table>
    <tr>
        <th>字面量</th>
        <th>含义</th>
    </tr>
    <tr>
        <td>\n</td>
        <td>换行</td>
    </tr>
     <tr>
        <td>\t</td>
        <td>制表</td>
    </tr>
     <tr>
        <td>\b</td>
        <td>退格</td>
    </tr>
     <tr>
        <td>\r</td>
        <td>回车</td>
    </tr>
     <tr>
        <td>\f</td>
        <td>进纸</td>
    </tr>
     <tr>
        <td>\\</td>
        <td>斜杠</td>
    </tr>
     <tr>
        <td>\'</td>
        <td>单引号</td>
    </tr>
     <tr>
        <td>\"</td>
        <td>双引号</td>
    </tr>
     <tr>
        <td>\xnn</td>
        <td>以十六进制代码nn表示一个字符（n为0~F），例如\x41表示"A"</td>
    </tr>
     <tr>
        <td>\unnnn</td>
        <td>以十六进制代码nnnn表示一个Unicode字符（n为0~F），例如\u03a3表示希腊字符∑</td>
    </tr>
</table>

length属性，取得任何字符串属性长度`alert(texe.length);`
#### 字符串的特点
字符串一旦创建，值就不能改变，要改变首先要销毁原字符串再用新值字符串填充该变量。
转换字符变量：
- toString（）方法，返回相应值的字符串表现。null和undefined没有这个方法。默认输出十进制，以进制数作为第一个参数可输出二进制、八进制、十六进制
- String（）函数，将任何类型的值转换为字符串。
    - 如果值有toString（）方法则调用该方法
    - 如果值为null，返回"null"
    - 如果值为undefined，返回"undefined"

## 操作符

## 语句

## 函数

