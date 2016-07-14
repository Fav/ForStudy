---
layout: post
title: Lesson09-透明度基础
tags: osgjs
categories: osgjs官方教程笔记
---
[官方效果展示](http://codepen.io/osgjs/pen/jmqkJ)

这一节基本上所有的代码都在之前的内容中见过

## 知识点

### 透明度的改变

```
this.alpha += 0.01;
if ( this.alpha > 1.0 ) this.alpha = 0.0;
var channel;

channel = this.material.getDiffuse();
channel[ 3 ] = this.alpha;
```
可以看到 所做的更改是 漫反射的第四个分量 