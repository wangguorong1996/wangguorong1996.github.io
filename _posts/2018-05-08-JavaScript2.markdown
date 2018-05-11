---
layout:     post
title:      "JavaScript高级程序设计（一)"
subtitle:   "JavaScript高级程序设计第2章"          
date:       2018-05-08 10:25:00
author:     "GR"
header-img: "img/post-bg-javascript1.jpg"
tags:
    - 笔记
    - js
    - JavaScript
---
> 转载请标明出处。<br><br>


# 第2章 在HTML中使用JavaScript
## `<script>`元素
- type属性的值依旧还是text/javascript但不是必需。
- 解释器对`<script>`元素内部的所有代码求值完毕以前，页面其余内容都不会被浏览器加载或显示。
- 解析外部JavaScript文件时，页面处理会暂停。
- defer属性，脚本立即下载，但延迟到整个页面解析完毕后（文档完全呈现）顺序执行，只适用于外部脚本文件。
- async属性，不必等待其他脚本和文档呈现，但不保证先后顺序执行。
- `<noscript>`元素可以在不支持脚本、脚本被禁用的浏览器中显示替代内容。
