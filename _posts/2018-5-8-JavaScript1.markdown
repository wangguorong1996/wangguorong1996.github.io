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
> JavaScript高级程序设计第1-3章。<br><br>

# 第1章 JavaScript简介
<div>
    <br>
    <ol>
        <li>在Netscape Navigator 2正式发布前，Netscape为了搭上媒体炒热的Java的顺风车，临时把LiveScript改名为JavaScript。</li>
        <br>
        <li>微软在其Internet Explorer 3 中加入了名为JScript的JavaScript实现。</li>
        <br>
        <li>欧洲计算机制造商协会ECMA指定39号技术委员会（TC39）完成了ECMA-262--一种名为ECMAScript的新脚本语言标准。</li>
        <br>
        <li>一个完整的JavaScript实现由三个部分组成：核心（ECMAScript）、文档对象模型（DOM）、浏览器对象模型（BOM）。 </li>
        <br>
        ECMA-262第3版标志着ECMAScript成为一门真正的编程语言。 </li>
        <br>
        <li>TC29下属的一个小组认为第4版跨度太大，提出ECMAScript3.1的替代性建议。ESMA-262第4版在正式发布前被放弃，ESMAScript3.1成为ECMA-262第5版。 </li>
        <br>
        <li>文档对象模型（DOM）是针对XML但经过扩展用于HTML的应用程序编程接口API，提供访问的操作页面内容的方法和接口。 </li>
        <br>
        <li>浏览器对象模型（BOM），提供与浏览器交互的方法和接口。 </li>
        <br>
        <li>五个主要浏览器：IE微软、Firefox火狐、Chrome谷歌、Safari苹果、Opera欧朋 </li>
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

## 1.语法
区分大小写
### 标识符
- 驼峰大小写格式，第一个单词小写，剩下的每个单词首字母大写
- 不能把关键字、保留字、ture、false、null用作标识符
### 注释
- // 单行注释
- `/*`
  `*`多行注释
  `*/`
### 严格模式
指定函数中、脚本顶部添加编译指示`"use strict";`为这门语言中容易出错的地方施加限制
### 语句
- 分号;结尾
- 多条语句组合到一个{}代码块
- 应该在控制语句中使用代码块，即使代码块只有一条语句
## 2.关键字
- break do instanceof typeof
- case else new var
- catch finally return void
- continue for switch while
- debugger function this with
- default if throw
- delete in try
## 3.变量
- 松散类型，保存任何类型的数据
- var操作符定义的变量是定义该变量的作用域中的局部变量，如果在函数中，变量在函数退出后被销毁。
## 4.数据类型
基本数据类型：Undefined、Null、Boolean、Number、String<br>复杂数据类型：Object
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
- toString（）方法，返回相应值的字符串表现。null和undefined没有这个方法。<br>默认输出十进制，以进制数作为第一个参数可输出二进制、八进制、十六进制
- String（）函数，将任何类型的值转换为字符串。
    - 如果值有toString（）方法则调用该方法
    - 如果值为null，返回"null"
    - 如果值为undefined，返回"undefined"
### Object类型
对象，就是一组数据和功能的集合。<br>执行new操作符创建`var 0 = new Object();`
Object的每个实例都具备一下属性和方法
- construction：保留着用于创建当前对象的函数
- hasOwnProperty（"propertyName"）：检查给定的属性在当前对象实例中（而不是在实例的原型中）是否存在
- isPrototypeOf(object)：检查传入对象对否是当前对象的原型
- propertyIsEnumerable（"propertyName"）：检查给定的属性是否能够使用for-in语句来枚举
- toLocaleString（）：返回对象的字符串表示，该字符串与执行环境的地区对应
- toString（）：返回对象的字符串
- valueOf（）：返回对象的字符串、数值、布尔值表示，通常与toString（）方法返回值相同
## 5.操作符
- 一元操作符
    - 一元加（+）：放在数值前不会产生任何影响，对非数值应用则如同Number（）转型函数一样转换该值
- 位操作符
    - 0表示正，1表示负
    - 负数以二进制补码（绝对值的反码加1）格式存储
    - 按位非`~`返回数值反码，数值表示的最底层执行操作，速度更快
    - 按位与`&`，32位整数每一位对其，全1出1
    - 按位或`|`，有1出1
    - 按位异或`^`，不同出1
    - 左移`<<`、右移`>>`，空位0填充，符号位不动
    - 无符号左移`<<<`，无符号右移`>>>`，符号位也移动
- 布尔操作符
    - 逻辑非`!`<br>对象、非空字符、非零数值（包括Infinity）返回false<br>空字符、0、null、NaN、undefined返回true<br>同时使用两个!!则模拟Bloolean（）转型函数
    - 逻辑与`&&`，短路操作，第一个操作数能够决定结果则不对第二个操作数求值
    - 逻辑或`||`，短路操作
- 乘性操作符
    - 乘法`*`，如果有一个操作符不是数值，则后台调用Number（）
    - 除法`/`
    - 求模`%`
- 加性操作符，有+0结果为+0
    - 加法 
    - 减法
- 关系操作符<、>、<=、>=
    - 如果两个操作数是字符串，则比较对应的字符编码。<br>如果是对象，则调用valueOf（）方法，没有则调用toString（）方法。<br>如果是布尔值则转化为数值比较
    - 如果一个是数值，则将另一个转化为数值再比较
    - 大写字母字符编码 < 小写字母字符编码
    - 任何操作符与NaN比较都返回false
- 相等操作符
    - 相等与不相等
    - 全等于不全等
- 条件转换符`var max = (num1 > num2) ? num1 : num2;`
- 赋值操作符 `*=`、`/=`、`%=`、`+=`、`-=`、`<<=`、`>>=`、`>>>=`,不会带来任何性能的提升

## 6.语句 
if、while、for、for-in、label、break、continue、with、switch
## 7.函数
- 位于return后面的语句永远不会执行
- return不带任何返回值则返回undefined
- argument对象类似数组，方括号访问元素，第一个元素`argument[0]`。<br>length属性确定传递了多少了参数,不是定义时命名参数的个数。<br>可以与命名函数一起使用。
- 没有重载（在同一作用域内，有一组不同参数列表的同名函数），定义两个同名函数，该名字属于后定义的函数

