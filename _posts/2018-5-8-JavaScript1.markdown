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
## <script>元素
- type属性的值依旧还是text/javascript但不是必需。
- 解释器对<script>元素内部的所有代码求值完毕以前，页面其余内容都不会被浏览器加载或显示。
- 解析外部JavaScript文件时，页面处理会暂停。
- defer属性，脚本立即下载，但延迟到整个页面解析完毕后（文档完全呈现）顺序执行，只适用于外部脚本文件。
- async属性，不必等待其他脚本和文档呈现，但不保证先后顺序执行。
- <noscript>元素可以在不支持脚本、脚本被禁用的浏览器中显示替代内容。
    

